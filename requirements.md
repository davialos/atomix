# Functional Specification: Atomix

## Overview
Atomix aims to solve the "documentation rot" problem by automatically converting raw data into a living, interconnected knowledge base. The system focuses on high-speed ingestion and automated cross-referencing.

## Core Workflow

### 1. Ingestion
Users can interact with the system in two primary ways:
*   **Direct Stream:** Pasting text into the command interface.
*   **Batch Import:** Uploading Markdown or PDF files.

### 2. Processing Pipeline
The AI pipeline must:
1.  **Atomize:** Break down input into self-contained units of knowledge.
2.  **Contextualize:** Assign relevant metadata and tags.
3.  **Relate:** Identify references to existing topics and establish links.

## User Interface Design

The application utilizes a **Three-Pane Layout** for maximum information density:

| Pane | Role | Description |
| :--- | :--- | :--- |
| **Navigator** (Left) | Global View | An alphabetized list of all topics and tags in the system. |
| **Workspace** (Center) | Active Focus | Note viewer (top) and a chat-style ingestion input (bottom). |
| **Graph View** (Right) | Lateral Context | Displays all notes linked to the currently active topic. |

## System Goals
*   **Instant Visibility:** As soon as a note is linked, it must appear in the UI.
*   **Atomic Integrity:** Each note should focus on a single concept.
*   **Zero-Config Linking:** The user should not have to manually link related concepts.
