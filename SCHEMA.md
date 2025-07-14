# AI-Trackdown Ticketing Schema

## Overview

The AI-Trackdown ticketing system uses a hierarchical structure to organize project work into manageable units. This document defines the schema structure, field definitions, and data format for all ticket types.

## Hierarchical Structure

### Relationship Model

```
Projects (Multi-Project Management)
  ↓ contains
Epics (Strategic Initiatives)
  ↓ contains
Issues (Implementation Features)
  ↓ breaks down into
Tasks (Development Work)
  ↓ results in
Pull Requests (Code Changes)
```

### Visual Hierarchy

```
📁 Multi-Project Portfolio
├── 📋 Project (PRJ-XXXX)       # Project container
│   ├── 📊 Epic (EP-XXXX)       # Strategic initiatives
│   │   ├── 🎯 Issue (ISS-XXXX) # Implementation features
│   │   │   ├── ✅ Task (TSK-XXXX) # Development work
│   │   │   └── 🔄 Task (TSK-YYYY) # Development work
│   │   └── 🎯 Issue (ISS-YYYY) # Implementation features
│   │       ├── ✅ Task (TSK-ZZZZ) # Development work
│   │       └── 🔀 Pull Request (PR-XXXX) # Code changes
│   └── 📊 Epic (EP-YYYY)       # Strategic initiatives
└── 📋 Project (PRJ-YYYY)       # Project container
```

## Usage Modes

### Single-Project Mode

For individual projects or small teams, AI-Trackdown can operate without explicit project containers. In this mode:
- Project information is stored in configuration files
- All tickets (epics, issues, tasks, PRs) belong to the implicit project
- Directory structure focuses on ticket type organization
- Ideal for single-repository development workflows

### Multi-Project Mode

For larger organizations or teams managing multiple projects simultaneously:
- Each project has its own PRJ-XXXX identifier
- Project-specific metadata includes git repositories, team members, and deployment info
- Hierarchical organization with projects as the top-level container
- Cross-project dependencies and relationships are tracked
- Ideal for enterprise environments and multi-team coordination

## Ticket Type Definitions

### Project (PRJ-XXXX)

**Purpose**: Top-level container for multi-project management with git repository integration and team coordination.

**Schema Structure**:
```yaml
project_id: PRJ-0001                 # Auto-generated identifier
type: project                        # Type identifier
name: "AI-TRACKDOWN"                 # Display name
title: "AI-TRACKDOWN Project Management System" # Full title
description: "Hierarchical ticket management system for AI-driven development workflows" # Project description
state: open                          # Unified state (replaces status)
status: active                       # DEPRECATED: Use state field
priority: high                       # Business priority
assignee: @maintainer               # Project owner
created_date: 2025-07-09T10:00:00Z  # Creation timestamp
updated_date: 2025-07-09T10:00:00Z  # Last modification
estimated_tokens: 10000             # Total AI processing estimate
actual_tokens: 2500                  # Actual AI tokens consumed
ai_context:                          # AI context categories
  - context/requirements
  - context/dependencies
sync_status: synced                  # External sync state
# State metadata for automation and tracking
state_metadata:
  transitioned_at: 2025-07-09T10:00:00Z    # Last state change timestamp
  transitioned_by: @maintainer             # Who changed the state
  previous_state: planning                  # Previous state for rollback
  automation_eligible: true                # Can be auto-transitioned
  assignee_on_transition: @maintainer      # Auto-assign on state change
  notifications_sent: []                   # Notification tracking
git_origin: "https://github.com/user/ai-trackdown.git" # Git repository URL
git_branch: main                     # Default branch
repository_url: "https://github.com/user/ai-trackdown.git" # Repository URL
clone_url: "git@github.com:user/ai-trackdown.git" # Clone URL
default_branch: main                 # Default git branch
languages: ["javascript", "json", "markdown"] # Programming languages
framework: "Node.js CLI"             # Technology stack
deployment_url: "https://npmjs.com/package/ai-trackdown" # Production URL
documentation_url: "https://ai-trackdown.com/docs" # Documentation URL
team_members: ["@maintainer", "@contributor1", "@contributor2"] # Team members
license: "MIT"                       # Project license
completion_percentage: 75            # Progress indicator
related_projects: []                 # Related project identifiers
```

