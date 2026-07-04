# System Architecture

The project is built on a modular, decoupled architecture, allowing each agent to act as an independent microservice or function. 

## High-Level Architecture

```mermaid
graph LR
    subgraph Frontend [Client Layer]
        UI[Agent Playground HTML/JS]
    end

    subgraph API [API Gateway / Router]
        FastAPI[FastAPI Server]
    end

    subgraph Agents [Agentic Layer]
        A1[Resume Agent]
        A2[JD Agent]
        A3[Match Agent]
        A4[Interview Agent]
        A5[Judge Agent]
        A6[Report Agent]
    end

    subgraph External [External Services]
        LLM[Google Gemini API]
        DB[(Supabase DB)]
    end

    UI -->|HTTP POST| FastAPI
    FastAPI --> A1 & A2 & A3 & A4 & A5 & A6
    A1 & A2 & A3 & A4 & A5 & A6 -->|Prompt + Schema| LLM
    A1 & A2 & A3 & A4 & A5 & A6 -->|Read/Write State| DB
```

## Component Details

1. **Client Layer:** A lightweight HTML/JS frontend (Agent Playground) that makes direct API calls.
2. **Agentic Layer:** Pure Python modules. Each agent contains specialized system prompts and Pydantic schemas to strictly type the LLM outputs.
3. **LLM Engine:** `gemini_core.py` manages the connection to the Google Gemini API, ensuring consistent JSON enforcement across all agents.
4. **State Persistence:** Database integrations (like Supabase) are used to store parsed profiles and ongoing interview transcripts so that context is not lost between HTTP requests.
