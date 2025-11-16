# UdaPlay --- Agentic AI Research Assistant for Game Knowledge

UdaPlay is an end-to-end **Agentic AI system** that demonstrates how
large language models can combine *retrieval-augmented generation
(RAG)*, *tool use*, and *web-connected reasoning* to answer open-domain
questions about video games.

This project mirrors the design patterns used in real-world AI products:
vector search, tool orchestration, memory, evaluation loops, and
LLM-driven decision-making.

------------------------------------------------------------------------

## 🚀 What This Project Demonstrates

### ✔ Building a Local RAG System from Scratch

-   Persistent vector store using **ChromaDB**
-   Embedding and indexing pipeline for structured JSON metadata
-   Document schema design (name, platform, genre, publisher,
    description, release year)
-   Top-k retrieval with similarity scoring
-   Evaluation utilities to measure retrieval quality

### ✔ Developing a Modern Agentic AI System

A fully functioning agent with:
- **RAG-based reasoning**
- **Web-search augmentation** via Tavily
- **Tool use and tool routing**
- **Session-based short-term memory** (conversation state tied to a session ID)
- **Natural-language outputs** (readable text without enforced schema)
- Automated fallback: if local retrieval is insufficient, the agent intelligently triggers a web search


This is the same pattern used by advanced agents built with frameworks
like LangGraph, crewAI, and OpenAI tool calling.

------------------------------------------------------------------------

## 🧱 High-Level Architecture

    UdaPlay Agent
    ├── Memory Layer
    │    └── Conversation state + retrieved context
    ├── Tools
    │    ├── retrieve_game()       → Vector search
    │    ├── evaluate_retrieval()  → Scoring + quality check
    │    └── game_web_search()     → External knowledge via Tavily
    └── LLM Reasoning Loop
         ├── Think
         ├── Retrieve / Use Tools
         ├── Validate Results
         └── Produce Structured Final Answer

The agent dynamically selects the best tool based on retrieval
confidence --- a hallmark of modern agent design.

------------------------------------------------------------------------

## 📂 Repository Structure

    project/
    ├── starter/
    │   ├── games/                       # Video game metadata (JSON)
    │   ├── lib/
    │   │   ├── llm.py                   # LLM abstraction + model wrapper
    │   │   ├── messages.py              # Message schema + memory structures
    │   │   ├── tooling.py               # Tool implementations
    │   │   └── ...
    │   ├── Udaplay_01_starter_project.ipynb   # RAG construction
    │   └── Udaplay_02_starter_project.ipynb   # Agent development

------------------------------------------------------------------------

## ⚙️ Technology Stack

-   **Python 3.11+**
-   **ChromaDB** (vector database)
-   **OpenAI** (LLM + embedding model)
-   **Tavily Search API**
-   **dotenv**
-   **Jupyter Notebook** for prototyping

------------------------------------------------------------------------

## ▶️ How to Run

1.  Create a virtual environment\
2.  Install required packages\
3.  Add your API keys to a `.env` file:


    OPENAI_API_KEY="YOUR_KEY"
    CHROMA_OPENAI_API_KEY="YOUR_KEY"
    TAVILY_API_KEY="YOUR_KEY"

4.  Run notebooks in order:
    -   **Part 1:** Build the vector store & embedding pipeline\
    -   **Part 2:** Build the agent & integrate tool use\
    -   Test with your own queries

------------------------------------------------------------------------

## 🧪 Example Interactions

Try questions like: - **"When was Pokémon Gold and Silver released?"** -
**"Which Mario game first introduced 3D platforming?"** - **"Was Mortal
Kombat X released for PlayStation 5?"**

The agent will: 1. Search the vector database\
2. Evaluate retrieval quality\
3. Automatically decide whether to perform web search\
4. Synthesize a structured final answer

------------------------------------------------------------------------

## 🌟 Optional Enhancements

This project is intentionally extensible. Some potential next steps: -
Long-term memory (episodic + semantic) - Confidence scoring with
retrieval thresholds - Tool-routing graphs using LangGraph - Automated
evaluation suite for regression testing - Support for multimodal game
data (images, screenshots) - Web UI wrapper (e.g., using Streamlit or
Gradio)

------------------------------------------------------------------------

## 🧠 Why This Project Matters

RAG and agentic systems are the foundation of modern enterprise AI.\
This project illustrates the real mechanisms behind those systems: \
- Knowledge indexing\
- Tool orchestration\
- Session-based memory\
- Dynamic retrieval\
- Natural language output\
- LLM reasoning loops

It's a practical, end-to-end demonstration of **agent architecture
design** --- the same concepts used in production-grade AI assistants
across industry.