**Content Structure**:
- Project overview and business context
- Technical specifications and architecture
- Git repository and deployment configuration
- Team member roles and responsibilities
- Integration and dependency management
- Resource allocation and budget tracking
- Progress metrics and completion criteria
- Cross-project relationships and dependencies

### Epic (EP-XXXX)

**Purpose**: Strategic initiatives spanning multiple features and requiring complex coordination.

**Schema Structure**:
```yaml
epic_id: EP-0001                    # Auto-generated identifier
project_id: PRJ-0001                # Parent project reference (multi-project mode)
title: "Strategic Initiative Name"   # Business-focused title
description: "Business outcome..."   # Executive summary
state: planning                      # Unified state (replaces status)
status: planning                     # DEPRECATED: Use state field
priority: high                       # Business importance
assignee: masa                       # Primary owner
created_date: 2025-07-09T10:00:00Z  # Creation timestamp
updated_date: 2025-07-09T10:00:00Z  # Last modification
estimated_tokens: 1000              # AI processing estimate
actual_tokens: 0                     # Actual AI tokens consumed
ai_context:                          # AI context categories
  - context/requirements
  - context/constraints
  - context/assumptions
  - context/dependencies
sync_status: local                   # External sync state
# State metadata for automation and tracking
state_metadata:
  transitioned_at: 2025-07-09T10:00:00Z    # Last state change timestamp
  transitioned_by: masa                    # Who changed the state
  previous_state: null                     # Previous state for rollback
  automation_eligible: true                # Can be auto-transitioned
  assignee_on_transition: null             # Auto-assign on state change
  notifications_sent: []                   # Notification tracking
related_issues: []                   # Linked issues
dependencies: []                     # Epic dependencies
completion_percentage: 0             # Progress indicator
```

**Content Structure**:
- Overview section with business context
- Strategic goals with measurable outcomes
- Success metrics and completion criteria
- Scope definition (in-scope/out-of-scope)
- Dependencies and prerequisites
- Timeline and milestone planning
- Risk assessment and mitigation
- Related issues (auto-populated)
- Additional notes and considerations

### Issue (ISS-XXXX)

**Purpose**: Specific features or enhancements within an epic, focused on implementation deliverables.

**Schema Structure**:
```yaml
issue_id: ISS-0001                   # Auto-generated identifier
project_id: PRJ-0001                # Parent project reference (multi-project mode)
epic_id: EP-0001                     # Parent epic reference
title: "Feature Implementation"      # Implementation-focused title
description: "Technical feature..."  # Technical description
state: ready_for_engineering         # Unified state (replaces status)
status: planning                     # DEPRECATED: Use state field
priority: high                       # Implementation priority
assignee: masa                       # Primary developer
created_date: 2025-07-09T10:00:00Z  # Creation timestamp
updated_date: 2025-07-09T10:00:00Z  # Last modification
estimated_tokens: 500               # AI processing estimate
actual_tokens: 0                     # Actual AI tokens consumed
ai_context:                          # AI context categories
  - context/requirements
  - context/constraints
  - context/assumptions
  - context/dependencies
sync_status: local                   # External sync state
# State metadata for automation and tracking
state_metadata:
  transitioned_at: 2025-07-09T10:00:00Z    # Last state change timestamp
  transitioned_by: masa                    # Who changed the state
  previous_state: planning                 # Previous state for rollback
  automation_eligible: true                # Can be auto-transitioned
  assignee_on_transition: @engineering     # Auto-assign on state change
  notifications_sent: ["@engineering"]     # Notification tracking
related_tasks: []                    # Linked tasks
related_issues: []                   # Peer issues
completion_percentage: 0             # Progress indicator
blocked_by: []                       # Blocking dependencies
blocks: []                           # Dependent items
```

