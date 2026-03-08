---

description: "Task list template for feature implementation"
---

# Tasks: [FEATURE NAME]

**Input**: Design documents from `/specs/[###-feature-name]/`
**Prerequisites**: plan.md (required), spec.md (required for user stories),
research.md, data-model.md, contracts/

**Verification**: The examples below include automated and manual verification tasks.
For user-facing catalog or gameplay changes, automated validation plus mobile and
desktop smoke checks are REQUIRED by the constitution. Add deeper test coverage
whenever the spec calls for it.

**Organization**: Tasks are grouped by user story to enable independent
implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Web game hub**: `apps/web/src/`, `packages/`, `tests/`
- **Web app + backend**: `apps/web/src/`, `apps/api/src/`, `packages/`, `tests/`
- Paths shown below assume a web game hub; adjust based on `plan.md`

<!--
  ============================================================================
  IMPORTANT: The tasks below are SAMPLE TASKS for illustration purposes only.

  The /speckit.tasks command MUST replace these with actual tasks based on:
  - User stories from spec.md (with their priorities P1, P2, P3...)
  - Feature requirements from plan.md
  - Entities from data-model.md
  - Endpoints from contracts/

  Tasks MUST be organized by user story so each story can be:
  - Implemented independently
  - Tested independently
  - Delivered as an MVP increment

  DO NOT keep these sample tasks in the generated tasks.md file.
  ============================================================================
-->

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic structure

- [ ] T001 Create project structure per implementation plan
- [ ] T002 Initialize [language] project with [framework] dependencies
- [ ] T003 [P] Configure linting and formatting tools
- [ ] T004 [P] Define supported browser/device matrix and smoke-test checklist in [path]
- [ ] T005 [P] Setup analytics or event schema baseline in [path]

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Core infrastructure that MUST be complete before ANY user story can be implemented

**⚠️ CRITICAL**: No user story work can begin until this phase is complete

Examples of foundational tasks (adjust based on your project):

- [ ] T006 Setup database schema and migrations framework
- [ ] T007 [P] Implement authentication or player identity framework
- [ ] T008 [P] Setup API routing and middleware structure
- [ ] T009 Create base models or entities that all stories depend on
- [ ] T010 [P] Establish shared game-shell and module integration contract
- [ ] T011 Configure error handling, logging, and rollback or kill-switch infrastructure
- [ ] T012 Setup environment configuration management

**Checkpoint**: Foundation ready - user story implementation can now begin in parallel

---

## Phase 3: User Story 1 - [Title] (Priority: P1) 🎯 MVP

**Goal**: [Brief description of what this story delivers]

**Independent Test**: [How to verify this story works on its own]

### Verification for User Story 1 ⚠️

> **NOTE: Add automated checks before implementation when the story changes playable
> or catalog behavior, and keep a manual smoke path for mobile and desktop browsers.**

- [ ] T013 [P] [US1] Contract or component test for [interface] in tests/contract/[name]
- [ ] T014 [P] [US1] Integration test for [user journey] in tests/integration/[name]
- [ ] T015 [US1] Record mobile and desktop smoke validation steps in tests/smoke/[name].md

### Implementation for User Story 1

- [ ] T016 [P] [US1] Create [Entity1/module] in [path]
- [ ] T017 [P] [US1] Create [Entity2/module] in [path]
- [ ] T018 [US1] Implement [service/gameplay loop] in [path] (depends on T016, T017)
- [ ] T019 [US1] Implement [route/feature] in [path]
- [ ] T020 [US1] Add validation, fallback handling, and accessibility support
- [ ] T021 [US1] Add analytics events and error logging for user story 1 operations
- [ ] T022 [US1] Validate performance budget for user story 1 in [path/tool]

**Checkpoint**: At this point, User Story 1 should be fully functional and testable independently

---

## Phase 4: User Story 2 - [Title] (Priority: P2)

**Goal**: [Brief description of what this story delivers]

**Independent Test**: [How to verify this story works on its own]

### Verification for User Story 2 ⚠️

- [ ] T023 [P] [US2] Contract or component test for [interface] in tests/contract/[name]
- [ ] T024 [P] [US2] Integration test for [user journey] in tests/integration/[name]
- [ ] T025 [US2] Record mobile and desktop smoke validation steps in tests/smoke/[name].md

### Implementation for User Story 2

- [ ] T026 [P] [US2] Create [Entity/module] in [path]
- [ ] T027 [US2] Implement [service/gameplay loop] in [path]
- [ ] T028 [US2] Implement [route/feature] in [path]
- [ ] T029 [US2] Integrate with shared shell or platform services (if needed)
- [ ] T030 [US2] Add analytics, fallback handling, and performance validation

