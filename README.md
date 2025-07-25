# AI Track Down

> **Revolutionary markdown-based task management framework for the AI development era**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Documentation](https://img.shields.io/badge/docs-framework-blue.svg)](https://github.com/ai-trackdown/ai-trackdown)

## 🚨 Why AI Track Down is the issue management system for the ai orchestrated development era

**The Problem**: Current task management systems were designed for human-only workflows. In the AI development era, we face:

- **Token Blindness**: No visibility into AI assistant costs across projects
- **Context Fragmentation**: AI agents lose context between sessions, requiring expensive re-explanations
- **Integration Overhead**: Complex APIs and databases that slow down development velocity
- **Vendor Lock-in**: Proprietary systems that trap your project data
- **AI Accessibility**: Traditional systems are opaque to AI agents, requiring complex integrations

**The Solution**: AI Track Down is the first task management framework designed from the ground up for human-AI collaborative development:

✅ **Native AI Context**: Built-in llms.txt support means AI agents understand your project instantly  
✅ **Token Economics**: Track and optimize AI costs at every level (task/epic/project)  
✅ **Git-Native**: Your tasks live where your code lives - no separate systems  
✅ **Zero Lock-in**: Pure markdown files you can read, edit, and migrate anywhere  
✅ **AI-First Design**: Optimized for minimal token consumption and maximum AI efficiency  

AI Track Down isn't just another task manager - it's the missing documentation framework for AI-enhanced development teams.

> **📋 Documentation Framework**: This project provides templates, examples, and documentation patterns. Working CLI tools are being developed separately.

## 🚀 Key Features

- **Multi-Project Management**: Support for both single-project and multi-project workflows with PRJ-XXXX identifiers
- **Hierarchical Structure**: Projects → Epics → Issues → Tasks → Pull Requests with full relationship tracking
- **Pure Markdown Templates**: All templates and examples use human-readable markdown with GitHub Flavored Markdown (GFM)
- **Native llms.txt Support**: Templates for generating llms.txt files for AI discoverability and context
- **Git-Native Structure**: File organization leverages git's distributed nature with state management patterns
- **Token Usage Tracking**: Template structures for tracking AI token usage at task/epic/project levels
- **Integration Patterns**: Documentation patterns for GitHub Issues, Jira, and Linear integration
- **Zero Dependencies**: Template system works offline with no external dependencies
- **AI-Optimized**: Structured for minimal token consumption and maximum AI efficiency
- **Team Coordination**: Project-level team member management and cross-project dependency tracking

## 📋 Ticketing Schema

**IMPORTANT**: AI-Trackdown uses a structured ticketing schema to ensure consistency and reliability across all project management activities.

### Schema Documentation

- **[SCHEMA.md](SCHEMA.md)** - Complete ticketing schema specification with field definitions, data types, and validation rules
- **[AI-TRACKDOWN.json](AI-TRACKDOWN.json)** - JSON Schema file for programmatic validation and tooling integration

### Key Schema Features

- **Hierarchical Structure**: Projects → Epics → Issues → Tasks → Pull Requests
- **Multi-Project Support**: Optional `project_id` field for cross-project management
- **Standardized Field Names**: `project_id`, `epic_id`, `issue_id`, `task_id`, `assignee`, `created_date`, `updated_date`
- **Modern ID Formats**: `PRJ-0001`, `EP-0001`, `ISS-0001`, `TSK-0001`, `PR-0001`
- **Required Fields**: All tickets must include `description`, `estimated_tokens`, `actual_tokens`, `ai_context`, `sync_status`
- **Validation Ready**: Schema v4.3.0 with comprehensive validation rules including project support
- **Git Integration**: Built-in git repository metadata for project-level coordination

### Schema Compliance

All templates, examples, and documentation in this project follow the schema specification. When creating new tickets or customizing templates, ensure compliance with the schema requirements defined in [SCHEMA.md](SCHEMA.md).

## 📦 Getting Started

### Clone the Framework

```bash
git clone https://github.com/ai-trackdown/ai-trackdown.git
cd ai-trackdown
```

### Choose Your Usage Mode

**Single-Project Mode** (recommended for individual projects):
```bash
# Copy the single-project template structure
cp -r templates/single-project/ your-project/
cd your-project
```

**Multi-Project Mode** (recommended for organizations):
```bash
# Copy the multi-project template structure
cp -r templates/multi-project/ your-organization/
cd your-organization
```

### Project Setup

**For Single-Project Mode**:
- Project information stored in `.ai-trackdown/config.yaml`
- All tickets implicitly belong to the project
- Focus on epic/issue/task organization

**For Multi-Project Mode**:
- Each project gets a PRJ-XXXX identifier
- Project-specific metadata includes git repos and team members
- Cross-project dependencies and coordination

### Framework Structure

This framework provides documentation patterns and templates - no installation required.

## 🤖 AI Agent Setup

### For AI Agents Working with This Framework

If you're an AI agent helping with AI Track Down implementation, read the complete setup instructions in:

**[AI-AGENT-PROMPT.md](AI-AGENT-PROMPT.md)** - Complete system prompt and workflow guide

This file contains:
- Complete framework context and structure
- Task creation and updating workflows  
- Token tracking guidelines and best practices
- AI-optimized templates and patterns
- Integration with development workflows

**Quick AI Agent Workflow:**
1. Read `AI-AGENT-PROMPT.md` for complete context
2. Copy templates from `/templates/` directory for new tasks
3. Update task status and token usage in YAML frontmatter
4. Use AI context markers for technical implementation details
5. Update project dashboard in `AI-TRACKDOWN.md`

This framework is optimized for AI-human collaboration with built-in token tracking and context management.

## 🏁 Quick Start

### 1. Choose Your Setup Mode

**Single-Project Setup**:
```bash
# Copy single-project templates
cp -r templates/single-project/ your-project/
cd your-project
```

**Multi-Project Setup**:
```bash
# Copy multi-project templates
cp -r templates/multi-project/ your-organization/
cd your-organization
```

### 2. Configure Your Environment

**Single-Project Mode**:
```bash
# Edit project configuration
vim .ai-trackdown/config.yaml
# Set project name, git repository, team members
```

**Multi-Project Mode**:
```bash
# Create your first project
cp templates/project-template.md projects/PRJ-0001-my-project.md
# Edit with project details, git repo, team info
```

### 3. Create Your First Epic

**Single-Project Mode**:
```bash
# Use the epic template
cp templates/epic-template.md tickets/epics/EP-0001-user-authentication.md
# Edit with your epic details
```

**Multi-Project Mode**:
```bash
# Use the epic template with project reference
cp templates/epic-template.md epics/EP-0001-user-authentication.md
# Edit with your epic details and add project_id: PRJ-0001
```

### 4. Add Issues to the Epic

```bash
# Use the issue template
cp templates/issue-template.md issues/ISS-0001-login-flow.md
# Edit with your issue details and link to EP-0001
# Add project_id: PRJ-0001 if using multi-project mode
```

### 5. Break Down Issues into Tasks

```bash
# Use the task template
cp templates/task-template.md tasks/TSK-0001-login-form.md
# Edit with your task details and link to ISS-0001
# Add project_id: PRJ-0001 if using multi-project mode
```

### 6. Track AI Token Usage

Follow the token tracking patterns in the templates to manually log AI usage.

### 7. Generate llms.txt for AI Context

Use the llms.txt template and customize for your project structure.

## 🔧 Configuration

### Basic Configuration

Use the provided `.ai-trackdown/config.yaml` template:

```yaml
version: 1
project:
  name: "My Project"
  id_prefix: "PROJ"
  
sync:
  github:
    enabled: true
    repo: "org/repo"
```

### Advanced Configuration

See [Configuration Guide](docs/configuration.md) for complete template options including:
- Integration setup patterns (GitHub, Jira, Linear)
- Token tracking configuration examples
- AI agent permission templates
- Git hooks setup guides

## 📖 Usage

### Framework Workflow

Follow these manual workflows using the provided templates:

**Single-Project Workflow**:
```bash
# Project Setup
cp -r templates/single-project/ your-project/       # Copy project structure
vim your-project/.ai-trackdown/config.yaml          # Customize configuration

# Creating Items
cp templates/epic-template.md tasks/epics/EP-XXXX.md    # Create epic
cp templates/issue-template.md tasks/issues/ISS-XXXX.md # Create issue  
cp templates/task-template.md tasks/tasks/TSK-XXXX.md    # Create task
cp templates/pr-template.md tasks/prs/PR-XXXX.md        # Create pull request
```

**Multi-Project Workflow**:
```bash
# Organization Setup
cp -r templates/multi-project/ your-organization/   # Copy organization structure
vim your-organization/.ai-trackdown/config.yaml     # Customize configuration

# Creating Projects
cp templates/project-template.md projects/PRJ-XXXX.md   # Create project

# Creating Items (with project_id references)
cp templates/epic-template.md epics/EP-XXXX.md          # Create epic
cp templates/issue-template.md issues/ISS-XXXX.md       # Create issue  
cp templates/task-template.md tasks/TSK-XXXX.md         # Create task
cp templates/pr-template.md prs/PR-XXXX.md              # Create pull request
```

**Common Operations**:
```bash
# Managing Status
# Edit YAML frontmatter in task files to update status
# Use examples/status-workflows/ for common patterns

# Token Tracking
# Follow token tracking patterns in task templates
# Use examples/token-tracking/ for reporting templates

# Integration Setup
# Follow examples/integrations/ for GitHub/Jira/Linear patterns
# Use webhook templates for bidirectional sync

# AI Context Generation
# Use templates/llms-txt/ for generating AI context files
# Follow examples/ai-integration/ for optimization patterns
```

### Directory Structure

**Single-Project Mode**:
```
project-root/
├── .ai-trackdown/
│   ├── config.yaml              # Project configuration
│   ├── sync/                    # Sync pattern templates
│   │   ├── github.json
│   │   ├── jira.json
│   │   └── linear.json
│   └── llms.txt                 # AI context template
├── tasks/
│   ├── epics/
│   │   ├── EP-0001-user-authentication.md
│   │   └── EP-0002-payment-integration.md
│   ├── issues/
│   │   ├── ISS-0001-login-flow.md
│   │   └── ISS-0002-password-reset.md
│   ├── tasks/
│   │   ├── TSK-0001-create-login-form.md
│   │   └── TSK-0002-implement-oauth.md
│   └── prs/
│       ├── PR-0001-add-auth-middleware.md
│       └── PR-0002-update-login-form.md
├── docs/
│   └── llms-full.txt            # Complete task context template
└── AI-TRACKDOWN.md                 # Project task overview template
```

**Multi-Project Mode**:
```
organization-root/
├── .ai-trackdown/
│   ├── config.yaml              # Organization configuration
│   ├── sync/                    # Sync pattern templates
│   │   ├── github.json
│   │   ├── jira.json
│   │   └── linear.json
│   └── llms.txt                 # AI context template
├── projects/
│   ├── PRJ-0001-web-app.md
│   ├── PRJ-0002-mobile-app.md
│   └── PRJ-0003-api-service.md
├── epics/
│   ├── EP-0001-user-authentication.md    # project_id: PRJ-0001
│   └── EP-0002-payment-integration.md    # project_id: PRJ-0001
├── issues/
│   ├── ISS-0001-login-flow.md           # project_id: PRJ-0001
│   └── ISS-0002-mobile-auth.md          # project_id: PRJ-0002
├── tasks/
│   ├── TSK-0001-create-login-form.md    # project_id: PRJ-0001
│   └── TSK-0002-implement-oauth.md      # project_id: PRJ-0001
├── prs/
│   ├── PR-0001-add-auth-middleware.md   # project_id: PRJ-0001
│   └── PR-0002-mobile-login.md          # project_id: PRJ-0002
├── docs/
│   └── llms-full.txt            # Complete organization context
└── AI-TRACKDOWN.md                 # Organization overview template
```

### Task File Format

Each task template follows the structured markdown format defined in [SCHEMA.md](SCHEMA.md). All templates comply with the AI-TRACKDOWN.json schema specification:

**Single-Project Mode Example**:
```markdown
---
issue_id: ISS-0001
type: issue
epic_id: EP-0001
title: Implement user login flow
description: "Create a secure login flow with email/password authentication and OAuth2 support"
status: in-progress
priority: high
assignee: johndoe
created_date: 2025-01-07T10:00:00Z
updated_date: 2025-01-07T14:30:00Z
estimated_tokens: 1500
actual_tokens: 1247
ai_context:
  - context/requirements
  - context/constraints
  - context/assumptions
sync_status: synced
labels: [authentication, frontend, priority-high]
related_tasks: []
related_issues: []
completion_percentage: 60
blocked_by: []
blocks: []
---
```

**Multi-Project Mode Example**:
```markdown
---
project_id: PRJ-0001
issue_id: ISS-0001
type: issue
epic_id: EP-0001
title: Implement user login flow
description: "Create a secure login flow with email/password authentication and OAuth2 support"
status: in-progress
priority: high
assignee: johndoe
created_date: 2025-01-07T10:00:00Z
updated_date: 2025-01-07T14:30:00Z
estimated_tokens: 1500
actual_tokens: 1247
ai_context:
  - context/requirements
  - context/constraints
  - context/assumptions
sync_status: synced
labels: [authentication, frontend, priority-high]
related_tasks: []
related_issues: []
related_projects: [PRJ-0002]  # Cross-project dependency
completion_percentage: 60
blocked_by: []
blocks: []
---

# Implement user login flow

## Description
Create a secure login flow with email/password authentication and OAuth2 support.

## Acceptance Criteria
- [ ] Email/password login form with validation
- [ ] OAuth2 integration (Google, GitHub)
- [ ] Remember me functionality
- [ ] Rate limiting on login attempts
- [x] Session management

## Technical Notes
- Use JWT for session tokens
- Implement PKCE flow for OAuth2
- Store sessions in Redis

## Token Context
<!-- AI_CONTEXT_START -->
This issue implements the authentication flow for the user management system. 
Related files: `src/auth/*`, `src/components/LoginForm.tsx`
Dependencies: Redis for session storage, JWT library
<!-- AI_CONTEXT_END -->

## Related Tasks
- Blocks: TASK-003, TASK-004
- Blocked by: ISSUE-002
- Related: ISSUE-005
```

## 🏢 Project Management

### When to Use Single vs Multi-Project Mode

**Single-Project Mode** - Choose when:
- Working on a single repository or application
- Small team (1-5 developers)
- Focused development scope
- Simple organizational structure
- Want minimal overhead and maximum simplicity

**Multi-Project Mode** - Choose when:
- Managing multiple repositories or applications
- Large team or multiple teams
- Complex organizational structure
- Need cross-project dependency tracking
- Enterprise environment with multiple stakeholders
- Want centralized project portfolio management

### Project Management Workflows

**Single-Project Setup**:
1. Initialize project with configuration in `.ai-trackdown/config.yaml`
2. Define project metadata (name, git repo, team members)
3. Create epics, issues, and tasks without project_id references
4. Leverage git integration for repository coordination
5. Use project-level token budgeting and tracking

**Multi-Project Setup**:
1. Create organization structure with central configuration
2. Define each project with PRJ-XXXX identifiers
3. Include project_id in all epics, issues, tasks, and PRs
4. Track cross-project dependencies and relationships
5. Coordinate multiple git repositories and teams
6. Use project-level resource allocation and planning

### Git Integration Benefits

- **Repository Coordination**: Direct git repository links in project metadata
- **Branch Management**: Pull request templates with branch tracking
- **Team Integration**: Git-based team member identification
- **Deployment Tracking**: Production and staging environment links
- **Documentation Links**: Automatic documentation URL references

### Cross-Project Dependencies

In multi-project mode, you can track:
- **Related Projects**: `related_projects` field for project relationships
- **Cross-Project Blocking**: Dependencies between projects using `blocked_by` and `blocks`
- **Resource Sharing**: Team members working across multiple projects
- **Technology Alignment**: Framework and technology stack coordination

### Team Coordination Features

- **Project Ownership**: Clear assignee and team member definitions
- **Role Management**: Team member roles and responsibilities
- **Communication**: Integration with GitHub, Jira, and Linear for notifications
- **Progress Tracking**: Project-level completion percentages and milestones
- **Token Budgeting**: AI usage tracking and budget allocation per project

## 🤖 AI Integration

### llms.txt Support

The framework provides llms.txt templates following the standard:

- `/llms.txt` - Project index template for quick AI context
- `/docs/llms-full.txt` - Complete project context template

### Token Tracking

Track AI token usage using the provided templates:

```bash
# Follow token tracking patterns in task templates
# Edit YAML frontmatter to log token usage:
#   token_usage:
#     total: 892
#     by_agent:
#       claude: 892

# Use examples/token-tracking/ for reporting templates
# Customize budget tracking patterns for your workflow
```

### AI Context Optimization

The framework optimizes context for AI agents through:
- Context markers in task templates
- Token budgeting patterns
- Efficient context generation templates
- Agent-specific permission examples

## 🔄 Integrations

### GitHub Issues

```bash
# Follow GitHub integration patterns in examples/integrations/github/
# Use webhook templates for bidirectional sync
# Configure .ai-trackdown/sync/github.json using provided templates
```

### Jira

```bash
# Follow Jira integration patterns in examples/integrations/jira/
# Use API mapping templates for field synchronization
# Configure .ai-trackdown/sync/jira.json using provided templates
```

### Linear

```bash
# Follow Linear integration patterns in examples/integrations/linear/
# Use GraphQL templates for API integration
# Configure .ai-trackdown/sync/linear.json using provided templates
```

## 🛠️ Framework Development

### Prerequisites

- Git for version control
- Text editor for markdown editing
- Basic understanding of YAML and markdown

### Contributing to Templates

```bash
git clone https://github.com/ai-trackdown/ai-trackdown.git
cd ai-trackdown
# Edit templates in templates/ directory
# Add examples in examples/ directory
# Update documentation as needed
```

### Template Validation

```bash
# Validate YAML frontmatter in templates
# Check markdown formatting
# Ensure example consistency
# Test template copying workflows
```

### Documentation

```bash
# Update docs/ directory with new patterns
# Add integration examples
# Maintain template documentation
```

## 📚 Comprehensive Documentation

### 🚀 Getting Started
- **[Getting Started Guide](docs/getting-started.md)** - Complete template setup tutorial with examples
- **[FAQ](docs/faq.md)** - Answers to common questions about AI Track Down's revolutionary framework approach

### 🏗️ Framework Deep Dive  
- **[Architecture Guide](docs/architecture.md)** - Framework design, AI integration patterns, and scaling strategies
- **[Template Reference](docs/template-reference.md)** - Complete template structure reference with examples
- **[Configuration Guide](docs/configuration.md)** - Advanced configuration templates and team setups

### 🔄 Platform Integration
- **[Integration Guide](docs/integrations.md)** - GitHub, Jira, Linear integration patterns with field mapping examples
- **[Best Practices](docs/best-practices.md)** - Proven strategies for AI-human collaboration workflows

### 💡 Examples and Templates
- **[Basic Setup Example](examples/basic-setup/)** - Small team starter template configuration
- **[Multi-Project Setup](examples/multi-project-setup/)** - Organization-wide project management configuration
- **[Enterprise Integration](examples/enterprise-integration/)** - Large organization template setup with multi-team coordination
- **[Sample Tasks](examples/sample-tasks/)** - Real-world epic, issue, and task template examples
- **[Project Templates](examples/project-templates/)** - Ready-to-use project configuration templates
- **[Configuration Templates](examples/configs/)** - Ready-to-use config file templates for different scenarios

### 🏢 Multi-Project Examples

**Scenario 1: Software Company Portfolio**
```yaml
# PRJ-0001: Main Web Application
name: "Customer Portal"
git_origin: "https://github.com/company/customer-portal.git"
team_members: ["@frontend-team", "@backend-team"]
languages: ["typescript", "react", "node.js"]

# PRJ-0002: Mobile Application  
name: "Mobile App"
git_origin: "https://github.com/company/mobile-app.git"
team_members: ["@mobile-team"]
languages: ["swift", "kotlin", "react-native"]

# PRJ-0003: API Gateway
name: "API Gateway"
git_origin: "https://github.com/company/api-gateway.git"
team_members: ["@backend-team", "@devops-team"]
languages: ["python", "golang", "docker"]
```

**Scenario 2: Cross-Project Dependencies**
```yaml
# Epic in PRJ-0001 depends on API changes in PRJ-0003
epic_id: EP-0001
project_id: PRJ-0001
title: "User Authentication Frontend"
blocked_by: ["ISS-0025"]  # API endpoint in PRJ-0003
related_projects: ["PRJ-0003"]
```

**Scenario 3: Shared Resources**
```yaml
# Team member working across multiple projects
team_members: ["@fullstack-dev"]  # In PRJ-0001
team_members: ["@fullstack-dev"]  # In PRJ-0002
team_members: ["@fullstack-dev"]  # In PRJ-0003
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Quick Contributing Steps

1. Fork the repository
2. Create a feature branch
3. Add or improve templates
4. Update documentation and examples
5. Submit a pull request

## 📋 Roadmap

### Phase 1: Framework Foundation ✅
- [x] Basic template structure and documentation
- [x] Git workflow patterns
- [x] Markdown template formats
- [x] Configuration templates

### Phase 2: AI Integration Templates 🚧
- [x] llms.txt template patterns
- [x] Token tracking templates
- [x] AI context marker templates
- [ ] Advanced AI optimization patterns

### Phase 3: Integration Patterns 📋
- [ ] GitHub Issues integration templates
- [ ] Jira webhook pattern templates
- [ ] Linear API integration patterns
- [ ] Conflict resolution workflow templates

### Phase 4: Tooling Development 📋
- [ ] CLI implementation (separate project)
- [ ] Web UI templates (optional)
- [ ] Analytics template patterns
- [x] Multi-project template structures

## 📄 License

MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [llms.txt standard](https://llmstxt.org/) for AI context conventions
- [GitHub Flavored Markdown](https://github.github.com/gfm/) for file format
- The open-source community for inspiration and best practices

## 💬 Support

- [GitHub Issues](https://github.com/ai-trackdown/ai-trackdown/issues) - Bug reports and feature requests
- [Discussions](https://github.com/ai-trackdown/ai-trackdown/discussions) - Community discussions and template sharing
- [Documentation](https://ai-trackdown.github.io/ai-trackdown/) - Complete framework documentation

---

**Made with ❤️ for human-AI collaborative development - A documentation framework for the AI era**