**Content Structure**:
- Description with technical requirements
- Task breakdown list
- Acceptance criteria with testable conditions
- Implementation notes and considerations

### Task (TSK-XXXX)

**Purpose**: Specific development work items with clear deliverables and action steps.

**Schema Structure**:
```yaml
task_id: TSK-0001                    # Auto-generated identifier
project_id: PRJ-0001                # Parent project reference (multi-project mode)
issue_id: ISS-0001                   # Parent issue reference
epic_id: EP-0001                     # Root epic reference
title: "Development Task"            # Action-oriented title
description: "Specific work item..." # Clear deliverable description
state: in_progress                   # Unified state (replaces status)
status: active                       # DEPRECATED: Use state field
priority: medium                     # Development priority
assignee: masa                       # Assigned developer
created_date: 2025-07-09T10:00:00Z  # Creation timestamp
updated_date: 2025-07-09T10:00:00Z  # Last modification
estimated_tokens: 100               # AI processing estimate
actual_tokens: 0                     # Actual AI tokens consumed
ai_context:                          # AI context categories
  - context/requirements
  - context/constraints
  - context/assumptions
  - context/dependencies
sync_status: local                   # External sync state
# State metadata for automation and tracking
state_metadata:
  transitioned_at: 2025-07-09T10:00:00Z    # Last state change timestamp
  transitioned_by: masa                    # Who changed the state
  previous_state: open                     # Previous state for rollback
  automation_eligible: true                # Can be auto-transitioned
  assignee_on_transition: masa             # Auto-assign on state change
  notifications_sent: ["masa"]             # Notification tracking
subtasks: []                         # Sub-task breakdown
blocked_by: []                       # Blocking dependencies
blocks: []                           # Dependent items
```

**Content Structure**:
- Description with specific work definition
- Implementation steps (numbered sequence)
- Acceptance criteria with verification points
- Technical notes and implementation details

### Pull Request (PR-XXXX)

**Purpose**: Code changes and review workflow for completed development work.

**Schema Structure**:
```yaml
pr_id: PR-0001                       # Auto-generated identifier
project_id: PRJ-0001                # Parent project reference (multi-project mode)
issue_id: ISS-0001                   # Parent issue reference
epic_id: EP-0001                     # Root epic reference
title: "Code Change Title"           # Git commit style title
description: "Code changes..."       # Technical change description
state: ready_for_review              # Unified state (replaces status)
status: open                         # DEPRECATED: Use state field
priority: medium                     # Review priority
assignee: masa                       # Code author
created_date: 2025-07-09T10:00:00Z  # Creation timestamp
updated_date: 2025-07-09T10:00:00Z  # Last modification
estimated_tokens: 50                # AI processing estimate
actual_tokens: 0                     # Actual AI tokens consumed
ai_context:                          # AI context categories
  - context/requirements
  - context/constraints
sync_status: local                   # External sync state
# State metadata for automation and tracking
state_metadata:
  transitioned_at: 2025-07-09T10:00:00Z    # Last state change timestamp
  transitioned_by: masa                    # Who changed the state
  previous_state: open                     # Previous state for rollback
  automation_eligible: true                # Can be auto-transitioned
  assignee_on_transition: @reviewers       # Auto-assign on state change
  notifications_sent: ["@reviewers"]       # Notification tracking
branch_name: feature/branch-name     # Git branch reference
files_changed: []                    # Modified file list
review_status: pending               # DEPRECATED: Use state field
```

**Content Structure**:
- Description with code change summary
- Files modified and change rationale
- Testing performed and validation steps
- Review notes and feedback

## Field Reference

### Common Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `*_id` | String | Yes | Auto-generated unique identifier |
| `title` | String | Yes | Human-readable title |
| `description` | String | Yes | Detailed description |
| `state` | String | Yes | Unified state (replaces status) |
| `status` | String | No | DEPRECATED: Use state field |
| `priority` | String | Yes | Importance ranking |
| `assignee` | String | Yes | Primary responsible party |
| `created_date` | ISO Date | Yes | Creation timestamp |
| `updated_date` | ISO Date | Yes | Last modification timestamp |
| `estimated_tokens` | Number | Yes | AI processing estimate |
| `actual_tokens` | Number | Yes | Actual AI tokens consumed |
| `sync_status` | String | Yes | External synchronization state |
| `state_metadata` | Object | Yes | State transition tracking and automation |

