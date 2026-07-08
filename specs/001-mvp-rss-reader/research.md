# Research: MVP RSS Reader

## Decisions

- Decision: Implement the MVP with ASP.NET Core Web API for the backend and Blazor WebAssembly for the frontend.
  - Rationale: This matches the project’s stated technology direction and supports future extension without a full rewrite.
  - Alternatives considered: A single-page JavaScript application and a console-only prototype. Both were rejected because the project explicitly targets a web-based UI and a .NET-friendly architecture.

- Decision: Keep subscription storage in memory for the MVP.
  - Rationale: The stakeholder goals state that persistence is deferred and the simplest implementation is acceptable for the proof-of-concept.
  - Alternatives considered: Database-backed storage. Rejected because it adds complexity not required for the first milestone.

- Decision: Limit the first version to adding subscriptions and listing them.
  - Rationale: This is the core user story and matches the MVP scope defined in the stakeholder documents.
  - Alternatives considered: Feed fetching, parsing, and item display. Rejected because those features are explicitly out of scope for the current milestone.
