---
issue_id: ISS-0003
type: issue
epic_id: EP-0001
title: "Extend schema to support multi-project system with project entities"
description: "Add optional project support to ai-trackdown schema to enable both single-project and multi-project usage modes. Projects should include git origin and metadata, with optional references in all tickets."
status: completed
priority: high
assignee: masa
created_date: 2025-07-09T21:00:00Z
updated_date: 2025-07-09T21:30:00Z
estimated_tokens: 600
actual_tokens: 580
ai_context:
  - context/requirements
  - context/constraints
  - context/assumptions
  - context/dependencies
sync_status: local
labels: ["schema", "projects", "multi-project", "enhancement"]
related_tasks: []
related_issues: []
completion_percentage: 100
dependencies: []
blocked_by: []
blocks: []
---

# Issue: Extend schema to support multi-project system with project entities

## Description

Extend the AI-TRACKDOWN schema to support both single-project and multi-project usage modes by adding optional project entities. This enhancement will allow users to manage multiple git projects within a single ai-trackdown instance while maintaining backward compatibility.

## Requirements

### Project Entity Definition
- **Project ID Format**: `PRJ-XXXX` (e.g., `PRJ-0001`)
- **Project Scope**: Equivalent to a git repository/project
- **Usage Modes**: 
  - **Single Project**: Default mode, no project references needed
  - **Multi-Project**: Projects required when tasks/ in parent directory

### Project Schema Fields
- `project_id`: Unique identifier (PRJ-XXXX format)
- `type`: "project" constant
- `name`: Project display name
- `description`: Project description
- `git_origin`: Git repository URL
- `git_branch`: Default branch (e.g., "main", "master")
- `status`: Project status (active, archived, maintenance)
- `priority`: Project priority level
- `assignee`: Project owner/maintainer
- `created_date`: Project creation timestamp
- `updated_date`: Last update timestamp
- `estimated_tokens`: Token budget for project
- `actual_tokens`: Token usage tracking
- `ai_context`: AI context categories
- `sync_status`: Sync status with external systems
- `labels`: Project tags/categories
- `related_projects`: Related project references
- `dependencies`: Project dependencies
- `blocked_by`: Blocking projects
- `blocks`: Projects blocked by this one

### Project Metadata Fields
- `repository_url`: Git repository URL
- `clone_url`: Git clone URL
- `default_branch`: Default git branch
- `languages`: Programming languages used
- `framework`: Framework/stack information
- `deployment_url`: Production deployment URL
- `documentation_url`: Project documentation URL
- `team_members`: Team member list
- `license`: Project license

### Ticket Schema Extensions
- `project_id`: Optional project reference (PRJ-XXXX)
- **Default Behavior**: If no project_id specified, assumes current/default project
- **Multi-Project Mode**: project_id becomes required when tasks/ in parent directory
- **Single-Project Mode**: project_id remains optional

## Directory Structure Options

### Single-Project Mode (Current)
```
my-project/
├── tasks/
│   ├── epics/
│   ├── issues/
│   └── tasks/
├── SCHEMA.md
└── AI-TRACKDOWN.json
```

### Multi-Project Mode (New)
```
workspace/
├── tasks/
│   ├── projects/
│   │   ├── PRJ-0001-web-app.md
│   │   ├── PRJ-0002-api-service.md
│   │   └── PRJ-0003-mobile-app.md
│   ├── epics/
│   ├── issues/
│   └── tasks/
├── SCHEMA.md
└── AI-TRACKDOWN.json
```

## Tasks

- [ ] Update AI-TRACKDOWN.json schema to include project entity
- [ ] Create project template (project-template.md)
- [ ] Update epic template to include optional project_id
- [ ] Update issue template to include optional project_id
- [ ] Update task template to include optional project_id
- [ ] Update PR template to include optional project_id
- [ ] Update SCHEMA.md to document project support
- [ ] Update README.md to explain single vs multi-project modes
- [ ] Create project examples in examples/ directory
- [ ] Update all existing example files to show project usage
- [ ] Create project management documentation
- [ ] Update CLI specification to include project commands

## Acceptance Criteria

- [ ] AI-TRACKDOWN.json schema validates project entities
- [ ] Project template follows schema requirements
- [ ] All ticket templates support optional project_id field
- [ ] SCHEMA.md documents project entity and usage modes
- [ ] README.md explains single vs multi-project usage
- [ ] Examples demonstrate both usage modes
- [ ] Backward compatibility maintained for single-project mode
- [ ] Multi-project mode properly validates project_id requirements
- [ ] Project metadata supports git integration

## Implementation Strategy

### Phase 1: Schema Extension
1. **Update AI-TRACKDOWN.json** to include project entity definition
2. **Create project template** with all required fields
3. **Extend ticket schemas** to support optional project_id

### Phase 2: Documentation Updates
1. **Update SCHEMA.md** to document project support
2. **Update README.md** to explain usage modes
3. **Create project management guide**

### Phase 3: Template Updates
1. **Update all ticket templates** to include project_id
2. **Create project examples** for both modes
3. **Update existing examples** to demonstrate project usage

### Phase 4: Validation
1. **Schema validation** for project entities
2. **Multi-project mode validation** logic
3. **Backward compatibility** testing

## Project Reference Examples

### Single-Project Mode (Optional)
```yaml
epic_id: EP-0001
project_id: PRJ-0001  # Optional, defaults to current project
title: "User Authentication System"
```

### Multi-Project Mode (Required)
```yaml
epic_id: EP-0001
project_id: PRJ-0001  # Required when tasks/ in parent directory
title: "User Authentication System"
```

## Git Integration Benefits

- **Repository Tracking**: Link tickets to specific git repositories
- **Branch Management**: Track default branches and deployment targets
- **Team Coordination**: Manage multiple projects with shared team
- **Token Tracking**: Budget and track AI usage per project
- **Deployment Tracking**: Link tickets to deployment URLs

## Notes

This enhancement maintains full backward compatibility while adding powerful multi-project capabilities. The optional nature of project references ensures existing single-project workflows remain unchanged while enabling sophisticated multi-project management for teams managing multiple repositories.

The project entity enables better organization, git integration, and team coordination while maintaining the simple, file-based approach that makes ai-trackdown easy to use and understand.