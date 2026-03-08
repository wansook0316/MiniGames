# Implementation Plan: [FEATURE]

**Branch**: `[###-feature-name]` | **Date**: [DATE] | **Spec**: [link]
**Input**: Feature specification from `/specs/[###-feature-name]/spec.md`

**Note**: This template is filled in by the `/speckit.plan` command. See
`.specify/templates/plan-template.md` for the execution workflow.

## Summary

[Extract from feature spec: primary requirement + technical approach from research]

## Technical Context

<!--
  ACTION REQUIRED: Replace the content in this section with the technical details
  for the project. The structure here is presented in advisory capacity to guide
  the iteration process.
-->

**Language/Version**: [e.g., TypeScript 5.x, Unity WebGL, Rust 1.75 or NEEDS CLARIFICATION]  
**Primary Dependencies**: [e.g., React, Phaser, Pixi, Vite or NEEDS CLARIFICATION]  
**Storage**: [if applicable, e.g., localStorage, IndexedDB, PostgreSQL or N/A]  
**Testing**: [e.g., Vitest, Playwright, Cypress or NEEDS CLARIFICATION]  
**Target Platform**: [e.g., mobile and desktop web browsers or NEEDS CLARIFICATION]  
**Supported Browsers/Devices**: [e.g., iPhone Safari, Android Chrome, desktop Chrome/Edge or NEEDS CLARIFICATION]  
**Input Model**: [e.g., touch-first with keyboard/mouse fallback or NEEDS CLARIFICATION]  
**Project Type**: [e.g., web-game-hub, web-app + backend or NEEDS CLARIFICATION]  
**Performance Goals**: [e.g., <=3s TTI, <=10s to first playable action, 60 fps gameplay or NEEDS CLARIFICATION]  
**Constraints**: [e.g., 2D only, mobile-first, low asset weight, privacy-safe analytics or NEEDS CLARIFICATION]  
**Accessibility Baseline**: [e.g., readable at 360px, reduced motion support, labeled controls or NEEDS CLARIFICATION]  
**Telemetry**: [e.g., catalog_view, game_start, retry, session_complete, error events or NEEDS CLARIFICATION]  
**Scale/Scope**: [e.g., initial catalog size, estimated DAU, number of game modules or NEEDS CLARIFICATION]

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

- Browser-first delivery is defined: supported browsers/device classes are named, and
  any unsupported capability has a fallback or explicit exclusion.
- The feature remains within the 2D web mini-game catalog scope, or the plan records
  an approved constitution exception.
- Touch-first mobile UX is specified, with desktop keyboard/mouse behavior documented
  where relevant.
- Performance budgets are explicit, including load time and time-to-first-play goals.
- The integration contract identifies what belongs to the shared shell versus the
  per-game module, including metadata, analytics, and failure handling.
- Accessibility, telemetry, and rollback or kill-switch expectations are captured for
  every user-facing change.
- Validation includes automated checks plus manual smoke coverage for mobile and
  desktop browser profiles.

## Project Structure

### Documentation (this feature)

```text
specs/[###-feature]/
├── plan.md              # This file (/speckit.plan command output)
├── research.md          # Phase 0 output (/speckit.plan command)
├── data-model.md        # Phase 1 output (/speckit.plan command)
├── quickstart.md        # Phase 1 output (/speckit.plan command)
├── contracts/           # Phase 1 output (/speckit.plan command)
└── tasks.md             # Phase 2 output (/speckit.tasks command - NOT created by /speckit.plan)
```

### Source Code (repository root)
<!--
  ACTION REQUIRED: Replace the placeholder tree below with the concrete layout
  for this feature. Delete unused options and expand the chosen structure with
  real paths (e.g., apps/admin, packages/something). The delivered plan must
  not include Option labels.
-->

```text
# [REMOVE IF UNUSED] Option 1: Web game hub (DEFAULT)
apps/
└── web/
    ├── src/
    │   ├── app/
    │   ├── catalog/
    │   ├── games/
    │   └── shared/
    └── tests/

packages/
├── game-sdk/
├── platform-services/
└── ui/

tests/
├── contract/
├── integration/
└── smoke/

# [REMOVE IF UNUSED] Option 2: Web app + backend services
apps/
├── web/
│   ├── src/
│   │   ├── app/
│   │   ├── catalog/
│   │   ├── games/
│   │   └── shared/
│   └── tests/
└── api/
    ├── src/
    │   ├── routes/
    │   ├── services/
    │   └── domain/
    └── tests/

packages/
├── game-sdk/
├── platform-services/
└── ui/

tests/
├── contract/
├── integration/
└── smoke/
```

**Structure Decision**: [Document the selected structure and reference the real
directories captured above]

## Complexity Tracking

> **Fill ONLY if Constitution Check has violations that must be justified**

| Violation | Why Needed | Simpler Alternative Rejected Because |
|-----------|------------|-------------------------------------|
| [e.g., native wrapper] | [current need] | [why browser-only delivery is insufficient] |
| [e.g., per-game custom SDK] | [specific problem] | [why shared platform layer is insufficient] |
