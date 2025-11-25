# MCP Details — Personal Assistant

Summary
This document summarizes the Model-Context-Protocol (MCP) design, integration points, and patterns used by the original Personal Assistant project. The full implementation code and prompt book are intentionally not included in this repository.

Key Concepts
- Model: Java Spring Boot application containing services that orchestrate calls to large language models and maintain conversational memory.
- Context: Conversation-level state and memory patterns are stored and retrieved via pluggable memory services (short-term and long-term), with patterns that decide what to persist.
- Protocol: Interaction flows use HTTP REST endpoints and webhooks (e.g., Telegram) to accept user updates, translate them into copilot chat requests, call the LLM endpoints, and return formatted responses.

Architecture Integration Points
- Controllers: accept incoming webhooks and REST calls (e.g., `TelegramController`, `AiController`).
- Services: `CopilotService` (LLM orchestration), `MemoryPatternsService` (persistence rules), and supporting services for transformations.
- Config: `SpringAiConfig`, `WebClientConfig`, `UserAuthorizationConfig` for credentials and HTTP client setup.

Security & Secrets
Secrets and API keys are kept outside this repository. In production, use secret stores (Azure Key Vault or environment variables).

Notes
- This document describes design and integration; the concrete implementation code resides in the original project and is excluded here.
