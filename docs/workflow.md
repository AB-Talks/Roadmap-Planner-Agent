# Agent Workflow

The AB Talks AI Agentic System uses a linear, step-by-step workflow where the output of one agent becomes the context or direct input for the next. 

```mermaid
graph TD
    A[Candidate Resume] -->|PDF Upload| B(Resume Parser Agent)
    C[Job Description] -->|Text Input| D(JD Parser Agent)
    
    B -->|Structured Profile| E{Readiness Match Agent}
    D -->|Structured Requirements| E
    
    E -->|Fit Score & Skill Gaps| F[Planner Agent]
    F -->|Interview Strategy| G[Interview Agent]
    
    G -->|Dynamic Question| H((Candidate))
    H -->|Answer| I[Judge Agent]
    
    I -->|Evaluation Rubric| J[Memory Agent]
    J -->|Updated Context| G
    
    J -->|End of Interview| K[Report Agent]
    B -->|Resume Data| L[Roadmap Agent]
    D -->|Target Role| L
```

## Step-by-Step Flow

1. **Information Extraction**: The system begins by asynchronously parsing both the candidate's Resume and the target Job Description.
2. **Alignment Assessment**: The Readiness Match Agent takes both parsed schemas and computes an initial baseline fit.
3. **Strategic Planning**: The Planner Agent uses the identified gaps to map out an interview strategy.
4. **Adaptive Interviewing**: The Interview Agent asks questions, the candidate answers, and the Judge Agent evaluates. The Memory Agent continuously tracks what skills have been proven.
5. **Finalization**: The Report Agent aggregates the entire session, while the Roadmap Agent provides actionable career feedback.
