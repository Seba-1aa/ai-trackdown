# ai-trackdown Templates

This directory contains comprehensive markdown templates for implementing ai-trackdown, a lightweight, git-native task management system designed for human-AI collaboration.

## Overview

ai-trackdown is a pure markdown-based methodology that provides:

**IMPORTANT**: All templates and examples in this directory comply with the AI-Trackdown schema specification. See [SCHEMA.md](../SCHEMA.md) for complete field definitions and validation rules.

### Key Features
- **Text-First Approach**: All data stored as human-readable markdown files
- **Git-Native Integration**: Leverages git's distributed nature and version control
- **AI-Optimized Structure**: Designed for minimal token consumption and maximum context efficiency
- **Tool-Agnostic Workflow**: Works with any text editor, IDE, or command-line tools
- **llms.txt Standard**: Native support for AI discoverability and context management

## Template Files

### Core Templates
- **`project-template.md`** - Template for complete project information and setup
- **`epic-template.md`** - Template for high-level project initiatives
- **`issue-template.md`** - Template for development issues and user stories
- **`task-template.md`** - Template for granular implementation tasks
- **`AI-TRACKDOWN-template.md`** - Project overview dashboard template

### Documentation Templates
- **`directory-structure.md`** - Complete guide to organizing ai-trackdown projects
- **`llms-txt-examples.md`** - Templates for AI-discoverable project indexes
- **`manual-workflows.md`** - Step-by-step processes for task management

## Quick Start

### 1. Set Up Project Structure
```bash
mkdir -p my-project/{.ai-trackdown,tasks/{epics,issues,tasks},docs,templates}
cd my-project
```

### 2. Copy Templates
```bash
# Copy all templates to your project
cp /path/to/ai-trackdown/templates/* templates/

# Create project information file (new in v4.3.0)
cp templates/project-template.md PRJ-0001-project-info.md

# Create initial project dashboard
cp templates/AI-TRACKDOWN-template.md AI-TRACKDOWN.md
```

### 3. Create Your First Epic
```bash
# Copy and customize epic template
cp templates/epic-template.md tasks/epics/EP-0001-user-authentication.md

# Edit the file to add your specific requirements
vim tasks/epics/EP-0001-user-authentication.md
```

### 4. Create Initial Configuration
```bash
# Create basic configuration
cat > .ai-trackdown/config.yaml << EOF
version: 1
project:
  name: "My Project"
  id_prefix: "PROJ"
EOF
```

### 5. Initialize AI Index
```bash
# Create basic llms.txt for AI discovery
cp templates/llms-txt-examples.md .ai-trackdown/llms.txt
# Edit to match your project
```

## File Naming Conventions

### Task Hierarchy
- **Projects**: `PRJ-XXXX-descriptive-name.md` (complete project information)
- **Epics**: `EP-XXXX-descriptive-name.md` (major features, 1-6 months)
- **Issues**: `ISS-XXXX-descriptive-name.md` (user stories, 1-2 sprints)
- **Tasks**: `TSK-XXXX-descriptive-name.md` (implementation work, hours-days)

### ID Format
- Use zero-padded numbers: `PRJ-0001`, `EP-0001`, `ISS-0042`, `TSK-0123`
- Descriptive names in kebab-case: `user-authentication-system`
- Include key domain concepts: `payment-integration`, `api-redesign`

## Template Structure

### Frontmatter (YAML)
All templates use YAML frontmatter for metadata following the schema defined in [SCHEMA.md](../SCHEMA.md):
```yaml
---
# Optional project association (new in v4.3.0)
project_id: PRJ-0001  # Omit for single-project setups

task_id: TSK-0001
type: task
issue_id: ISS-0001
epic_id: EP-0001
title: Task Title
description: "Clear task description"
status: planning
priority: medium
assignee: username
created_date: 2025-07-07T10:00:00Z
updated_date: 2025-07-07T10:00:00Z
estimated_tokens: 100
actual_tokens: 0
ai_context:
  - context/requirements
  - context/constraints
sync_status: local
labels: [frontend, authentication]
blocked_by: []
blocks: []
---
```

### Content Sections
- **Description**: Clear problem statement and objectives
- **Acceptance Criteria**: Measurable completion requirements
- **Technical Notes**: Implementation guidance and constraints
- **AI Context**: Information for AI agents working on the task
- **Activity Log**: Timeline of work and decisions
- **Related Items**: Dependencies and relationships

## AI Integration Features

### Token Tracking
All templates include comprehensive token usage tracking:
- **Total Usage**: Cumulative tokens across all AI interactions
- **Agent Breakdown**: Usage by specific AI agent (Claude, GPT-4, etc.)
- **Purpose Tracking**: What the tokens were used for
- **Budget Management**: Epic-level token budgets and alerts

### Context Optimization
Special AI context sections provide focused information:
```markdown
<!-- AI_CONTEXT_START -->
This task implements user authentication for the e-commerce platform.
Key files: src/auth/, src/components/LoginForm.tsx
Dependencies: JWT library, Redis for sessions
Security considerations: OWASP guidelines, rate limiting
<!-- AI_CONTEXT_END -->
```

### llms.txt Integration
AI-discoverable project indexes:
- **Basic Index** (`.ai-trackdown/llms.txt`): Project overview for AI agents
- **Full Context** (`docs/llms-full.txt`): Comprehensive project information
- **Auto-Generation Ready**: Structured for automated index creation

## Workflow Integration

### Git Integration
- **Branch Naming**: `feature/ISSUE-001-login-flow`
- **Commit Messages**: Reference task IDs for automatic status updates
- **Status Tracking**: Task completion tied to git workflow

