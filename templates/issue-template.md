---
# Issue Template - AI-TRACKDOWN v4.3.0
# Detailed implementation issue template

# Project Association (Optional)
# For multi-project environments, specify the parent project
# For single-project environments, this can be omitted or left as null
project_id: PRJ-0001  # Optional: Remove for single-project setups

issue_id: ISS-0000
type: issue
epic_id: EP-0000
title: "[Issue Title]"
description: "Detailed description of the issue or feature request"
state: ready_for_engineering
status: planning                     # DEPRECATED: Use state field
priority: medium
assignee: "@username"
created_date: "2025-07-09T10:00:00Z"
updated_date: "2025-07-09T10:00:00Z"
estimated_tokens: 500
actual_tokens: 0
ai_context:
  - "context/requirements"
  - "context/constraints"
  - "context/assumptions"
  - "context/dependencies"
sync_status: local

# State metadata for automation and tracking
state_metadata:
  transitioned_at: "2025-07-09T10:00:00Z"
  transitioned_by: "@username"
  previous_state: planning
  automation_eligible: true
  assignee_on_transition: "@engineering"
  notifications_sent: ["@engineering"]
labels: []
estimate: 0
token_usage:
  total: 0
  by_agent: {}
sync:
  github: null
  jira: null
  linear: null
related_tasks: []
related_issues: []
completion_percentage: 0
dependencies: []
blocked_by: []
blocks: []
---

# [Issue Title]

> **Usage Mode**: This template supports both single-project and multi-project environments.
> - **Single Project**: Remove or set `project_id: null` in the frontmatter
> - **Multi-Project**: Specify the parent project ID (e.g., `PRJ-0001`)

## Description
[Detailed description of the issue or feature request]

## Problem Statement
[What problem does this solve? What is the current pain point?]

## Acceptance Criteria
- [ ] Primary acceptance criterion
- [ ] Secondary acceptance criterion
- [ ] Edge case handling
- [ ] Error handling
- [ ] Performance requirements

## Technical Requirements
[Technical specifications, constraints, dependencies]

### Dependencies
- [ ] Dependency 1
- [ ] Dependency 2

### Architecture Impact
[How this affects the overall system architecture]

## Design Considerations
[UI/UX considerations, user flows, design mockups]

## Token Context
<!-- AI_CONTEXT_START -->
[Context for AI agents working on this issue]
Related files: []
Key concepts: []
Integration points: []
<!-- AI_CONTEXT_END -->

## Breakdown
[List of tasks that need to be completed]
- [ ] TASK-000: [Task description]
- [ ] TASK-000: [Task description]
- [ ] TASK-000: [Task description]

## Activity Log
- YYYY-MM-DDTHH:mm:ssZ: Created by @username

## Related Issues
- Blocks: []
- Blocked by: []
- Related: []
- Depends on: []

## Success Metrics
[How will we measure success?]
- Metric 1: [Target value]
- Metric 2: [Target value]

## Testing Strategy
[Test approach, test cases, validation criteria]

### Test Cases
- [ ] Happy path test
- [ ] Edge case test
- [ ] Error handling test
- [ ] Performance test
- [ ] Integration test

## Documentation Requirements
- [ ] User documentation
- [ ] Developer documentation
- [ ] API documentation
- [ ] Runbook updates

## Rollout Plan
[Deployment strategy, rollback plan, monitoring]

## Risk Assessment
[Potential risks and mitigation strategies]

## Discussion
[Questions, concerns, alternative approaches]
