# Claude Code Skills Library

A centralized repository of reusable skills for Claude Code to reference across all projects.

## 🎯 Purpose

This repository serves as a **knowledge base** that Claude Code can reference in any conversation to:
- Remember your preferences and configurations
- Follow consistent workflows across projects
- Apply best practices automatically
- Troubleshoot issues with proven solutions
- Save time by not re-explaining processes

## 👤 User Profile

**GitHub Username:** molaw
**GitHub Profile:** https://github.com/molaw
**Skills Repository:** https://github.com/molaw/claude-skills

## 🎓 Global LLM Instructions

**[LLM_INSTRUCTIONS.md](./LLM_INSTRUCTIONS.md)** - Universal instructions for ALL projects

This file contains global preferences that apply everywhere:
- Python projects: Always use `uv`
- Project organization: `C:\Users\frank\Projects\` structure
- Required files: README.md, CLAUDE.md, .gitignore
- Code style, security, git conventions
- Testing and deployment standards

**Claude Code should read this file at the start of every project!**

## 📚 Available Skills

### 🔧 Development & Tools

#### [GitHub Repository Management](./github/repository-management.md)
Complete workflow for creating and managing GitHub repositories
- Repository creation via API
- Token-based authentication
- Security best practices
- Common git operations
- Troubleshooting guide

**Keywords:** git, github, repository, push, commit, source control

---

## 🚀 How to Use These Skills

### For You (The User)

Simply mention the task in conversation:
- "Create a GitHub repository"
- "Push this to GitHub"
- "Set up source control"

Claude Code will automatically reference the relevant skill.

### For Claude Code

When starting a new conversation:
1. Check if task matches any skill keywords
2. Reference the skill file for detailed instructions
3. Apply user preferences and configurations
4. Follow the documented workflow
5. Handle issues using troubleshooting guides

## 📁 Repository Structure

```
claude-skills/
├── README.md                          # This file
├── SKILLS_INDEX.md                    # Searchable index of all skills
├── USER_PROFILE.md                    # User preferences and configurations
│
├── github/                            # GitHub-related skills
│   ├── repository-management.md       # Create and manage repos
│   ├── pull-requests.md               # PR workflows (future)
│   └── actions.md                     # GitHub Actions (future)
│
├── python/                            # Python development skills
│   ├── project-setup.md               # New project initialization (future)
│   ├── testing.md                     # Testing workflows (future)
│   └── packaging.md                   # PyPI publishing (future)
│
├── docker/                            # Docker and containers
│   ├── dockerfile-best-practices.md   # (future)
│   └── compose-setup.md               # (future)
│
├── documentation/                     # Documentation skills
│   ├── readme-templates.md            # (future)
│   └── api-docs.md                    # (future)
│
├── security/                          # Security practices
│   ├── secrets-management.md          # (future)
│   └── code-scanning.md               # (future)
│
└── templates/                         # Reusable templates
    ├── .gitignore-python              # Python .gitignore
    ├── .gitignore-node                # Node.js .gitignore
    └── commit-message-template.txt    # Git commit template
```

## 🔍 Skills Index

Quick reference by task:

| Task | Skill | File |
|------|-------|------|
| Create GitHub repo | GitHub Repository Management | [github/repository-management.md](./github/repository-management.md) |
| Push to GitHub | GitHub Repository Management | [github/repository-management.md](./github/repository-management.md) |
| Git operations | GitHub Repository Management | [github/repository-management.md](./github/repository-management.md) |
| Setup Python project | Python Project Setup | [python/project-setup.md](./python/project-setup.md) (future) |
| Write tests | Python Testing | [python/testing.md](./python/testing.md) (future) |
| Create Dockerfile | Docker Best Practices | [docker/dockerfile-best-practices.md](./docker/dockerfile-best-practices.md) (future) |

## 🎓 Creating New Skills

### Skill Template

When creating a new skill, use this structure:

```markdown
# Skill Name

Brief description of what this skill does.

## Keywords
List keywords for auto-detection: keyword1, keyword2, keyword3

## When to Use This Skill
- Use case 1
- Use case 2

## User Preferences (if applicable)
[User-specific configurations]

## Prerequisites
- Requirement 1
- Requirement 2

## Step-by-Step Instructions

