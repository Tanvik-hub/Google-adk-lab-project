# Google-adk-lab-project
Code and lab files for Google's "Get started with Agent Development Kit (ADK)" Qwiklab (GENAI104).

# Get started with Agent Development Kit (ADK) - Lab Project

This repository contains my completed project from the Google Cloud lab **GENAI104: Get started with Agent Development Kit**. This lab was my first hands-on experience bridging the gap between the *theory* of AI agents and the *practical* steps of building, testing, and running them.

## 📖 What I Learned (The "Class" Concepts)

Before the hands-on, I learned the core components of the Agent Development Kit (ADK) and what makes it a powerful framework:

  * **Agents:** The core AI "workers" or "brains" designed to accomplish specific tasks.
  * **Tools:** How to give agents real-world abilities. An agent with a `Search` tool is no longer limited to its training data; it can access the live internet.
  * **Session Services (State & Events):** This is the agent's "memory." It allows an agent to remember the context of a conversation, which is essential for multi-step tasks.
  * **The Runner:** This is the "engine" that manages the entire lifecycle, executing the agent's logic and handling the flow of information.
  * **Orchestration:** The concept of using multiple agents together (sequentially, in parallel, etc.) to solve complex problems.
  * **RAG (Retrieval-Augmented Generation):** The formal name for what I built. The agent *retrieves* new information (from search) to *augment* its final, generated response.
  * <img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/60087df4-f4cf-428b-9a29-0a5a57dc2bc8" />
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/34e84fca-a9de-4072-977e-f01a0bdd4ad7" />


-----

## 🛠️ What I Did & Explored (The "Hands-On" Lab)

This lab was focused on building and running agents in different ways. Here's a summary of what's in this project.

### 1\. Agent with a Tool (`my_google_search_agent`)

This was the "Hello, World\!" of ADK.

  * **What I did:** I built a single agent and, with just one line of code, equipped it with the pre-built `Google Search` tool.
  * **Why it's cool:** This transformed the agent from a simple chatbot into a real-time assistant. By asking it **"What is some recent global news?"**, I could see it use the tool to find current information that its base model couldn't possibly know.

### 2\. Structured Output Agent (`app_agent`)

This agent demonstrated how to make an agent's output reliable for use in a real application.

  * **What I did:** I created a new agent and used a **Pydantic `BaseModel`** to define a strict `output_schema`.
  * **Why it's cool:** This is a critical feature. Instead of the agent replying with a conversational sentence like "The capital of France is Paris," I forced it to *only* reply with structured JSON:
    ```json
    {"capital": "Paris"}
    ```
    This makes the agent's output predictable and machine-readable, so another program can use its answer reliably.

### 3\. The Three Ways to Run an Agent

A major part of the lab was seeing the different ways to test and deploy an agent:

1.  **💻 The ADK Dev UI (`adk web`)**
    This was my visual debugger. It was perfect for development, allowing me to inspect the entire "thought process" of the agent—every event, state change, and tool call—in a clear web interface.

2.  **🐍 Programmatically (Python script)**
    This is how an agent would be used in a real application (e.g., as part of a web server backend). It required me to manually set up the `Runner` and `SessionService` that the Dev UI normally handles automatically.

3.  **⌨️ The CLI Chat Interface (`adk chat`)**
    This was a fast, simple way to interact with the agent directly from my terminal for a quick test.

    <img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/7b50405b-5d0c-48a9-9cc0-e06e97369b9f" />


-----

## 💡 Key Takeaways

This lab was a great introduction to the power of agentic AI. The biggest "a-ha" moment was realizing the difference between a simple LLM and an **agent**. An agent can perceive its environment, take actions with tools, and (with output schemas) provide reliable, structured data that other software can actually build upon.