### Relationship Fields

| Field | Type | Description |
|-------|------|-------------|
| `project_id` | String | Parent project identifier (PRJ-XXXX) |
| `epic_id` | String | Parent epic identifier (EP-XXXX) |
| `issue_id` | String | Parent issue identifier (ISS-XXXX) |
| `related_issues` | Array | Related issue identifiers |
| `related_tasks` | Array | Related task identifiers |
| `related_projects` | Array | Related project identifiers |
| `dependencies` | Array | Dependency identifiers |
| `blocked_by` | Array | Blocking item identifiers |
| `blocks` | Array | Dependent item identifiers |

### State Metadata Fields

| Field | Type | Description |
|-------|------|-------------|
| `state_metadata.transitioned_at` | ISO Date | Timestamp of last state transition |
| `state_metadata.transitioned_by` | String | User who triggered the state change |
| `state_metadata.previous_state` | String | Previous state for rollback capability |
| `state_metadata.automation_eligible` | Boolean | Whether ticket can be auto-transitioned |
| `state_metadata.assignee_on_transition` | String | Auto-assignee when state changes |
| `state_metadata.notifications_sent` | Array | Tracking of notifications sent for state |

### AI Context Fields

| Field | Type | Description |
|-------|------|-------------|
| `ai_context` | Array | AI context category tags |
| `completion_percentage` | Number | Progress percentage (0-100) |
| `estimated_tokens` | Number | AI token usage estimate |
| `actual_tokens` | Number | Actual AI tokens consumed |

### Project Specific Fields

| Field | Type | Description |
|-------|------|-------------|
| `name` | String | Project display name |
| `git_origin` | String | Git repository URL |
| `git_branch` | String | Default branch name |
| `repository_url` | String | Git repository URL |
| `clone_url` | String | Git clone URL |
| `default_branch` | String | Default git branch |
| `languages` | Array | Programming languages used |
| `framework` | String | Framework or technology stack |
| `deployment_url` | String | Production deployment URL |
| `documentation_url` | String | Documentation URL |
| `team_members` | Array | Team member identifiers |
| `license` | String | Project license |

### Pull Request Specific Fields

| Field | Type | Description |
|-------|------|-------------|
| `branch_name` | String | Git branch reference |
| `files_changed` | Array | Modified file list |
| `review_status` | String | Code review state |

## Data Types and Constraints

### Status Values (DEPRECATED - Use State Field)

**Note**: The `status` field is deprecated in favor of the unified `state` field. For backward compatibility, existing `status` values are automatically mapped to `state` values.

| Status | Description | Applies To | Maps to State |
|--------|-------------|------------|---------------|
| `planning` | Initial state, requirements gathering | All types | `open` |
| `active` | Currently being worked on | All types | `in_progress` |
| `blocked` | Cannot proceed due to dependencies | All types | `blocked` |
| `done` | Completed successfully | All types | `done` |
| `draft` | Initial code state | Pull Requests | `open` |
| `open` | Ready for review | Pull Requests | `ready_for_review` |
| `review` | Under active review | Pull Requests | `in_review` |
| `approved` | Review approved | Pull Requests | `ready_for_deployment` |
| `merged` | Code merged to main branch | Pull Requests | `done` |

### State Values (UNIFIED STATE-RESOLUTION MODEL)

**The unified `state` field replaces separate `status` and `resolution` tracking with a single, comprehensive state management system.**

#### Core States (All Ticket Types)

