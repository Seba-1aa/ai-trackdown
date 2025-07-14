---
# PR Template - AI-TRACKDOWN v4.3.0
# Pull request template for code changes

# Project Association (Optional)
# For multi-project environments, specify the parent project
# For single-project environments, this can be omitted or left as null
project_id: PRJ-0001  # Optional: Remove for single-project setups

pr_id: "PR-0000"
type: pr
issue_id: ISS-0000
epic_id: EP-0000
title: "[PR Title]"
description: "Technical description of code changes"
state: ready_for_review
status: open                         # DEPRECATED: Use state field
priority: medium
assignee: "@username"
created_date: "2025-07-09T10:00:00Z"
updated_date: "2025-07-09T10:00:00Z"
estimated_tokens: 50
actual_tokens: 0
ai_context:
  - "context/requirements"
  - "context/constraints"
sync_status: local

# State metadata for automation and tracking
state_metadata:
  transitioned_at: "2025-07-09T10:00:00Z"
  transitioned_by: "@username"
  previous_state: open
  automation_eligible: true
  assignee_on_transition: "@reviewers"
  notifications_sent: ["@reviewers"]
labels: []
author: "@username"
reviewer: "@reviewer"
target_branch: "main"
source_branch: "feature/branch-name"
branch_name: "feature/branch-name"
linked_issues: []
linked_tasks: []
files_changed: []
commit_count: 0
additions: 0
deletions: 0
review_requests: []
approval_count: 0
merge_strategy: "merge"
milestone: ""
token_usage:
  total: 0
  by_agent: {}
sync:
  github: null
  jira: null
  linear: null
review_status: "pending"
---

# {PR_TITLE}

> **Usage Mode**: This template supports both single-project and multi-project environments.
> - **Single Project**: Remove or set `project_id: null` in the frontmatter
> - **Multi-Project**: Specify the parent project ID (e.g., `PRJ-0001`)

## 📝 Summary

Brief description of what this PR accomplishes and why it's needed.

## 🔗 Related Items

### Linked Issues
- [ ] ISSUE-XXX: [Issue Title](../tasks/issues/ISSUE-XXX-filename.md)

### Linked Tasks  
- [ ] TASK-XXX: [Task Title](../tasks/tasks/TASK-XXX-filename.md)

## 🎯 Type of Change

- [ ] 🐛 Bug fix (non-breaking change which fixes an issue)
- [ ] ✨ New feature (non-breaking change which adds functionality)
- [ ] 💥 Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] 📚 Documentation update
- [ ] 🔧 Maintenance (dependency updates, code cleanup, etc.)
- [ ] 🚀 Performance improvement
- [ ] 🧪 Test coverage improvement

## 📋 Changes Made

### Core Changes
- Description of main changes
- Key components modified
- New functionality added

### Technical Details
- Implementation approach
- Architecture decisions
- Dependencies affected

## 🧪 Testing Strategy

### Test Coverage
- [ ] Unit tests added/updated
- [ ] Integration tests added/updated
- [ ] Manual testing completed
- [ ] Performance testing completed

### Test Results
- Test suite status
- Coverage metrics
- Performance benchmarks

## 📸 Screenshots/Demo

<!-- Include screenshots, GIFs, or demo links if applicable -->

## 🚀 Deployment Notes

### Prerequisites
- Required environment changes
- Database migrations needed
- Configuration updates required

### Rollback Plan
- Steps to rollback if issues arise
- Monitoring checkpoints
- Rollback decision criteria

## 👥 Review Checklist

### Author Checklist
- [ ] Code follows project style guidelines
- [ ] Self-review completed
- [ ] Tests added/updated and passing
- [ ] Documentation updated
- [ ] No merge conflicts
- [ ] Performance impact assessed
- [ ] Security implications reviewed

### Reviewer Checklist
- [ ] Code quality review completed
- [ ] Architecture review completed
- [ ] Test coverage adequate
- [ ] Documentation accurate
- [ ] Performance acceptable
- [ ] Security considerations addressed
- [ ] Breaking changes documented

## 🔍 Review Comments

### Review Round 1
**Reviewer**: @username  
**Date**: YYYY-MM-DD  
**Status**: approved | changes-requested | commented

**Comments**:
- Feedback point 1
- Feedback point 2

**Action Items**:
- [ ] Action item 1
- [ ] Action item 2

### Review Round 2
<!-- Additional review rounds as needed -->

## 📊 Metrics

### Code Metrics
- **Files Changed**: X files
- **Lines Added**: +X
- **Lines Deleted**: -X
- **Complexity Impact**: Low | Medium | High

### Token Usage
- **Creation Tokens**: X tokens
- **Review Tokens**: X tokens
- **Total Tokens**: X tokens

## 🔄 Activity Log

### {YYYY-MM-DD HH:MM} - PR Created
- **Author**: @username
- **Action**: Created PR from {source_branch} to {target_branch}
- **Linked**: Connected to ISSUE-XXX, TASK-XXX

### {YYYY-MM-DD HH:MM} - Review Requested
- **Author**: @username
- **Action**: Requested review from @reviewer
- **Status**: ready → in-review

### {YYYY-MM-DD HH:MM} - Changes Requested
- **Reviewer**: @reviewer
- **Action**: Requested changes
- **Status**: in-review → changes-requested
- **Comments**: X review comments added

### {YYYY-MM-DD HH:MM} - Updates Applied
- **Author**: @username
- **Action**: Applied requested changes
- **Status**: changes-requested → ready
- **Changes**: Addressed all review feedback

### {YYYY-MM-DD HH:MM} - Approved
- **Reviewer**: @reviewer
- **Action**: Approved PR
- **Status**: ready → approved
- **Notes**: Ready for merge

### {YYYY-MM-DD HH:MM} - Merged
- **Author**: @username
- **Action**: Merged PR using {merge_strategy}
- **Status**: approved → merged
- **Result**: Changes deployed to {target_branch}

## 🏷️ AI Context

### Change Summary
This PR implements [brief technical summary] to address [business need]. The changes primarily affect [system components] and introduce [new capabilities].

### Impact Assessment
- **Risk Level**: Low | Medium | High
- **Rollback Complexity**: Simple | Moderate | Complex
- **Performance Impact**: None | Minimal | Significant
- **Breaking Changes**: None | Minor | Major

### Integration Points
- External systems affected
- API changes introduced
- Database schema changes
- Configuration updates needed

---

**PR Template Version**: 1.0  
**Last Updated**: {CURRENT_DATE}  
**Framework**: ai-trackdown internal PR model