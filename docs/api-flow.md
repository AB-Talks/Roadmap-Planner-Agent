# API Flow

Because the agents are stateless functions, the API flow relies on passing strict JSON payloads and database IDs between endpoints.

## Standard Endpoint Interaction

```mermaid
sequenceDiagram
    participant Client as Playground UI
    participant Router as FastAPI
    participant Agent as Specific Agent
    participant Gemini as Gemini LLM API

    Client->>Router: POST /api/{agent} (Payload)
    Router->>Agent: Invoke Agent Logic
    Agent->>Gemini: Send System Prompt + User Data + Pydantic Schema
    Gemini-->>Agent: Return strictly typed JSON string
    Agent-->>Router: Parsed Python Dictionary
    Router-->>Client: 200 OK (JSON Response)
```

## Example: Match Agent Flow

1. **Client** sends a `POST` request to `/api/match`. It provides `resume_id` and `jd_id`.
2. **API Router** fetches the raw Resume JSON and JD JSON from the database.
3. **Match Agent** compiles a prompt: *"Compare this Candidate {resume} with this Role {jd}."*
4. **Gemini LLM** responds with an evaluation matching the `MatchSchema`.
5. **Client** receives the JSON and visually renders the fit score and gaps.
