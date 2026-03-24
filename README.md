# LangGraph + Groq: AI Workflow Patterns

This repository contains my practice notebooks for building agentic workflows. It explores the four fundamental design patterns of AI orchestration using **LangGraph** for logic and **Groq** for high-speed inference.

**Workflow Patterns Explored**

1. **Sequential Workflow**
The simplest form of orchestration. The output of one LLM node is passed directly as the input to the next. This is ideal for multi-step content generation (e.g., Title -> Outline -> Full Blog).

2. **Parallel (Fan-out/Fan-in) Workflow**
Multiple nodes run at the same time to perform independent tasks. This uses a Reducer function to collect all parallel outputs into a single state before proceeding to a "Join" node.
Example: Calculating different cricket statistics (Strike Rate, Boundary %) simultaneously.

3. **Conditional (Branching) Workflow**
A "Router" function evaluates the current state and decides which path the graph should take. This allows for triage and specialized handling based on logic.
Example: Routing a support ticket to different nodes based on Sentiment Analysis.

4. **Iterative (Self-Correction) Workflow**
A loop where a "Writer" generates content and a "Critic" evaluates it. If the quality score doesn't meet the threshold, the graph loops back for a rewrite until the criteria are met or the iteration limit is reached.

## 🛠 Installation

To run these notebooks, you will need to install the following libraries:

langchain-groq 

langgraph 

python-dotenv 

pydantic

You will also need a `.env` file in the root directory with your API key:
`GROQ_API_KEY=your_gsk_key_here`