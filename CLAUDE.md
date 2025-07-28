# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

The ZenAI Programming Rituals framework is a practical, open-source system for collaborating with AI development assistants using the 3PAI philosophy. It provides structured rituals, standards, and personas for effective AI-human collaboration.

## Development Environment

### Shell and Package Management

```zsh
# Use zsh for all shell commands
# For Python projects, use uv instead of pip
# Always use virtual environments (venv) for project isolation

# Python setup with uv
uv venv                   # Create virtual environment
source .venv/bin/activate # Activate virtual environment
uv pip install -r requirements.txt  # Install dependencies

# Node.js projects
# Use project-local node_modules (never global installs)
npm install               # Installs to local node_modules/
```

### Documentation Site (MkDocs)

```zsh
# Create and activate virtual environment
uv venv
source .venv/bin/activate

# Install dependencies
uv pip install -r requirements.txt

# Development
mkdocs serve              # Start documentation server (usually on http://127.0.0.1:8000)
mkdocs build              # Build static documentation site

# Preview built site
python -m http.server -d site/
```

### Git Workflow

```zsh
# Standard git workflow
git status                # Check current changes
git add .                 # Stage changes
git commit -m "type(scope): description"  # Use conventional commits

# Conventional commit types:
# feat: New feature
# fix: Bug fix
# docs: Documentation changes
# style: Code style changes (formatting, etc)
# refactor: Code refactoring
# test: Test additions or changes
# chore: Build process or auxiliary tool changes
```

## High-Level Architecture

### 3PAI Framework Philosophy

The **3PAI Philosophy** is a framework for effective AI-human collaboration in software development. Despite its name, it consists of **four interconnected pillars** that ensure every technical, design, and business decision is filtered through a **customer value lens**:

#### 1. **People + AI** 🧠
**Focus**: Customer-centric collaboration and stakeholder alignment
- **Key Principle**: AI capabilities enhance human expertise, not replace it
- **Implementation**: Through defined personas (Customer, Architect, Security Engineer, etc.)
- **North Star**: The Customer Persona guides all decisions
- **Goal**: True AI-human partnership with clear roles and responsibilities

#### 2. **Process** ⚙️
**Focus**: Efficient and effective ways to build trustworthy, secure, faster, cheaper, and highest quality products
- **Implementation**: Through rituals (structured processes for common development challenges)
- **Examples**: Project documentation ritual, test strategy ritual, retrospective ritual
- **Goal**: Continuous improvement and learning captured in reusable patterns
- **Mindset**: Work smarter, not harder

#### 3. **Platform** 🏗️
**Focus**: Technology, tools, frameworks, and standards that enable success
- **Implementation**: Through standards (technical and process standards for consistency)
- **Examples**: Logging standards, security standards, error handling standards
- **Goal**: Consistent technical practices across projects
- **Benefit**: Reduced cognitive load through established patterns

#### 4. **AI** 🤖
**Focus**: Integrated throughout all pillars to enhance human capabilities
- **Implementation**: 
  - Intelligent automation in development workflows
  - Knowledge capture from every interaction
  - Predictive assistance and proactive problem identification
- **Goal**: AI as a true teammate, not just a code generator
- **Philosophy**: Enhance human expertise rather than replace it

**Core Philosophy**: The framework is **learning-oriented** - extracting standards from what worked, rituals from how to improve, and continuously evolving based on real-world usage. Every decision should ultimately serve customer needs and improve their experience.

### Framework Structure

```
zenai/
├── README.md                      # 3PAI Framework Overview
├── personas.md                    # People + AI (Customer-centric roles)
├── rituals/                       # Process (How we work efficiently)
│   ├── ritual_project_documentation.md
│   ├── ritual_test_strategy.md
│   ├── ritual_technical_blueprint.md
│   ├── ritual_validation_checklist.md
│   ├── ritual_retrospective.md
│   ├── ritual_interface_design.md
│   └── ritual_antipatterns.md
├── standards/                     # Platform (What we use)
│   ├── standard_logging.md
│   ├── standard_security.md
│   ├── standard_error_handling.md
│   └── standard_testing.md
└── .cursorrules                  # AI assistant behavioral contract
```

### Key Components

- **Personas**: Define roles for both AI assistants and human team members
- **Rituals**: Proven processes for common development challenges
- **Standards**: Technical and process standards for consistency
- **Cursor Rules**: Behavioral contract for AI assistants working in the framework

## Important Guidelines

### Core Principles

1. **Design First, Code Later**: Complete planning before implementation
2. **Security is Default**: Follow security principles in all decisions
3. **Customer-Centric**: Filter all decisions through customer value lens
4. **Validate Before Acting**: Confirm compatibility before using tools/frameworks
5. **Source Code Organization**: 
   - Optimal file length: 150-200 lines
   - Refactor signal: 300 lines
   - Focus on single responsibility per file

### Framework Usage

1. **Start with Personas**: Understand roles and responsibilities
2. **Apply Relevant Rituals**: Choose processes that fit your project phase
3. **Follow Standards**: Use established technical patterns
4. **Continuous Learning**: Capture insights through retrospectives
5. **Contribute Back**: Share learnings to improve the framework

### Documentation Practices

1. **Keep Content Generic**: No project-specific or user-specific information
2. **Focus on Actionable Insights**: Provide practical guidance
3. **Maintain Consistency**: Follow framework structure and style
4. **Version Control**: Use conventional commits for all changes
5. **Open Source Mindset**: Write for public consumption

## Working with the Framework

### For New Projects
1. Read the 3PAI Framework overview (README.md)
2. Choose relevant personas from personas.md
3. Select appropriate rituals for your project phase
4. Apply technical standards consistently
5. Document learnings for framework improvement

### For AI Assistants
1. Review .cursorrules for behavioral expectations
2. Adopt appropriate personas based on context
3. Follow established rituals and standards
4. Validate decisions against customer value
5. Maintain security-first mindset

### For Contributors
1. Follow conventional commit format
2. Keep documentation generic and reusable
3. Focus on actionable insights and patterns
4. Test rituals in real projects before proposing
5. Include rationale for new additions

## Resources

- Framework README: `README.md`
- Cursor Rules: `zenai/.cursorrules`
- Personas Guide: `zenai/personas.md`
- Rituals Directory: `zenai/rituals/`
- Standards Directory: `zenai/standards/`