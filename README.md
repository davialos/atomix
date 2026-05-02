# Atomix

**Atomix** is an event-driven knowledge engine designed to ingest large-scale documentation and distill it into a structured graph of "atomic notes." It leverages Java 21's Virtual Threads, Spring AI, and LangGraph4J to orchestrate complex agentic workflows that automatically identify, tag, and link knowledge fragments.

## 🚀 Key Features

*   **Autonomous Mining:** Automated extraction of core concepts from raw text and files.
*   **Dynamic Graphing:** Bidirectional linking between notes based on semantic relevance.
*   **Real-time Interaction:** A reactive, three-pane interface for viewing and refining knowledge.
*   **Modular Monolith:** A clean, decoupled architecture built for scale and maintainability.

## 🛠️ Technology Stack

- **Backend:** Java 21, Spring Boot 3.3 (WebFlux), Gradle (Kotlin DSL).
- **AI/LLM:** Spring AI, Gemini 3 Flash, LangGraph4J.
- **Messaging:** Apache Kafka.
- **Data:** Redis Stack (State, Caching, and Vector Search).
- **Frontend:** React, Vite, Tailwind CSS.

## 📖 Documentation

- [User Requirements](requirements.md)
- [Architecture & Modules](architecture.md)
- [Technical Design](technical_design.md)

---
*Created for high-performance knowledge management.*