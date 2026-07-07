<!--
Sync Impact Report
- Version change: 0.0.0 → 1.0.0
- Modified principles: None → MVP-First Scope Discipline, Simple Maintainable Architecture, Secure Input Handling and Safe Rendering, Testable User Journeys, Cross-Platform Reliability
- Added sections: Implementation Constraints, Quality Gates
- Removed sections: None
- Templates requiring updates: ⚠ pending .specify/templates/plan-template.md, .specify/templates/spec-template.md, .specify/templates/tasks-template.md
- Follow-up TODOs: None
-->

# RSS Feed Reader Constitution

## Core Principles

### I. MVP-First Scope Discipline
The project MUST deliver the smallest slice that proves the subscription-management experience before adding feed fetching, persistence, or visual polish. Any proposed feature outside the current MVP scope MUST be documented as Extended-MVP or post-MVP and explicitly deferred. This keeps the proof-of-concept focused, reviewable, and fast to build.

### II. Simple, Maintainable Architecture
The backend and frontend MUST use clear, single-purpose components and avoid premature abstraction. Shared logic MUST be extracted only when it is reused in more than one place, and the codebase MUST remain easy to read for another contributor. Models, API contracts, and UI state MUST stay minimal and explicit.

### III. Secure Input Handling and Safe Rendering
Feed URLs and any user-supplied content MUST be treated as untrusted. The application MUST avoid unsafe HTML rendering, MUST handle malformed input predictably, and MUST not assume that a pasted URL or feed payload is safe to process without validation. When feed fetching is introduced, sanitization and explicit error handling are mandatory.

### IV. Testable User Journeys
Each user-visible behavior MUST have a concrete acceptance scenario that can be verified manually or automatically before implementation is considered complete. The MVP MUST be testable by adding a subscription URL and confirming that the subscription appears in the UI. New behavior without a clear verification step is not accepted.

### V. Cross-Platform Reliability
The application MUST be buildable and runnable on Windows, macOS, and Linux without relying on OS-specific assumptions. Local configuration, including ports and API base URLs, MUST remain consistent and documented so a fresh clone can be verified with the same workflow.

## Implementation Constraints
The project MUST use the agreed technology stack of ASP.NET Core Web API for the backend and Blazor WebAssembly for the frontend. The MVP MUST remain limited to adding a subscription by URL and displaying the subscription list. In-memory storage is acceptable for the MVP, but persistence and background processing are explicitly deferred until a later phase. Configuration and routing MUST be verified before feature work continues.

## Quality Gates
Work is not complete until the relevant build and runtime checks have been performed and the user-visible behavior has been verified. Before a feature is considered done, the implementation MUST be checked for build errors, the expected UI or API behavior MUST be exercised, and any scope changes MUST be reflected in the relevant spec or plan documents. Pull requests MUST note which constitution principles apply to the change.

## Governance
This constitution supersedes ad hoc development practices for this repository. Any amendment MUST update the constitution and any affected planning or specification artifacts, and MUST include a clear rationale for the change. Versioning follows semantic versioning: major changes remove or redefine core principles, minor changes add or materially expand guidance, and patch changes clarify wording or improve non-semantic guidance. Compliance reviews MUST verify that implementation decisions remain consistent with these principles.

**Version**: 1.0.0 | **Ratified**: 2026-07-07 | **Last Amended**: 2026-07-07