**Checkpoint**: At this point, User Stories 1 AND 2 should both work independently

---

## Phase 5: User Story 3 - [Title] (Priority: P3)

**Goal**: [Brief description of what this story delivers]

**Independent Test**: [How to verify this story works on its own]

### Verification for User Story 3 ⚠️

- [ ] T031 [P] [US3] Contract or component test for [interface] in tests/contract/[name]
- [ ] T032 [P] [US3] Integration test for [user journey] in tests/integration/[name]
- [ ] T033 [US3] Record mobile and desktop smoke validation steps in tests/smoke/[name].md

### Implementation for User Story 3

- [ ] T034 [P] [US3] Create [Entity/module] in [path]
- [ ] T035 [US3] Implement [service/gameplay loop] in [path]
- [ ] T036 [US3] Implement [route/feature] in [path]
- [ ] T037 [US3] Add analytics, fallback handling, and performance validation

**Checkpoint**: All user stories should now be independently functional

---

[Add more user story phases as needed, following the same pattern]

---

## Phase N: Polish & Cross-Cutting Concerns

**Purpose**: Improvements that affect multiple user stories

- [ ] TXXX [P] Documentation updates in docs/
- [ ] TXXX Code cleanup and refactoring
- [ ] TXXX Performance optimization across all stories
- [ ] TXXX [P] Additional automated coverage in tests/unit/ or tests/component/
- [ ] TXXX Validate analytics dashboards or events in staging
- [ ] TXXX Security and privacy hardening
- [ ] TXXX Run quickstart.md validation
- [ ] TXXX Complete final mobile and desktop browser smoke pass

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **Foundational (Phase 2)**: Depends on Setup completion - BLOCKS all user stories
- **User Stories (Phase 3+)**: All depend on Foundational phase completion
  - User stories can then proceed in parallel (if staffed)
  - Or sequentially in priority order (P1 -> P2 -> P3)
- **Polish (Final Phase)**: Depends on all desired user stories being complete

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Foundational (Phase 2) - No dependencies on other stories
- **User Story 2 (P2)**: Can start after Foundational (Phase 2) - May integrate with US1 but should be independently testable
- **User Story 3 (P3)**: Can start after Foundational (Phase 2) - May integrate with US1/US2 but should be independently testable

### Within Each User Story

- Automated checks for user-facing behavior MUST exist before implementation is declared done
- Shared contracts or modules before service wiring
- Services or gameplay logic before routes or UI hooks
- Core implementation before integration
- Analytics, accessibility, and performance validation before story sign-off

### Parallel Opportunities

- All Setup tasks marked [P] can run in parallel
- All Foundational tasks marked [P] can run in parallel (within Phase 2)
- Once Foundational phase completes, all user stories can start in parallel (if team capacity allows)
- All verification tasks for a user story marked [P] can run in parallel
- Modules within a story marked [P] can run in parallel
- Different user stories can be worked on in parallel by different team members

---

## Parallel Example: User Story 1

```bash
# Launch all automated checks for User Story 1 together:
Task: "Contract or component test for [interface] in tests/contract/[name]"
Task: "Integration test for [user journey] in tests/integration/[name]"

# Launch all independent modules for User Story 1 together:
Task: "Create [Entity1/module] in [path]"
Task: "Create [Entity2/module] in [path]"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup
2. Complete Phase 2: Foundational (CRITICAL - blocks all stories)
3. Complete Phase 3: User Story 1
4. **STOP and VALIDATE**: Test User Story 1 independently
5. Deploy or demo if ready

### Incremental Delivery

1. Complete Setup + Foundational -> Foundation ready
2. Add User Story 1 -> Test independently -> Deploy/Demo (MVP!)
3. Add User Story 2 -> Test independently -> Deploy/Demo
4. Add User Story 3 -> Test independently -> Deploy/Demo
5. Each story adds value without breaking previous stories

### Parallel Team Strategy

With multiple developers:

1. Team completes Setup + Foundational together
2. Once Foundational is done:
   - Developer A: User Story 1
   - Developer B: User Story 2
   - Developer C: User Story 3
3. Stories complete and integrate independently

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- Each user story should be independently completable and testable
- Include mobile and desktop smoke coverage for user-facing changes
- Verify automated checks fail before implementing when applicable
- Commit after each task or logical group
- Stop at any checkpoint to validate story independently
- Avoid: vague tasks, same file conflicts, cross-story dependencies that break independence
