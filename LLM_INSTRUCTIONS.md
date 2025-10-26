# LLM Instructions for All Projects

Global instructions that apply to ALL projects unless explicitly overridden in a project's CLAUDE.md file.

**Purpose:** Ensure consistent workflows and preferences across all projects when working with Claude Code or other LLM assistants.

---

## 🎯 Quick Reference

**User:** Frank (molaw)
**GitHub:** https://github.com/molaw
**Skills Repo:** https://github.com/molaw/claude-skills
**Project Root:** `C:\Users\frank\Projects\`

---

## 📦 Python Projects

### Package Management
**ALWAYS use `uv` for Python projects, never pip directly**

```bash
# Install dependencies
uv sync

# Run Python scripts
uv run python script.py

# Add new dependency
uv add package-name

# Run commands in virtual environment
uv run pytest
uv run python -m module
```

**Why uv?**
- Faster than pip
- Better dependency resolution
- Lockfile support (uv.lock)
- Consistent environments

### Python Version
- **Default:** Python 3.12
- **Specified in:** `.python-version` file
- **Management:** uv handles Python versions automatically

### Project Structure
```
my-python-project/
├── my_package/          # Main package (snake_case)
│   ├── __init__.py
│   ├── main.py
│   └── utils/
├── tests/
│   └── __init__.py
├── .gitignore           # Use template from claude-skills
├── .python-version      # 3.12
├── pyproject.toml       # Dependencies and metadata
├── README.md
├── CLAUDE.md            # Reference claude-skills
└── uv.lock              # Lockfile
```

### Dependencies File
**Always use `pyproject.toml`, not requirements.txt**

```toml
[project]
name = "my-project"
version = "0.1.0"
description = "Project description"
requires-python = ">=3.12"
dependencies = [
    "rich>=13.0.0",
    "click>=8.1.0",
]
```

---

## 📁 Project Organization

### Where to Create New Projects

**Python CLI Tool:**
```
C:\Users\frank\Projects\Active\Python\my-tool\
```

**Web Application:**
```
C:\Users\frank\Projects\Active\WebDev\my-app\
```

**.NET Application:**
```
C:\Users\frank\Projects\Active\DotNet\my-app\
```

**Arduino/ESP32:**
```
C:\Users\frank\Projects\IoT\ESP32\my-device\
```

**Quick Experiment:**
```
C:\Users\frank\Projects\Sandbox\temp-YYYY-MM-DD\
```

**Client Work:**
```
C:\Users\frank\Projects\Client-Work\CWIC\my-project\
```

### Project Lifecycle Rules

1. **Start** → Create in `Active/[Technology]/`
2. **Deploy** → Move to `Production/[Category]/`
3. **Complete** → Move to `Archive/[Year]/`
4. **Extract** → Copy reusable code to `Library/`

---

## 📝 Required Files in Every Project

### 1. README.md
**Always create**, minimum structure:
```markdown
# Project Name

Brief description

## Installation
[How to install/setup]

## Usage
[How to use]

## Technology Stack
- Python 3.12
- uv for package management
- [other dependencies]
```

### 2. CLAUDE.md
**Always create**, reference skills:
```markdown
# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

## Skills Reference
This project references skills from: https://github.com/molaw/claude-skills