| State | Description | Applies To | Automation Triggers |
|-------|-------------|------------|-------------------|
| `open` | Ready to begin work, all prerequisites met | All types | Auto-assign based on priority/capacity |
| `in_progress` | Currently being actively worked on | All types | Start time tracking, notify stakeholders |
| `blocked` | Cannot proceed due to external dependencies | All types | Escalation notifications, dependency tracking |
| `ready_for_engineering` | Requirements complete, ready for implementation | Issues, Tasks | Auto-assign to development team |
| `ready_for_qa` | Implementation complete, ready for testing | Issues, Tasks, PRs | Auto-assign to QA team, trigger test suite |
| `ready_for_deployment` | QA approved, ready for production deployment | Issues, Tasks, PRs | Trigger deployment pipeline |
| `won't_do` | Deliberately not implementing (not a failure) | All types | Archive, remove from active backlogs |
| `done` | Successfully completed and verified | All types | Close, update metrics, trigger notifications |

#### Workflow-Specific States

| State | Description | Applies To | Automation Triggers |
|-------|-------------|------------|-------------------|
| `ready_for_review` | Code complete, ready for peer review | PRs | Auto-assign reviewers, trigger review tools |
| `in_review` | Under active code review | PRs | Track review time, remind reviewers |
| `review_approved` | Code review passed, ready for merge | PRs | Auto-merge if conditions met |
| `planning` | Requirements gathering and design phase | Epics, Issues | Schedule planning meetings |
| `on_hold` | Temporarily paused, can be resumed | All types | Pause tracking, schedule review date |

#### Resolution States (Terminal States)

These states represent final outcomes and should not transition to other states:

| State | Description | Context | Metrics Impact |
|-------|-------------|---------|----------------|
| `done` | Successfully completed all acceptance criteria | Positive completion | Count toward velocity/completion |
| `won't_do` | Deliberately not pursuing (scope change, priority shift) | Planned cancellation | Count as scope management |
| `duplicate` | Identified as duplicate of existing work | Process optimization | Count toward backlog hygiene |
| `obsolete` | No longer relevant due to external changes | External factors | Count as environmental change |

#### State Transition Rules

**Valid State Transitions** (to prevent invalid state changes):

```
Core Workflow States:
open → in_progress → ready_for_qa → ready_for_deployment → done
  ↓       ↓             ↓                ↓
blocked   blocked       blocked          blocked
  ↓       ↓             ↓                ↓
open    open          open             open

Resolution States (Terminal):
Any state → won't_do, duplicate, obsolete (no further transitions)

Special Workflow States:
ready_for_engineering → in_progress (when assigned to developer)
ready_for_review → in_review → review_approved → ready_for_deployment
planning → open (when requirements complete)
on_hold → previous_state (when resumed)
```

**State Validation Rules**:
- Terminal states (`done`, `won't_do`, `duplicate`, `obsolete`) cannot transition to other states
- `blocked` state requires `blocked_by` field to be populated
- Workflow-specific states only apply to appropriate ticket types
- State transitions must include `state_metadata` updates

#### Backward Compatibility Mapping

**Automatic Status-to-State Migration**:

```yaml
# Migration mapping for existing tickets
status_migration_map:
  planning: open
  active: in_progress
  blocked: blocked
  done: done
  # PR-specific mappings
  draft: open
  open: ready_for_review
  review: in_review
  approved: ready_for_deployment
  merged: done
  # Legacy mappings
  todo: open
  in_progress: in_progress
  completed: done
  cancelled: won't_do
```

**Implementation Strategy**:
1. **Phase 1**: Add `state` field to all schemas (keep `status` for compatibility)
2. **Phase 2**: Implement automatic migration logic in CLI tools
3. **Phase 3**: Update templates to use `state` field as primary
4. **Phase 4**: Mark `status` field as deprecated in documentation
5. **Phase 5**: Eventually remove `status` field in future major version

### Priority Values

| Priority | Description | Use Case |
|----------|-------------|----------|
| `critical` | Immediate attention required | Blocking issues |
| `high` | Important for current milestone | Core features |
| `medium` | Standard priority | Regular development |
| `low` | Nice to have | Enhancement features |

### Sync Status Values

| Status | Description |
|--------|-------------|
| `local` | Only exists locally |
| `synced` | Synchronized with external system |
| `conflict` | Synchronization conflict detected |

### AI Context Categories