### External System Sync
Templates include sync metadata for:
- **GitHub Issues**: Bidirectional synchronization
- **Jira**: Enterprise project management integration
- **Linear**: Modern team collaboration

## Customization Guidelines

### Project-Specific Adaptations
1. **Modify ID Prefixes**: Change `EPIC`/`ISSUE`/`TASK` to project-specific prefixes
2. **Add Custom Fields**: Extend frontmatter for project needs
3. **Customize Sections**: Add or remove content sections as needed
4. **Label Taxonomy**: Define project-specific label categories

### Team Adaptations
1. **Estimation Methods**: Story points, T-shirt sizes, hours
2. **Status Workflows**: Define team-specific status transitions
3. **Review Processes**: Add team-specific review and approval sections
4. **Communication**: Integrate with team chat and notification systems

## Best Practices

### File Organization
- Keep related tasks grouped by epic
- Use consistent naming conventions
- Maintain clear parent-child relationships
- Archive completed items regularly

### Content Quality
- Write clear, actionable acceptance criteria
- Maintain current AI context sections
- Log all AI interactions with token usage
- Update activity logs regularly

### Token Management
- Set realistic epic-level budgets
- Monitor usage against budgets weekly
- Log purpose for all AI interactions
- Focus AI usage on high-impact activities

### Relationship Management
- Maintain bidirectional references
- Update dependencies when items complete
- Use consistent linking formats
- Validate references regularly

## Advanced Features

### Multi-Project Support
All templates now support both single-project and multi-project environments through the optional `project_id` field:

**Single Project Mode**:
```yaml
# Remove or set to null in template frontmatter
project_id: null  # Or omit entirely
```

**Multi-Project Mode**:
```yaml
# Specify parent project ID
project_id: PRJ-0001
```

**Workspace Structure**:
```
workspace/
├── project-a/           # Full ai-trackdown structure
│   ├── tasks/
│   │   ├── epics/      # project_id: PRJ-0001
│   │   ├── issues/     # project_id: PRJ-0001  
│   │   └── tasks/      # project_id: PRJ-0001
│   └── PRJ-0001-project-info.md
├── project-b/           # Full ai-trackdown structure
│   ├── tasks/
│   │   ├── epics/      # project_id: PRJ-0002
│   │   ├── issues/     # project_id: PRJ-0002
│   │   └── tasks/      # project_id: PRJ-0002
│   └── PRJ-0002-project-info.md
└── shared/
    ├── templates/       # Shared templates
    └── common-docs/     # Cross-project documentation
```

### Scaling Strategies
- **Monthly Archiving**: Move completed items to date-based folders
- **Component Organization**: Organize by system components
- **Team Boundaries**: Separate team-specific work areas
- **Epic Grouping**: Group related epics into programs

### Quality Assurance
- **Frontmatter Validation**: Ensure required fields are present
- **ID Uniqueness**: Prevent duplicate task identifiers
- **Reference Validation**: Check for broken links
- **Content Completeness**: Verify acceptance criteria quality

## Example Implementations

### Startup MVP Project
```
tasks/
├── epics/
│   ├── EP-0001-user-onboarding.md
│   ├── EP-0002-core-features.md
│   └── EP-0003-launch-preparation.md
├── issues/
│   ├── ISSUE-001-user-registration.md
│   ├── ISSUE-002-feature-a-implementation.md
│   └── ISSUE-003-analytics-integration.md
└── tasks/
    ├── TASK-001-signup-form.md
    ├── TASK-002-email-verification.md
    └── TASK-003-onboarding-flow.md
```

### Enterprise System Integration
```
tasks/
├── epics/
│   ├── EP-0001-legacy-system-integration.md
│   ├── EP-0002-security-compliance.md
│   └── EP-0003-performance-optimization.md
├── frontend/
│   ├── issues/
│   └── tasks/
├── backend/
│   ├── issues/
│   └── tasks/
└── infrastructure/
    ├── issues/
    └── tasks/
```

### Open Source Library
```
tasks/
├── epics/
│   ├── EP-0001-core-api-design.md
│   ├── EP-0002-documentation-system.md
│   └── EP-0003-community-tools.md
├── issues/
│   ├── ISSUE-001-api-interface.md
│   ├── ISSUE-002-getting-started-guide.md
│   └── ISSUE-003-contribution-workflow.md
└── tasks/
    ├── TASK-001-function-signatures.md
    ├── TASK-002-readme-tutorial.md
    └── TASK-003-pr-templates.md
```

## Getting Help

### Documentation References
1. **Design Document**: `/docs/ai-tasktrack-design-doc.md` - Complete system architecture
2. **Directory Structure**: `templates/directory-structure.md` - Organization guide
3. **Manual Workflows**: `templates/manual-workflows.md` - Step-by-step processes
4. **llms.txt Examples**: `templates/llms-txt-examples.md` - AI integration patterns

### Common Patterns
- **Task Dependencies**: Use "blocks" and "blocked_by" fields for task ordering
- **Epic Progress**: Track completion percentage in epic files
- **Status Transitions**: `planning → active → blocked → done`
- **Token Budgets**: Set epic-level budgets and track usage

### Troubleshooting
- **Broken References**: Use grep to find and fix orphaned references
- **Duplicate IDs**: Search for duplicate ID values across files
- **Missing Context**: Ensure all AI interactions are logged
- **Stale Status**: Regular review and update of task statuses

---

**ai-trackdown Templates provide a complete foundation for markdown-based project management with native AI integration. Start with the basic templates and customize them to match your team's workflow and project requirements.**