Relevant skills:
- [GitHub Repository Management](https://github.com/molaw/claude-skills/blob/main/github/repository-management.md)
- [User Profile](https://github.com/molaw/claude-skills/blob/main/USER_PROFILE.md)

## Project-Specific Notes
[Add project-specific instructions here]
```

### 3. .gitignore
**Use template from claude-skills:**
```bash
# Copy from template
cp C:\Users\frank\Projects\Production\Tools\claude-skills\templates\.gitignore-python .gitignore
```

Or reference: https://github.com/molaw/claude-skills/blob/main/templates/.gitignore-python

### 4. .python-version (for Python projects)
```
3.12
```

---

## 🔐 Security & Secrets

### Token Storage
**Location:** `.github_token` in project root
**MUST be in .gitignore**

### Environment Variables
**Location:** `.env` or `.env.local`
**MUST be in .gitignore**

### Never Commit:
- Tokens (`.github_token`, `*.token`)
- Credentials (`credentials.json`, `secrets.json`)
- Environment files (`.env`, `.env.local`)
- Private keys (`*.pem`, `id_rsa`)

---

## 🎨 Code Style

### Python
- **Functions/Variables:** snake_case
- **Classes:** PascalCase
- **Constants:** UPPER_SNAKE_CASE
- **Type hints:** Always use
- **Docstrings:** Required for all public functions
- **Line length:** 88 characters (Black default)

### Naming
- **Projects:** kebab-case (`my-project-name`)
- **Python packages:** snake_case (`my_package`)
- **Git branches:** feature/name, bugfix/name, docs/name

---

## 🔄 Git & GitHub

### Initialize Git (Always)
```bash
git init
git branch -M main
```

### Commit Messages
Use template from claude-skills:
```
Brief description (50 chars)

Detailed explanation:
- What changed
- Why it changed
- Important notes

Generated with Claude Code (claude.ai/code)

Co-Authored-By: Claude <noreply@anthropic.com>
```

### GitHub Repository Creation
**Reference the skill:**
See: https://github.com/molaw/claude-skills/blob/main/github/repository-management.md

**Key points:**
- Default visibility: Public (unless specified)
- Token stored in `.github_token`
- Always in .gitignore
- Use API, not gh CLI

---

## 🛠️ Development Tools

### Terminal Output
- **Use Rich library** for Python CLI output
- **Avoid emojis** (Windows console compatibility)
- **Use ANSI colors** via Rich
- **Progress bars** for long operations

### CLI Framework
- **Python:** Click (not argparse)
- **Structure:** Commands and subcommands
- **Help text:** Always provide --help

### Logging
- **Always log to file** with timestamps
- **Location:** `~/CodeOrganization_Logs/` or project-specific
- **Level:** INFO for production, DEBUG for development
- **Format:** ISO 8601 timestamps

---

## 📚 Documentation Standards

### Code Comments
- **Prefer:** Clear code over comments
- **When needed:** Explain WHY, not WHAT
- **Docstrings:** Always for public APIs

### README Sections
1. Title and description
2. Installation/Setup
3. Usage examples
4. Project structure (if complex)
5. Technology stack
6. Development setup
7. Contributing (if open source)
8. License

### CLAUDE.md Sections
1. Skills reference (link to claude-skills)
2. Common commands (build, test, run)
3. Architecture notes
4. Important constraints
5. Project-specific conventions

---

## 🧪 Testing

### Python Testing
- **Framework:** pytest
- **Structure:** `tests/` directory
- **Coverage:** Use pytest-cov
- **Run with:** `uv run pytest`

### Test Files
- **Naming:** `test_*.py` or `*_test.py`
- **Classes:** `TestClassName`
- **Functions:** `test_function_name`

---

## 📦 Dependencies

### Adding Dependencies
```bash
# Python (uv)
uv add package-name

# Dev dependencies
uv add --dev pytest black mypy
```

### Lockfiles
- **Python:** `uv.lock` (auto-generated)
- **Commit lockfiles:** Yes, always

---

## 🚀 Deployment

### Version Numbers
- **Format:** Semantic versioning (1.0.0)
- **Location:** pyproject.toml
- **Git tags:** Match version (v1.0.0)

### Release Process
1. Update version in pyproject.toml
2. Update CHANGELOG.md
3. Commit: "Release v1.0.0"
4. Tag: `git tag v1.0.0`
5. Push: `git push && git push --tags`

---

## 💡 LLM Interaction Guidelines

### When Claude Code Starts Work on a Project

**1. Check for CLAUDE.md**
- Read project-specific instructions first
- Follow any overrides to these global instructions

**2. Reference Skills**
- Check https://github.com/molaw/claude-skills
- Use relevant skills (GitHub, Python setup, etc.)
- Follow USER_PROFILE.md preferences

**3. Verify Setup**
- For Python: Check for pyproject.toml, use uv
- For all: Check .gitignore includes secrets
- Ensure in correct Project directory

**4. Follow Structure**
- New projects in Active/
- Production code in Production/
- Reusable code in Library/

### What to Ask User

**Always ask about:**
- Project name and description
- Public or private repository
- Any specific requirements or constraints

**Never ask about:**
- Python package manager (always uv)
- Project root location (always C:\Users\frank\Projects\)
- GitHub username (always molaw)
- Commit message format (use template)

---

## 🔍 Quick Checklist for New Projects

**Starting a Project:**
- [ ] Create in correct Active/ subdirectory
- [ ] Initialize git (git init, branch -M main)
- [ ] Create .python-version (3.12)
- [ ] Create pyproject.toml with uv
- [ ] Create .gitignore from template
- [ ] Create README.md
- [ ] Create CLAUDE.md (reference claude-skills)
- [ ] First commit
- [ ] Create GitHub repository
- [ ] Push code

**During Development:**
- [ ] Use uv for all Python operations
- [ ] Commit frequently with good messages
- [ ] Update README as project evolves
- [ ] Add tests for important functionality
- [ ] Log to file for debugging

**Completing a Project:**
- [ ] Final documentation update
- [ ] Tag release version
- [ ] Move to Production/ or Archive/
- [ ] Extract reusable code to Library/

---

## 🎯 Project Templates

**Location:** `C:\Users\frank\Projects\Templates/`

**Available templates:**
- Python-CLI/ (coming soon)
- Python-Web/ (coming soon)
- Arduino-Project/ (coming soon)
- DotNet-Console/ (coming soon)

**Using templates:**
```bash
cp -r C:\Users\frank\Projects\Templates/Python-CLI C:\Users\frank\Projects\Active\Python\my-project
cd C:\Users\frank\Projects\Active\Python\my-project
# Customize and start working
```

---

## 📖 Additional Resources

- **Skills Repository:** https://github.com/molaw/claude-skills
- **User Profile:** [USER_PROFILE.md](./USER_PROFILE.md)
- **GitHub Skill:** [github/repository-management.md](./github/repository-management.md)
- **Project Structure:** `C:\Users\frank\PROJECT_STRUCTURE.md`

---

## 🔄 Updating These Instructions

**When to update:**
- New tools or preferences
- Better workflows discovered
- Project structure changes
- New templates added

**How to update:**
1. Edit this file
2. Commit to claude-skills repo
3. Push to GitHub
4. Future Claude sessions will see updates

---

**Last Updated:** October 26, 2025
**Version:** 1.0.0
**Applies to:** All projects unless overridden in project's CLAUDE.md
