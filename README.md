# new-project-boilerplate
Boilerplate prompts, documentatiom, and process for building LLM driven applications.

## What is new-project-boilerplate?

new-project-boilerplate provides a systematic methodology for starting projects with solid foundations. Instead of jumping straight into code, it guides you through creating comprehensive documentation that defines your project's structure, rules, and implementation plan.

## Key Features

- **Documentation-First Approach** - Build comprehensive project documentation before coding
- **AI-Optimized** - Structured for maximum compatibility with AI development tools
- **Systematic Setup** - Step-by-step process from concept to implementation
- **Best Practices** - Industry-standard coding conventions and project structure
- **Iterative Development** - Phased approach from MVP to full-featured application

## Quick Start

1. **Follow the Setup Guide**: Start with [`llm/project/setup.md`](llm/project/setup.md) for the complete walkthrough
2. **Define Your Project**: Create a detailed project overview using the example template
3. **Build Documentation**: Generate user flows, tech stack, design rules, and project conventions
4. **Plan Development**: Outline iterative development phases from setup to MVP, with an optional review & hardening phase
5. **Capture Implementation Notes**: Add docs in [`llm/implementation/`](llm/implementation/) using the [template](llm/implementation/implementation-note-template.md)
6. **Start Building**: Begin development with a solid foundation in place

## Documentation Structure

```
llm/
├── README.md                    # How this workspace works
├── project/                     # Canonical project plan and phases
│   ├── setup.md                 # Complete setup walkthrough
│   ├── project-overview-example.md
│   ├── project-overview.md      # Your project definition (copy from example)
│   ├── user-flow.md             # User journey mapping
│   ├── tech-stack.md            # Technology choices and conventions
│   ├── design-rules.md          # UI principles and styling guidelines
│   ├── project-rules.md         # Coding standards and file organization
│   └── phases/                  # Development phase planning
│       ├── README.md
│       ├── phase-template.md
│       ├── setup-phase.md
│       ├── mvp-phase.md
│       ├── review-and-hardening-phase.md (optional)
│       └── [additional-phase].md (optional)
├── context/                     # Implementation-specific references (e.g., specs)
│   └── [context-docs].md
├── implementation/              # Implementation notes about the current build
│   ├── README.md
│   └── implementation-note-template.md
└── workflows/                   # Common runbooks (e.g., local lint/build/CI checks, db migrations, release)
    └── dev-env-local-example.md
```
Example templates end with `-example`; copy and rename them for your project.

## Getting Started

Begin by following the setup guide in [`llm/project/setup.md`](llm/project/setup.md) to establish your project foundation and development workflow. When prompting agents for tech-stack suggestions, attach `llm/context/freedom-tech-agent-prompt.md` (copied from the [AI Dev Program freedom-tech repo](https://github.com/pleb-devs/freedom-tech) [`agent-prompt.md`](https://github.com/pleb-devs/freedom-tech/blob/main/agent-prompt.md)) as suggestion-only input if you want sovereignty-focused options.
