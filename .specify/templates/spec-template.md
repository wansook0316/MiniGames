# Feature Specification: [FEATURE NAME]

**Feature Branch**: `[###-feature-name]`  
**Created**: [DATE]  
**Status**: Draft  
**Input**: User description: "$ARGUMENTS"

## User Scenarios & Testing *(mandatory)*

<!--
  IMPORTANT: User stories should be PRIORITIZED as user journeys ordered by importance.
  Each user story/journey must be INDEPENDENTLY TESTABLE - meaning if you implement just ONE of them,
  you should still have a viable MVP (Minimum Viable Product) that delivers value.

  Assign priorities (P1, P2, P3, etc.) to each story, where P1 is the most critical.
  Think of each story as a standalone slice of functionality that can be:
  - Developed independently
  - Tested independently
  - Deployed independently
  - Demonstrated to users independently
-->

### User Story 1 - [Brief Title] (Priority: P1)

[Describe this user journey in plain language]

**Why this priority**: [Explain the value and why it has this priority level]

**Independent Test**: [Describe how this can be tested independently - e.g., "Can be fully tested by [specific action] and delivers [specific value]"]

**Acceptance Scenarios**:

1. **Given** [initial state], **When** [action], **Then** [expected outcome]
2. **Given** [initial state], **When** [action], **Then** [expected outcome]

---

### User Story 2 - [Brief Title] (Priority: P2)

[Describe this user journey in plain language]

**Why this priority**: [Explain the value and why it has this priority level]

**Independent Test**: [Describe how this can be tested independently]

**Acceptance Scenarios**:

1. **Given** [initial state], **When** [action], **Then** [expected outcome]

---

### User Story 3 - [Brief Title] (Priority: P3)

[Describe this user journey in plain language]

**Why this priority**: [Explain the value and why it has this priority level]

**Independent Test**: [Describe how this can be tested independently]

**Acceptance Scenarios**:

1. **Given** [initial state], **When** [action], **Then** [expected outcome]

---

[Add more user stories as needed, each with an assigned priority]

### Edge Cases

<!--
  ACTION REQUIRED: The content in this section represents placeholders.
  Fill them out with the right edge cases.
-->

- What happens when [boundary condition]?
- How does system handle [error scenario]?
- What happens when an asset or game module fails to load on a supported browser?
- How does the experience degrade when a device cannot meet the preferred input or
  rendering mode?

## Experience Constraints *(mandatory for gameplay and catalog UX)*

### Platform & Input

- Target device classes: [e.g., touch phones first, tablet supported, desktop supported]
- Supported browsers: [e.g., iPhone Safari latest, Android Chrome latest, desktop Chrome/Edge latest]
- Primary input model: [e.g., touch gestures with keyboard fallback]
- Unsupported capability fallback: [e.g., degrade particle effects, disable tilt controls, show compatibility notice]

### Performance & Accessibility

- Time to interactive target: [e.g., <= 3 seconds on mid-range mobile]
- Time to first meaningful action: [e.g., <= 10 seconds from entry]
- Frame rate or animation target: [e.g., 60 fps gameplay on baseline devices]
- Accessibility baseline: [e.g., readable at 360px width, reduced motion respected, labeled controls]

### Instrumentation & Operations

- Required analytics events: [e.g., catalog_view, game_start, retry, session_complete]
- Error/health signals: [e.g., client error logging, asset load failures]
- Rollback or disable path: [e.g., feature flag, route removal, game hidden from catalog]
- Content safety or moderation needs: [e.g., age rating, ad constraints, external link review]

## Requirements *(mandatory)*

<!--
  ACTION REQUIRED: The content in this section represents placeholders.
  Fill them out with the right functional requirements.
-->

### Functional Requirements

- **FR-001**: System MUST [specific capability, e.g., "allow users to create accounts"]
- **FR-002**: System MUST [specific capability, e.g., "validate email addresses"]  
- **FR-003**: Users MUST be able to [key interaction, e.g., "reset their password"]
- **FR-004**: System MUST [data requirement, e.g., "persist user preferences"]
- **FR-005**: System MUST [behavior, e.g., "log all security events"]
- **FR-006**: System MUST define supported browsers, input methods, and fallback behavior
  for unsupported capabilities.
- **FR-007**: System MUST define measurable performance and accessibility requirements
  for the primary user flow.
- **FR-008**: System MUST specify required analytics events and a rollback or disable
  path for user-facing releases.

*Example of marking unclear requirements:*

- **FR-009**: System MUST authenticate users via [NEEDS CLARIFICATION: auth method not specified - email/password, SSO, OAuth?]
- **FR-010**: System MUST retain user data for [NEEDS CLARIFICATION: retention period not specified]

### Key Entities *(include if feature involves data)*

- **[Entity 1]**: [What it represents, key attributes without implementation]
- **[Entity 2]**: [What it represents, relationships to other entities]

## Success Criteria *(mandatory)*

<!--
  ACTION REQUIRED: Define measurable success criteria.
  These must be technology-agnostic and measurable.
-->

### Measurable Outcomes

- **SC-001**: [Measurable metric, e.g., "Users can complete account creation in under 2 minutes"]
- **SC-002**: [Measurable metric, e.g., "System handles 1000 concurrent users without degradation"]
- **SC-003**: [User satisfaction metric, e.g., "90% of users successfully complete primary task on first attempt"]
- **SC-004**: [Business metric, e.g., "Reduce support tickets related to [X] by 50%"]
- **SC-005**: [Performance metric, e.g., "90% of users reach first playable action within 10 seconds on baseline mobile devices"]
- **SC-006**: [Quality metric, e.g., "All required analytics events are recorded for the primary journey in staging validation"]
