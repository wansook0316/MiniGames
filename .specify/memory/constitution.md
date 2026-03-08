<!--
Sync Impact Report
Version change: template -> 1.0.0
Modified principles:
- PRINCIPLE_1_NAME -> I. Browser-First Game Delivery
- PRINCIPLE_2_NAME -> II. Mobile-Ready 2D UX
- PRINCIPLE_3_NAME -> III. Fast Session, Fast Load
- PRINCIPLE_4_NAME -> IV. Modular Game Integration
- PRINCIPLE_5_NAME -> V. Measured Quality Gates
Added sections:
- Product Scope & Constraints
- Delivery Workflow
Removed sections:
- None
Templates requiring updates:
- ✅ updated .specify/templates/plan-template.md
- ✅ updated .specify/templates/spec-template.md
- ✅ updated .specify/templates/tasks-template.md
- ✅ reviewed .specify/templates/agent-file-template.md (no change required)
- ✅ reviewed .specify/templates/constitution-template.md (no change required)
- ✅ no command templates present under .specify/templates/commands/
Follow-up TODOs:
- None
-->

# MiniGames Constitution

## Core Principles

### I. Browser-First Game Delivery
Every playable experience MUST run in a modern browser without requiring a native
install. Each game MUST expose a direct URL, define its supported browser baseline,
and provide a graceful fallback when an optional device capability is unavailable.
Rationale: this project succeeds only if casual players can start instantly across
common mobile and desktop browsers.

### II. Mobile-Ready 2D UX
All first-party experiences MUST be 2D and designed for touch-first mobile play while
remaining usable with keyboard and mouse on larger screens. Core flows MUST stay
legible at 360px viewport width or wider, present explicit control instructions, and
document any orientation assumptions in the feature spec. Rationale: the primary
audience is mobile web, but the catalog must remain usable on general browser clients.

### III. Fast Session, Fast Load
Each catalog page or game entry point MUST define a load budget and a time-to-first-
play target in its specification. The default target is an interactive screen within
3 seconds on a mid-range mobile network and a first meaningful action within 10
seconds from page entry. Features MUST prefer short-session loops, resumable state,
and asset budgets that protect repeat visits. Rationale: web mini-games compete on
immediacy, and slow starts directly reduce retention.

### IV. Modular Game Integration
Every game MUST integrate through a documented module contract that covers route
registration, metadata, asset ownership, analytics events, pause/resume hooks, and
failure handling. Shared platform concerns such as navigation, player progress,
monetization surfaces, and telemetry MUST live in reusable platform layers rather
than being reimplemented per game. Rationale: the catalog must scale cleanly as more
games are added.

### V. Measured Quality Gates
Every launch candidate MUST pass automated build validation and at least one manual
smoke pass on both a mobile browser profile and a desktop browser profile. Specs,
plans, and tasks MUST explicitly capture accessibility checks, performance budgets,
analytics coverage, and rollback or disable paths for user-facing changes. Rationale:
consumer-facing game regressions are product failures, not isolated engineering
issues.

## Product Scope & Constraints

- Initial scope is a browser-delivered catalog of 2D mini-games and the shared shell
  that lets players discover, launch, and replay them.
- Native mobile apps, 3D rendering, real-money gambling, high-risk PII collection,
  and hardware-specific integrations are out of scope unless a future amendment
  explicitly approves them.
- Shared platform capabilities MAY include anonymous progress, leaderboards,
  monetization, promotions, and social sharing, but each addition MUST define privacy
  impact, moderation requirements, and a failure fallback in the feature spec.
- New third-party SDKs or embeds MUST justify bundle cost, privacy impact, and
  operational ownership before adoption.

## Delivery Workflow

- Every significant change MUST begin with `/speckit.specify`, `/speckit.plan`, and
  `/speckit.tasks`, using this constitution as the default gate.
- Specifications MUST identify target devices and browsers, control scheme,
  accessibility considerations, performance budgets, analytics events, and any
  content-safety or moderation risks.
- Implementation plans MUST record the chosen architecture for shared shell,
  game module boundaries, data ownership, and any justified complexity exceptions.
- Task lists MUST preserve at least one independently shippable player journey and
  include tasks for performance verification, analytics wiring, and mobile/desktop
  smoke validation whenever user-visible behavior changes.
- Releases MUST include browser/device coverage notes plus a rollback or kill-switch
  path when the change affects a live game or catalog flow.

## Governance

- This constitution supersedes conflicting local conventions and planning shortcuts.
- Amendments require a documented diff, approval from the project owner, and updates
  to any impacted templates or runtime guidance in the same change.
- Compliance reviews MUST occur during plan creation, task generation, and pre-release
  review. Any temporary exception MUST be recorded in the relevant plan or release
  notes with rationale and an expiry condition.
- Semantic versioning applies to this constitution:
  - MAJOR for removing or materially redefining a principle or supported product scope.
  - MINOR for adding a principle or materially expanding governance obligations.
  - PATCH for clarifications that do not change governance meaning.

**Version**: 1.0.0 | **Ratified**: 2026-03-08 | **Last Amended**: 2026-03-08
