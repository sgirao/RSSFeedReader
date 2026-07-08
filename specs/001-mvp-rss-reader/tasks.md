# Tasks: MVP RSS Reader

**Input**: Design documents from `/specs/001-mvp-rss-reader/`

**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2)
- Include exact file paths in descriptions

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Create the local web application structure for the MVP

- [ ] T001 Create backend and frontend project folders per implementation plan
- [ ] T002 Initialize ASP.NET Core Web API backend and Blazor WebAssembly frontend projects
- [ ] T003 [P] Configure shared development settings for local backend/frontend ports and API base URL

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Establish the minimal API and UI foundation required before user story implementation

- [ ] T004 Create the subscription model in backend/src/Models/Subscription.cs
- [ ] T005 Create the in-memory subscription service in backend/src/Services/SubscriptionStore.cs
- [ ] T006 Implement the subscriptions API controller in backend/src/Controllers/SubscriptionsController.cs
- [ ] T007 Create the main Blazor page for adding and displaying subscriptions in frontend/src/Pages/Subscriptions.razor
- [ ] T008 Implement the frontend subscription service in frontend/src/Services/SubscriptionService.cs
- [ ] T009 Configure routing and navigation so the MVP page is the default experience in frontend/src/Pages and frontend/src/Layout/NavMenu.razor

**Checkpoint**: Foundation ready - user story implementation can now begin

---

## Phase 3: User Story 1 - Add a feed subscription (Priority: P1) 🎯 MVP

**Goal**: Allow a user to enter a feed URL and add it to the current subscription list.

**Independent Test**: A user can open the app, paste a URL, submit it, and confirm that the URL appears in the subscription list.

### Implementation for User Story 1

- [ ] T010 [P] [US1] Add backend POST handling for subscription creation in backend/src/Controllers/SubscriptionsController.cs
- [ ] T011 [P] [US1] Add frontend form input and submit handling in frontend/src/Pages/Subscriptions.razor
- [ ] T012 [US1] Implement duplicate and empty-input handling for the subscription flow in backend/src/Services/SubscriptionStore.cs
- [ ] T013 [US1] Display success or validation feedback in the Blazor UI in frontend/src/Pages/Subscriptions.razor

**Checkpoint**: User Story 1 should be fully functional and testable independently

---

## Phase 4: User Story 2 - Review current subscriptions (Priority: P2)

**Goal**: Show the current set of subscriptions in the UI and keep them visible after additional submissions.

**Independent Test**: A user can add multiple subscriptions and verify that all of them remain visible in the list.

### Implementation for User Story 2

- [ ] T014 [P] [US2] Add backend GET handling for returning the current subscription list in backend/src/Controllers/SubscriptionsController.cs
- [ ] T015 [P] [US2] Load and render the subscription list from the frontend service in frontend/src/Pages/Subscriptions.razor
- [ ] T016 [US2] Ensure the UI refreshes after each successful add action in frontend/src/Pages/Subscriptions.razor
- [ ] T017 [US2] Add basic state handling for loading and rendering the list in frontend/src/Services/SubscriptionService.cs

**Checkpoint**: User Stories 1 and 2 should both work independently

---

## Phase 5: Polish & Cross-Cutting Concerns

**Purpose**: Finalize the MVP experience and confirm it aligns with the spec and quickstart

- [ ] T018 [P] Update documentation and local run guidance in specs/001-mvp-rss-reader/quickstart.md
- [ ] T019 Run backend/frontend build verification and verify the MVP flow end to end
- [ ] T020 Review the implementation against the constitution and feature spec for scope compliance

---

## Dependencies & Execution Order

### Phase Dependencies
- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS all user stories
- **User Stories (Phase 3+)**: Depend on Foundational completion
- **Polish (Phase 5)**: Depends on the completed user stories

### User Story Dependencies
- **User Story 1 (P1)**: Can start after Foundational completion
- **User Story 2 (P2)**: Can start after Foundational completion and can build on the same API/UI flow

### Parallel Opportunities
- T003 can run in parallel with project initialization tasks
- T010 and T011 can be implemented in parallel once the foundational pieces exist
- T014 and T015 can be implemented in parallel once the API and UI layers are wired
