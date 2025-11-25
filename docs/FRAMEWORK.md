# Framework & Tech Stack

This repository documents the frameworks and libraries used in the original Personal Assistant project. The actual source code is excluded from this proxy.

Primary stack
- Language: Java 21 (LTS)
- Framework: Spring Boot (controllers, configuration, dependency injection)
- HTTP client: Spring WebClient for calling LLM APIs and external services
- Build: Maven (pom.xml in original project)

Key Components
- `CopilotService`: coordinates requests/responses with LLM provider(s).
- `MemoryPatternsService`: rules for extracting and persisting memory items.
- Webhook controllers: handle platform updates (example: Telegram).

External Integrations
- LLM endpoints (OpenAI, Azure OpenAI, or other hosted LLMs) via REST.
- Messaging platforms: Telegram webhook integration.
- Optional: Azure services (Key Vault, CosmosDB, Blob Storage) for secrets and memory persistence.

Deployment
- Containerize with Docker when deploying to cloud.
- Recommended: use secret stores and managed identity where possible.