### Step 1: [Action]
[Detailed instructions]

### Step 2: [Action]
[Detailed instructions]

## Code Examples
[Practical examples with copy-paste ready code]

## Common Issues and Solutions

### Issue: [Problem Description]
**Solution:** [Fix]

## Quick Reference
[Useful commands or snippets]

## Related Skills
- [Link to related skill 1]
- [Link to related skill 2]
```

### Adding a New Skill

1. **Choose the right category** (github, python, docker, etc.)
2. **Create the markdown file** with descriptive name
3. **Use the template above**
4. **Update README.md** - Add to "Available Skills" and index
5. **Update SKILLS_INDEX.md** - Add searchable entry
6. **Commit and push**
7. **Test** - Try referencing it in a conversation

## 🔄 Keeping Skills Updated

As you learn better approaches or preferences change:

1. **Edit the skill file** with improvements
2. **Commit with descriptive message**
3. **Push to GitHub**
4. Future Claude sessions will use the updated version

## 🌟 Benefits

### Consistency
- Same workflow across all projects
- No repeated explanations
- Reliable results

### Efficiency
- Faster task completion
- Automated best practices
- Quick troubleshooting

### Knowledge Retention
- Capture what works
- Document preferences
- Build expertise over time

### Collaboration
- Share skills with others
- Learn from community
- Contribute improvements

## 📝 Skill Categories

### 🔧 Development
Tools, setup, and development workflows

### 🧪 Testing
Testing strategies, frameworks, and CI/CD

### 📦 Deployment
Packaging, publishing, and deployment processes

### 📚 Documentation
Documentation generation and best practices

### 🔒 Security
Security scanning, secrets management, and best practices

### 🎨 Code Quality
Linting, formatting, and code review

### 🗄️ Databases
Database operations, migrations, and backups

### 🐳 Containers
Docker, Kubernetes, and containerization

### ☁️ Cloud
AWS, Azure, GCP, and cloud services

## 🎯 Recommended Skills to Create

Based on common tasks:

**High Priority:**
- [ ] Python project setup
- [ ] Testing with pytest
- [ ] Docker containerization
- [ ] Documentation generation
- [ ] Code review checklist

**Medium Priority:**
- [ ] GitHub Actions CI/CD
- [ ] API development patterns
- [ ] Database migrations
- [ ] Deployment workflows
- [ ] Security scanning

**Nice to Have:**
- [ ] Performance optimization
- [ ] Monitoring and logging
- [ ] Error handling patterns
- [ ] Refactoring strategies
- [ ] Architecture patterns

## 🔗 Integration

### In Projects

Reference this repository in your projects:

**Option 1: Git Submodule**
```bash
git submodule add https://github.com/molaw/claude-skills.git .claude/skills
```

**Option 2: Reference in CLAUDE.md**
```markdown
## Skills Repository
This project references skills from: https://github.com/molaw/claude-skills
```

**Option 3: Clone Locally**
```bash
git clone https://github.com/molaw/claude-skills.git ~/claude-skills
```

### In Conversations

Claude Code will automatically:
1. Detect task matches (via keywords)
2. Fetch relevant skill from repository
3. Apply instructions and preferences
4. Follow documented workflows

## 📊 Statistics

- **Total Skills:** 1
- **Categories:** 1
- **Lines of Documentation:** 553+
- **Code Examples:** 20+
- **Troubleshooting Entries:** 10+

## 🤝 Contributing

This is a personal skills library, but you can:
- Fork for your own use
- Submit suggestions via issues
- Share useful patterns
- Propose new skill categories

## 📜 License

MIT License - Free to use, modify, and share

## 🔮 Future Enhancements

- **Skill versioning** - Track changes to workflows
- **Skill dependencies** - Skills that reference other skills
- **Skill templates** - Pre-built templates for common tasks
- **Community skills** - Share and discover skills from others
- **Auto-update** - Claude automatically fetches latest versions

## 📞 Support

- **Repository Issues:** https://github.com/molaw/claude-skills/issues
- **Main Profile:** https://github.com/molaw
- **Claude Code:** https://claude.com/claude-code

---

**Last Updated:** October 26, 2025
**Version:** 1.0.0
**Status:** Active
**Skills Count:** 1

**Built with Claude Code** 🤖
