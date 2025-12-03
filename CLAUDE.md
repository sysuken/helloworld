# CLAUDE.md - AI Assistant Guide for helloworld Repository

**Last Updated:** 2025-12-03
**Repository:** sysuken/helloworld
**Purpose:** Hello World demonstration repository

---

## Repository Overview

This is a minimal "hello world" repository currently containing only a README.md file. It serves as a starting point for future development or demonstration purposes.

### Current Structure

```
helloworld/
├── README.md          # Simple greeting file with basic introduction
└── CLAUDE.md          # This file - AI assistant guide
```

---

## Codebase Analysis

### Current State
- **Language/Framework:** Not yet determined (no code files present)
- **Files:** 1 content file (README.md)
- **Commits:** 2 total commits
  - `978859f` - Initial commit
  - `91edbb8` - Update README.md
- **Branch:** `claude/claude-md-miq12r5zrfhk79fe-01413kqKfvNW5JB1TAV9bZq8`

### README.md Content
The README contains a simple greeting:
- Title: "helloworld"
- Message: "nice to meet you"

---

## Development Workflows

### Git Branching Strategy

**CRITICAL:** This repository uses a specific branch naming convention:

1. **Feature Branches:** Must start with `claude/` prefix
2. **Session Tracking:** Branch names include session identifiers
3. **Current Branch:** `claude/claude-md-miq12r5zrfhk79fe-01413kqKfvNW5JB1TAV9bZq8`

#### Branch Naming Pattern
```
claude/<descriptor>-<session-id>
```

### Git Operations Best Practices

#### Pushing Changes
```bash
# Always use the -u flag with origin
git push -u origin <branch-name>

# IMPORTANT: Branch MUST start with 'claude/' and end with matching session id
# Otherwise push will fail with 403 HTTP error
```

#### Network Resilience
- Retry failed operations up to 4 times with exponential backoff:
  - 1st retry: 2 seconds
  - 2nd retry: 4 seconds
  - 3rd retry: 8 seconds
  - 4th retry: 16 seconds

#### Fetching/Pulling
```bash
# Prefer specific branch fetches
git fetch origin <branch-name>
git pull origin <branch-name>
```

### Commit Message Conventions

Follow these guidelines for commit messages:

1. **Format:** Clear, descriptive messages that explain "why" not just "what"
2. **Style:** Use present tense ("Add feature" not "Added feature")
3. **Structure:**
   ```
   Brief summary (50 chars or less)

   Detailed explanation if needed (wrap at 72 chars)
   ```

### Development Workflow Steps

1. **Branch Creation/Verification**
   ```bash
   # Ensure you're on the correct claude/* branch
   git branch --show-current
   ```

2. **Make Changes**
   - Edit existing files or add new files as needed
   - Follow project conventions (see below)

3. **Stage Changes**
   ```bash
   git add <files>
   # Or for all changes:
   git add .
   ```

4. **Commit**
   ```bash
   git commit -m "$(cat <<'EOF'
   Descriptive commit message here
   EOF
   )"
   ```

5. **Push to Remote**
   ```bash
   git push -u origin <claude-branch-name>
   ```

---

## Key Conventions for AI Assistants

### General Principles

1. **Simplicity First:** This is a hello world repository - avoid over-engineering
2. **Read Before Modify:** Always read existing files before making changes
3. **Minimal Changes:** Only make changes that are explicitly requested
4. **No Unnecessary Features:** Don't add features, comments, or refactoring beyond what's asked

### File Operations

- **Prefer Editing:** Always prefer editing existing files over creating new ones
- **Use Proper Tools:** Use Read/Edit/Write tools, not bash commands for file operations
- **Check First:** Before creating directories or files, verify the parent directory exists

### Code Quality (When Code is Added)

- **Security:** Watch for common vulnerabilities (XSS, SQL injection, command injection, etc.)
- **Error Handling:** Only add error handling at system boundaries, not for internal operations
- **Comments:** Only add comments where logic isn't self-evident
- **Abstractions:** Don't create abstractions for one-time operations

### Communication Style

- **Concise:** Keep responses short and concise for CLI display
- **No Emojis:** Don't use emojis unless explicitly requested
- **Direct Output:** Output text directly, don't use echo or comments to communicate
- **Code References:** Use `file_path:line_number` format when referencing code

### Task Management

When working on multi-step tasks:

1. **Use TodoWrite Tool:** For tasks with 3+ steps or complex workflows
2. **Track Progress:** Mark tasks as in_progress before starting, completed when done
3. **One Task at a Time:** Only one task should be in_progress at once
4. **Real-time Updates:** Update task status immediately, don't batch completions

### Testing and Validation

Before committing:

1. Verify all requested changes are complete
2. Check that no unintended changes were made
3. Ensure no sensitive data is being committed (.env, credentials, etc.)
4. Run any existing tests or build commands if applicable

---

## Repository Context

### Remote Information
- **Origin:** `http://local_proxy@127.0.0.1:34264/git/sysuken/helloworld`
- **Owner:** sysuken
- **Type:** Git repository

### Future Development Considerations

Since this repository is currently minimal, here are recommendations for future expansion:

#### If Adding Code
- Determine and document the primary language/framework
- Add appropriate `.gitignore` file
- Include dependency management files (package.json, requirements.txt, etc.)
- Add configuration files as needed

#### If Creating a Project
- Define project structure in this document
- Document build/run instructions
- Add testing guidelines
- Include contribution guidelines if applicable

#### If Adding Documentation
- Keep README.md user-focused
- Use CLAUDE.md for AI assistant guidance
- Add additional docs in a `docs/` directory if needed

---

## Common Tasks

### Reading the Repository
```bash
# View all files
find . -type f ! -path "./.git/*"

# Check current branch
git branch --show-current

# View recent commits
git log --oneline -10

# Check repository status
git status
```

### Making Changes
```bash
# Check current state
git status

# Make your changes (use Read/Edit/Write tools)

# Stage changes
git add <files>

# Commit with descriptive message
git commit -m "Description of changes"

# Push to remote
git push -u origin claude/claude-md-miq12r5zrfhk79fe-01413kqKfvNW5JB1TAV9bZq8
```

### Troubleshooting

#### Push Fails with 403
- Verify branch name starts with `claude/`
- Verify branch name ends with correct session ID
- Check network connectivity
- Retry with exponential backoff (2s, 4s, 8s, 16s)

#### Branch Doesn't Exist
```bash
# Create and switch to the branch
git checkout -b <branch-name>
```

---

## Questions and Support

- For help with Claude Code: Use `/help` command
- To report issues: https://github.com/anthropics/claude-code/issues
- Repository-specific questions: Ask the repository owner (sysuken)

---

## Document Maintenance

This document should be updated when:
- Repository structure changes significantly
- New conventions are established
- Build/test processes are added
- New tools or frameworks are integrated
- Workflow changes are implemented

**Update Frequency:** Review and update whenever significant changes occur to the repository structure or development workflow.