| Category | Description |
|----------|-------------|
| `context/requirements` | Functional requirements and specifications |
| `context/constraints` | Technical and business constraints |
| `context/assumptions` | Project assumptions and dependencies |
| `context/dependencies` | External dependencies and integrations |

## File Structure

### Single-Project Directory Organization

```
tasks/
├── epics/                    # Epic files
│   ├── EP-0001-epic-name.md
│   ├── EP-0002-epic-name.md
│   └── ...
├── issues/                   # Issue files
│   ├── ISS-0001-issue-name.md
│   ├── ISS-0002-issue-name.md
│   └── ...
├── tasks/                    # Task files
│   ├── TSK-0001-task-name.md
│   ├── TSK-0002-task-name.md
│   └── ...
├── prs/                      # Pull Request files
│   ├── PR-0001-pr-name.md
│   ├── PR-0002-pr-name.md
│   └── ...
└── templates/               # Template files
    ├── epic-default.yaml
    ├── issue-default.yaml
    └── task-default.yaml
```

### Multi-Project Directory Organization

```
projects/
├── projects/                 # Project files
│   ├── PRJ-0001-project-name.md
│   ├── PRJ-0002-project-name.md
│   └── ...
├── epics/                    # Epic files
│   ├── EP-0001-epic-name.md
│   ├── EP-0002-epic-name.md
│   └── ...
├── issues/                   # Issue files
│   ├── ISS-0001-issue-name.md
│   ├── ISS-0002-issue-name.md
│   └── ...
├── tasks/                    # Task files
│   ├── TSK-0001-task-name.md
│   ├── TSK-0002-task-name.md
│   └── ...
├── prs/                      # Pull Request files
│   ├── PR-0001-pr-name.md
│   ├── PR-0002-pr-name.md
│   └── ...
└── templates/               # Template files
    ├── project-default.yaml
    ├── epic-default.yaml
    ├── issue-default.yaml
    └── task-default.yaml
```

### Naming Convention

**Files**: `{TYPE}-{NUMBER}-{kebab-case-title}.md`
- Type prefixes: `PRJ`, `EP`, `ISS`, `TSK`, `PR`
- Zero-padded numbers: `0001`, `0002`, etc.
- Kebab-case titles: lowercase with hyphens

**Examples**:
- `PRJ-0001-ai-trackdown-system.md`
- `EP-0001-user-authentication-system.md`
- `ISS-0042-implement-login-form.md`
- `TSK-0123-create-database-schema.md`
- `PR-0001-add-user-validation.md`

**Identifiers**: `{TYPE}-{ZERO_PADDED_NUMBER}`
- Project: `PRJ-0001`
- Epic: `EP-0001`
- Issue: `ISS-0001`
- Task: `TSK-0001`
- Pull Request: `PR-0001`

## Data Format

### File Structure

Each ticket file consists of:
1. **YAML Frontmatter**: Structured metadata
2. **Markdown Content**: Human-readable description

### YAML Frontmatter Format

```yaml
---
# Required fields (all ticket types)
{type}_id: {ID}
title: "Title"
description: "Description"
state: {state}                      # Unified state field
status: {status}                    # DEPRECATED: Use state field
priority: {priority}
assignee: {username}
created_date: {ISO_timestamp}
updated_date: {ISO_timestamp}
estimated_tokens: {number}
actual_tokens: {number}
ai_context: [{context_categories}]
sync_status: {sync_status}

# State metadata (required)
state_metadata:
  transitioned_at: {ISO_timestamp}
  transitioned_by: {username}
  previous_state: {previous_state}
  automation_eligible: {boolean}
  assignee_on_transition: {username}
  notifications_sent: [{usernames}]

# Relationship fields (as applicable)
epic_id: {epic_id}
issue_id: {issue_id}
related_issues: [{issue_ids}]
related_tasks: [{task_ids}]
dependencies: [{dependency_ids}]
blocked_by: [{blocking_ids}]
blocks: [{dependent_ids}]

# Progress tracking
completion_percentage: {0-100}

# Type-specific fields
# ... (varies by ticket type)
---
```

