# User Profile - molaw

This file contains user-specific preferences and configurations that Claude Code should reference across all projects.

## 👤 Identity

- **Name:** Frank
- **GitHub Username:** molaw
- **GitHub Profile:** https://github.com/molaw
- **Primary Email:** (stored locally, not in repo)

## 💻 Development Preferences

### Primary Technologies
- **Languages:** Python, C#, C/C++
- **Frameworks:** .NET, Arduino, ESP32/ESP8266, Docker
- **Platforms:** Windows, Linux, Embedded Systems
- **Tools:** VS Code, Git, uv (Python package manager)

### Development Environment
- **OS:** Windows (with OneDrive)
- **Python Version:** 3.12
- **Default Branch:** main (not master)
- **Line Endings:** LF (with CRLF warnings accepted on Windows)

## 🔐 Security Preferences

### Token Storage
- **Location:** `.github_token` in project root
- **Always in .gitignore:** Yes
- **Token Type:** Personal Access Token (classic)
- **Required Permissions:** repo, workflow

### Secret Management
- Store secrets in: `.env`, `.github_token`, `*.token` files
- Always exclude from git: Yes
- Use environment variables: Yes
- Scan before push: Yes

## 🎨 Code Style Preferences

### Git Commits
- **Style:** Detailed with bullet points
- **Format:**
  ```
  Brief description (50 chars)

  Detailed explanation:
  - Point 1
  - Point 2

  Generated with Claude Code (claude.ai/code)

  Co-Authored-By: Claude <noreply@anthropic.com>
  ```

### Code Comments
- Prefer: Clear, explanatory docstrings
- Documentation: Comprehensive module and function docs
- Type hints: Use Python type hints throughout

### Naming Conventions
- **Python:** snake_case for functions/variables, PascalCase for classes
- **Files:** kebab-case for multi-word files
- **Repos:** kebab-case (e.g., code-organizer)
- **Branches:** feature/name, bugfix/name, docs/name

## 🗂️ Project Structure Preferences

### Python Projects
```
project-name/
├── project_name/          # Main package
│   ├── __init__.py
│   ├── main.py
│   └── modules/
├── tests/
│   └── __init__.py
├── .gitignore
├── pyproject.toml
├── README.md
├── CLAUDE.md
└── .python-version
```

### .gitignore Patterns
Always include:
- Python: `__pycache__/`, `*.py[oc]`, `.venv/`, `*.egg-info`
- IDE: `.vscode/`, `.idea/`, `*.swp`
- OS: `.DS_Store`, `Thumbs.db`
- Secrets: `.github_token`, `*.token`, `.env`, `.env.local`
- Logs: `*.log`, project-specific log directories

## 📦 GitHub Repository Preferences

### Default Settings
- **Visibility:** Public (unless specified otherwise)
- **Features:** Enable issues, projects, wiki
- **Branch Protection:** Not required for personal projects
- **Description:** Always provide detailed description

### Repository Naming
- Use kebab-case
- Be descriptive (2-4 words)
- Avoid redundancy
- Examples: `code-organizer`, `claude-skills`, `iot-dashboard`

## 🛠️ Tool Preferences

### Package Management
- **Python:** uv (preferred), fallback to pip
- **Node.js:** npm
- **System:** Windows package managers where available

### Terminal
- **Windows:** Command Prompt, PowerShell
- **Unicode:** Avoid emojis in output (Windows console compatibility)
- **Colors:** Use ANSI colors via Rich library

### CLI Design
- **Framework:** Click
- **Output:** Rich library for beautiful terminal UI
- **Progress:** Show progress bars for long operations
- **Logging:** Always log to file with timestamps

## 📚 Documentation Preferences

### README Structure
1. Title and brief description
2. Features/Overview
3. Installation instructions
4. Usage examples
5. Project structure (if complex)
6. Technology stack
7. Roadmap (for active projects)
8. Contributing (if open source)
9. License

### Code Documentation
- All modules have docstrings
- All public functions have docstrings
- Use type hints
- Include examples in docstrings for complex functions

### CLAUDE.md
- Always create for projects
- Include common commands
- Document architecture
- Note important constraints
- Reference skills repository

## 🔄 Workflow Preferences

### Development Workflow
1. Create feature branch (optional for solo projects)
2. Make changes with frequent commits
3. Test changes
4. Update documentation
5. Create pull request or merge to main
6. Push to GitHub

### Git Workflow
- Commit frequently with clear messages
- Push regularly to GitHub
- Use `--force-with-lease` instead of `--force`
- Always pull before push if collaborating

### Testing Workflow
- Write tests for new features
- Run tests before committing
- Use pytest for Python projects
- Aim for reasonable coverage (not 100% obsession)

## 🎯 Project Philosophy

### Code Quality
- **Readability over cleverness**
- **Documentation is essential**
- **Testing is important but pragmatic**
- **Security first, always**

### Development Approach
- Start with working code
- Refactor as needed
- Document as you go
- Test important paths
- Optimize only when necessary

### Project Organization
- Modular architecture
- Clear separation of concerns
- Keep it simple (KISS)
- Don't repeat yourself (DRY)

## 📁 Common Project Locations

### Windows
- **Projects Root:** `C:\Users\frank\Projects\`
- **Active Work:** `C:\Users\frank\Projects\Active\`
- **Production Tools:** `C:\Users\frank\Projects\Production\Tools\`
- **Client Work:** `C:\Users\frank\Projects\Client-Work\`
- **Skills Repository:** `C:\Users\frank\Projects\Production\Tools\claude-skills\`
- **Logs:** `C:\Users\frank\CodeOrganization_Logs\`

### Legacy Locations (Being Organized)
- **Old Projects:** `C:\Users\frank\OneDrive - Central Baptist Church\Documents\3-Source\`
- **To Be Scanned:** Run code-organizer to catalog and organize

### Git Configuration
- **Global user.name:** (configured in git config)
- **Global user.email:** (configured in git config)
- **Default editor:** VS Code (if configured)

## 🚀 Future Preferences to Document

As you work on more projects, add:
- API design patterns you prefer
- Database schema conventions
- Error handling strategies
- Logging patterns
- Testing strategies
- Deployment workflows
- CI/CD preferences

## 📝 Notes

- This profile should be updated as preferences evolve
- Keep sensitive information out of this file
- Reference this in CLAUDE.md files: "See ~/claude-skills/USER_PROFILE.md"
- Claude Code should check this file when starting new projects

---

**Last Updated:** October 26, 2025
**Version:** 1.0.0
