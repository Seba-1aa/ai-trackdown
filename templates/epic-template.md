---
# Epic Template - AI-TRACKDOWN v4.3.0
# High-level strategic initiative template

# Project Association (Optional)
# For multi-project environments, specify the parent project
# For single-project environments, this can be omitted or left as null
project_id: PRJ-0001  # Optional: Remove for single-project setups

epic_id: EP-0000
type: epic
title: "[Epic Title]"
description: "High-level overview of what this epic accomplishes"
state: planning
status: planning                     # DEPRECATED: Use state field
priority: high
assignee: "@teamlead"
created_date: "2025-07-09T10:00:00Z"
updated_date: "2025-07-09T10:00:00Z"
estimated_tokens: 1000
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
  transitioned_by: "@teamlead"
  previous_state: null
  automation_eligible: true
  assignee_on_transition: null
  notifications_sent: []
labels: []
target_date: "2025-08-01T00:00:00Z"
token_budget: 50000
token_usage:
  total: 0
  by_agent: {}
sync:
  github: null
  jira: null
  linear: null
related_issues: []
completion_percentage: 0
dependencies: []
blocked_by: []
blocks: []
---

# [Epic Title]

> **Usage Mode**: This template supports both single-project and multi-project environments.
> - **Single Project**: Remove or set `project_id: null` in the frontmatter
> - **Multi-Project**: Specify the parent project ID (e.g., `PRJ-0001`)

## Executive Summary
[High-level overview of what this epic accomplishes]

## Business Value
[Why is this epic important? What business problem does it solve?]

## Success Metrics
[How will we measure the success of this epic?]
- Success metric 1: [Target value]
- Success metric 2: [Target value]
- Success metric 3: [Target value]

## Target Outcomes
[What should be true when this epic is complete?]
- [ ] Outcome 1
- [ ] Outcome 2
- [ ] Outcome 3

## Scope
### In Scope
- Feature/capability 1
- Feature/capability 2
- Feature/capability 3

### Out of Scope
- Feature/capability that will NOT be included
- Future consideration items

## Technical Architecture
[High-level technical approach and architecture decisions]

### Key Components
- Component 1: [Brief description]
- Component 2: [Brief description]
- Component 3: [Brief description]

### Integration Points
- Integration 1: [Description]
- Integration 2: [Description]

## Issues Breakdown
[List of issues that comprise this epic]
- [ ] ISSUE-000: [Issue title] (Status: open)
- [ ] ISSUE-000: [Issue title] (Status: open)
- [ ] ISSUE-000: [Issue title] (Status: open)

## Dependencies
[External dependencies that could impact this epic]
- [ ] External dependency 1
- [ ] External dependency 2
- [ ] Team dependency 1

## Risk Assessment
[Major risks and mitigation strategies]

### High Risk Items
- Risk 1: [Description and mitigation]
- Risk 2: [Description and mitigation]

### Medium Risk Items
- Risk 1: [Description and mitigation]
- Risk 2: [Description and mitigation]

## Timeline
[Key milestones and dates]

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| Milestone 1 | YYYY-MM-DD | pending |
| Milestone 2 | YYYY-MM-DD | pending |
| Milestone 3 | YYYY-MM-DD | pending |

## Resource Requirements
[Team members, skills, tools needed]

### Team Assignment
- Epic Owner: @teamlead
- Technical Lead: @techlead
- Contributors: @dev1, @dev2, @dev3

### Skills Required
- Skill 1
- Skill 2
- Skill 3

## Token Tracking
[AI token usage tracking for this epic]

| Date | Agent | Issue/Task | Tokens | Purpose |
|------|-------|------------|--------|----------|
| YYYY-MM-DD | [Agent] | [Task] | [Count] | [Purpose] |

### Token Budget Status
- Budget: 50,000 tokens
- Used: 0 tokens (0%)
- Remaining: 50,000 tokens
- Alert threshold: 40,000 tokens (80%)

## Stakeholder Communication
[Key stakeholders and communication plan]

### Stakeholders
- Primary: [Name/Role]
- Secondary: [Name/Role]
- Informed: [Name/Role]

### Communication Plan
- Weekly updates: [Day/Time]
- Milestone reviews: [Schedule]
- Demo schedule: [Schedule]

## Activity Log
- YYYY-MM-DDTHH:mm:ssZ: Epic created by @teamlead

## Related Epics
- Blocks: []
- Blocked by: []
- Related: []

## Research & Discovery
[Research findings, user interviews, technical spikes]

## Testing Strategy
[Overall testing approach for the epic]

### Test Coverage
- Unit tests: [Coverage target]
- Integration tests: [Coverage target]
- End-to-end tests: [Coverage target]
- Performance tests: [Criteria]

## Documentation Plan
[Documentation that needs to be created or updated]
- [ ] User guide updates
- [ ] API documentation
- [ ] Architecture documentation
- [ ] Runbook updates

## Rollout Strategy
[How will this epic be deployed and rolled out?]

### Deployment Phases
- Phase 1: [Description]
- Phase 2: [Description]
- Phase 3: [Description]

### Rollback Plan
[How to rollback if issues arise]

## Post-Epic Review
[Items to assess after epic completion]
- [ ] Success metrics achieved
- [ ] Performance benchmarks met
- [ ] User feedback collected
- [ ] Lessons learned documented