### Markdown Content Format

```markdown
# {Type}: {Title}

## Description
{Detailed description}

## {Type-specific sections}
{Varies by ticket type}

## Notes
{Additional context and considerations}
```

## Project Management Guide

### Usage Mode Selection

**Single-Project Mode**:
- Use when managing a single repository or application
- Project metadata stored in `.ai-trackdown/config.yaml`
- All tickets implicitly belong to the project
- No `project_id` field required in tickets
- Simpler directory structure and workflows

**Multi-Project Mode**:
- Use when managing multiple repositories or applications
- Each project has explicit PRJ-XXXX identifier
- All tickets include `project_id` field for association
- Supports cross-project dependencies and relationships
- Hierarchical project organization with centralized management

### Project Entity Management

**Project Creation**:
```yaml
project_id: PRJ-0001
type: project
name: "AI-TRACKDOWN"
title: "AI-TRACKDOWN Project Management System"
description: "Hierarchical ticket management system for AI-driven development workflows"
git_origin: "https://github.com/user/ai-trackdown.git"
git_branch: "main"
team_members: ["@maintainer", "@contributor1"]
languages: ["javascript", "json", "markdown"]
framework: "Node.js CLI"
```

**Project Relationships**:
- `related_projects`: List of related project identifiers
- `dependencies`: Cross-project dependencies
- `blocked_by`: Projects blocking this project
- `blocks`: Projects blocked by this project

### Git Integration Workflows

**Repository Coordination**:
- `git_origin`: Primary git repository URL
- `clone_url`: SSH or HTTPS clone URL
- `default_branch`: Main development branch
- `repository_url`: Public repository URL

**Deployment Integration**:
- `deployment_url`: Production deployment URL
- `documentation_url`: Project documentation URL
- Integration with CI/CD pipelines through git hooks

### Team Coordination

**Team Member Management**:
- `assignee`: Primary project owner
- `team_members`: Array of team member identifiers
- Cross-project team member assignments
- Role-based access control through assignee fields

**Communication Integration**:
- GitHub integration for issue tracking
- Jira integration for enterprise workflows
- Linear integration for modern development teams
- Slack/Discord notifications through webhooks

### Cross-Project Dependencies

**Dependency Types**:
- **Technical Dependencies**: Shared libraries, APIs, services
- **Resource Dependencies**: Team members, infrastructure, tools
- **Timeline Dependencies**: Milestone alignment, release coordination
- **Business Dependencies**: Feature alignment, strategy coordination

**Tracking Methods**:
- `blocked_by`: Explicit blocking relationships
- `blocks`: Items blocked by this project
- `related_projects`: Loose coupling relationships
- `dependencies`: Formal dependency declarations

## Migration Strategy for Unified State-Resolution Model

### Phase 1: Schema Enhancement (Immediate)
**Timeline**: 1-2 weeks
**Scope**: Schema and template updates

1. **Update Schema Documentation**
   - ✅ Add unified `state` field definition
   - ✅ Mark `status` field as deprecated
   - ✅ Document state transition rules
   - ✅ Create backward compatibility mapping

2. **Update Templates**
   - ✅ Add `state` field to all templates
   - ✅ Add `state_metadata` structure
   - ✅ Keep `status` field for compatibility
   - ✅ Update template documentation

### Phase 2: CLI Implementation (2-3 weeks)
**Timeline**: Following Phase 1
**Scope**: Core tool updates

1. **CLI Tool Updates**
   - [ ] Implement state field parsing and validation
   - [ ] Add backward compatibility layer for status field
   - [ ] Implement automatic migration logic
   - [ ] Add state transition validation
   - [ ] Update CLI commands to use state field

2. **Validation Enhancement**
   - [ ] Update JSON schemas to include state field
   - [ ] Add state transition validation rules
   - [ ] Implement migration warning system
   - [ ] Add state metadata validation

### Phase 3: Migration Utilities (1 week)
**Timeline**: Parallel with Phase 2
**Scope**: Migration tools and utilities

