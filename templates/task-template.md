---
# Task Template - AI-TRACKDOWN v4.3.0
# Specific implementation task template

# Project Association (Optional)
# For multi-project environments, specify the parent project
# For single-project environments, this can be omitted or left as null
project_id: PRJ-0001  # Optional: Remove for single-project setups

task_id: TSK-0000
type: task
issue_id: ISS-0000
epic_id: EP-0000
title: "[Task Title]"
description: "Brief description of what needs to be done"
state: open
status: planning                     # DEPRECATED: Use state field
priority: medium
assignee: "@username"
created_date: "2025-07-09T10:00:00Z"
updated_date: "2025-07-09T10:00:00Z"
estimated_tokens: 100
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
  previous_state: null
  automation_eligible: true
  assignee_on_transition: "@username"
  notifications_sent: []
labels: []
estimate: 0
token_usage:
  total: 0
  by_agent: {}
sync:
  github: null
  jira: null
  linear: null
subtasks: []
completion_percentage: 0
dependencies: []
blocked_by: []
blocks: []
---

# [Task Title]

> **Usage Mode**: This template supports both single-project and multi-project environments.
> - **Single Project**: Remove or set `project_id: null` in the frontmatter
> - **Multi-Project**: Specify the parent project ID (e.g., `PRJ-0001`)

## Description
[Brief description of what needs to be done]

## Acceptance Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## Implementation Notes
[Technical details, approach, constraints]

## Token Context
<!-- AI_CONTEXT_START -->
[Context for AI agents working on this task]
<!-- AI_CONTEXT_END -->

## Activity Log
- YYYY-MM-DDTHH:mm:ssZ: Created by @username

## Related Tasks
- Blocks: []
- Blocked by: []
- Related: []

## Files Modified
- [ ] `path/to/file1.js`
- [ ] `path/to/file2.js`

## Testing Notes
[Test cases, edge cases, validation steps]

## Documentation Updates
- [ ] README.md
- [ ] API documentation
- [ ] Code comments

## Review Checklist
- [ ] Code review completed
- [ ] Tests passing
- [ ] Documentation updated
- [ ] Performance impact assessed
