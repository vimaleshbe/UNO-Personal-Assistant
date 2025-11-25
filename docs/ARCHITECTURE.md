# Architecture

Overview
- This document explains the high-level architecture of the Personal Assistant service and includes an editable SVG diagram in `assets/architecture.svg`.

High-level components
- User Clients: Telegram, web UI, or other chat clients.
- Gateway: REST endpoints and webhook handlers accept user messages.
- Orchestrator: Service layer that prepares LLM requests and applies memory patterns.
- Model Provider: External LLM APIs (OpenAI, Azure OpenAI, etc.).
- Memory Store: short-term and long-term storage for remembered facts and conversation state.

Flow
1. User sends message via Telegram (webhook) or REST client.
2. Controller receives update and forwards to orchestrator service.
3. Orchestrator composes CopilotChatRequest and calls LLM via `CopilotService`.
4. Response is processed, memory patterns are applied, and selected items persist to the memory store.
5. Formatted response is returned to the user via the platform adapter.

Diagram
- See `assets/architecture.svg` for a simple block diagram you can use in posts and screenshots.

Notes for screenshots
- Open `assets/architecture.svg` in a browser or editor (Inkscape, VS Code) and capture a high-resolution screenshot for LinkedIn posts.

Author
- vimalesh jeyavelmani