1. **Migration Tools**
   - [ ] Create migration script for existing tickets
   - [ ] Implement status-to-state mapping utility
   - [ ] Add validation tools for migrated tickets
   - [ ] Create rollback utilities for safety

2. **User Communication**
   - [ ] Create migration guide documentation
   - [ ] Add deprecation warnings to CLI
   - [ ] Provide migration timeline communication
   - [ ] Create troubleshooting guide

### Phase 4: Gradual Rollout (2-4 weeks)
**Timeline**: Following Phase 2-3
**Scope**: User adoption and feedback

1. **Beta Testing**
   - [ ] Release beta version with both fields
   - [ ] Gather user feedback on migration
   - [ ] Test automation triggers and workflows
   - [ ] Validate performance impact

2. **Production Migration**
   - [ ] Release production version with migration support
   - [ ] Monitor migration adoption rates
   - [ ] Provide user support during transition
   - [ ] Address migration issues and edge cases

### Phase 5: Deprecation and Cleanup (Future)
**Timeline**: 6 months after Phase 4
**Scope**: Remove deprecated fields

1. **Status Field Removal**
   - [ ] Mark status field for removal in next major version
   - [ ] Update documentation to remove status references
   - [ ] Remove status field from templates
   - [ ] Clean up backward compatibility code

### Implementation Guidelines for Engineers

#### Core State Management

```typescript
// State field implementation
interface TicketState {
  state: 
    // Core states
    | 'open' | 'in_progress' | 'blocked' 
    | 'ready_for_engineering' | 'ready_for_qa' | 'ready_for_deployment'
    | 'won't_do' | 'done'
    // Workflow states  
    | 'ready_for_review' | 'in_review' | 'review_approved'
    | 'planning' | 'on_hold'
    // Resolution states
    | 'duplicate' | 'obsolete';
  
  // Backward compatibility (deprecated)
  status?: string;
  
  // State metadata
  state_metadata: {
    transitioned_at: string;
    transitioned_by: string;
    previous_state: string | null;
    automation_eligible: boolean;
    assignee_on_transition: string | null;
    notifications_sent: string[];
  };
}
```

#### Migration Logic

```typescript
// Automatic status-to-state migration
const statusToStateMap = {
  'planning': 'open',
  'active': 'in_progress',
  'blocked': 'blocked',
  'done': 'done',
  // PR-specific
  'draft': 'open',
  'open': 'ready_for_review',
  'review': 'in_review',
  'approved': 'ready_for_deployment',
  'merged': 'done',
  // Legacy
  'todo': 'open',
  'in_progress': 'in_progress',
  'completed': 'done',
  'cancelled': 'won't_do'
};

function migrateTicket(ticket: any): any {
  if (ticket.status && !ticket.state) {
    ticket.state = statusToStateMap[ticket.status] || 'open';
    ticket.state_metadata = {
      transitioned_at: new Date().toISOString(),
      transitioned_by: 'migration-tool',
      previous_state: null,
      automation_eligible: true,
      assignee_on_transition: null,
      notifications_sent: []
    };
  }
  return ticket;
}
```

#### State Transition Validation

```typescript
// Valid state transitions
const validTransitions = {
  'open': ['in_progress', 'blocked', 'won't_do', 'duplicate', 'obsolete'],
  'in_progress': ['ready_for_qa', 'blocked', 'won't_do', 'done'],
  'ready_for_qa': ['ready_for_deployment', 'in_progress', 'blocked'],
  'ready_for_deployment': ['done', 'blocked'],
  'blocked': ['open', 'in_progress', 'ready_for_qa', 'ready_for_deployment'],
  // Terminal states
  'done': [],
  'won't_do': [],
  'duplicate': [],
  'obsolete': []
};

function validateStateTransition(currentState: string, newState: string): boolean {
  return validTransitions[currentState]?.includes(newState) || false;
}
```

---

**Schema Version**: 4.4.0  
**Last Updated**: 2025-07-14  
**Status**: Enhanced with Unified State-Resolution Model  
**Migration Status**: Phase 1 Complete - Schema Design