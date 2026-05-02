# Technical Design: Atomix Internals

## Data Strategy

### 1. Persistence (Redis)
We utilize Redis Stack for both traditional key-value storage and vector-based semantic search.

*   **Atomic Notes (`note:{id}`):** Hash containing `title`, `body`, and `checksum`.
*   **Topic Index (`topics`):** Sorted Set for alphabetical navigation.
*   **Adjacency List (`links:{id}`):** Set of UUIDs representing bidirectional relationships.
*   **Vector Index:** Used by the `Linker` node to find semantically similar notes that don't share explicit keywords.

### 2. Messaging (Kafka)
Kafka acts as the system's "central nervous system," allowing the AI agents to work asynchronously without blocking the user.

*   `ingress.raw`: Incoming text fragments.
*   `ingress.files`: Metadata and paths for file imports.
*   `system.events`: Status updates (e.g., "Note #42 processed").
*   `system.notes`: Finalized notes broadcast to the UI.

## Agent Orchestration (LangGraph4J)

The AI logic is modeled as a stateful graph. Each execution session is checkpointed to Redis, allowing for long-running analyses.

1.  **Ingestor Node:** Normalizes input formats.
2.  **Reasoner Node:** Queries the existing Knowledge Base for context.
3.  **Extractor Node:** Generates the atomic note content using Spring AI.
4.  **Connector Node:** Suggests links and updates the adjacency list.

## Reactive Integration
The backend uses Spring WebFlux to maintain persistent WebSocket connections with the frontend. When a `system.notes` event is received from Kafka, it is immediately pushed to the client, triggering a UI update in the relevant pane.
