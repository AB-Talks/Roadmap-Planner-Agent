# AB Talks AI Agents

> **Open-source AI agents built by the AB Talks community for recruitment, interview preparation, and practical AI workflows.**

<p align="center">
  <b>Build. Learn. Contribute.</b>
</p>

## Why this project?

This repository contains modular AI agents developed as part of the AB Talks AI Challenge.

Each agent solves a specific task and can be reused independently or combined into larger AI workflows. We believe in practical, open-source AI development where each component is clean, self-contained, and easy to understand.

## Available Agents

| Agent | Purpose |
| --- | --- |
| **Resume Parser** | Extracts structured data from messy PDFs |
| **JD Parser** | Transforms raw job descriptions into precise requirements |
| **Readiness Match** | Compares candidates against role schemas to find gaps |
| **Interview Agent** | Simulates dynamic, adaptive technical interviews |
| **Judge Agent** | Evaluates interview responses against scoring rubrics |
| **Planner Agent** | Formulates interview and study roadmaps |
| **Report Agent** | Compiles QA history into final evaluation insights |
| **Memory Agent** | Maintains long-term context across workflows |

## Workflow

```text
Resume
      ↓
Resume Agent

Job Description
      ↓
JD Agent

      ↓
      
Readiness Match

      ↓

Interview

      ↓

Judge

      ↓

Final Report
```

## Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/abtalks/AI-Agents.git
   cd AI-Agents
   ```

2. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run an Agent:**
   ```bash
   python "Interview Agent"/interview_agent.py
   ```

## Example Use Cases
- Candidate Screening
- Resume and Job Description Parsing
- Mock Interviews
- Skill Gap Analysis

## Future Agents
- ⬜ Resume Optimizer
- ⬜ ATS Simulator
- ⬜ Career Coach
- ⬜ Salary Negotiator

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md) for details. In short:
1. Fork the repo
2. Create a branch
3. Commit your changes
4. Open a Pull Request

## License
MIT License. See [LICENSE](LICENSE) for details.
