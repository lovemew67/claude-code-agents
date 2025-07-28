# Claude Code Agent Framework

A template and reference implementation for creating specialized AI agents in Claude Code. This framework demonstrates best practices for building collaborative AI agents that enhance software development workflows.

## TL;DR

**Spec-driven development for AI agents** - Inspired by [AWS Kiro and win4r's methodology](https://www.aivi.fyi/aiagents/introduce-Sub-agents). Give AI precise context through specifications for exceptional results.

**Quick Start:** `cp personas/*.md /Users/<username>/.claude/agents/` then:
```bash
@product-manager create PRD → @strategic-planner design → @task-executor implement → @code-reviewer verify
```

## What is This?

This is a **template project** that serves as:
- 📚 **Learning Resource**: Study how professional Claude Code agents are structured
- 🛠️ **Reference Implementation**: Copy and adapt agents for your own projects
- 🎯 **Best Practices Guide**: Learn optimal patterns for agent design
- 🚀 **Quick Start Template**: Bootstrap your own agent-powered workflows

**Note**: This is not a standalone application, but rather a collection of agent definitions and patterns designed to be integrated into Claude Code for enhanced development capabilities.

## Core Philosophy: Spec-Driven Development

This project embodies a **spec-driven development** approach, empowering Claude Code to deliver exceptional results through precise, contextual guidance. Inspired by AWS Kiro and [win4r's AISuperDomain](https://github.com/win4r/AISuperDomain) methodology (detailed in their blog post: [Introduce Sub-agents](https://www.aivi.fyi/aiagents/introduce-Sub-agents)), our framework transforms how AI agents collaborate on software development.

### The Power of Precise Context

The spec-driven development workflow focuses on how to **precisely and concisely provide context** to agents for optimal task execution. By creating detailed specifications before implementation, we enable:

- **Clear Boundaries**: Each agent knows exactly what to build and how
- **Reduced Ambiguity**: Specifications eliminate guesswork and interpretation errors
- **Systematic Progress**: Tasks are broken down into atomic, verifiable steps
- **Quality Assurance**: Every implementation follows pre-defined acceptance criteria

This approach ensures that AI agents work with the same clarity and precision as experienced human developers following well-defined specifications.

## How to Use This Framework

### 🎓 For Learning
1. **Study Agent Definitions**: Explore the `/personas` directory to understand agent structure
2. **Review Workflows**: See how agents collaborate in the workflow patterns section
3. **Examine Best Practices**: Learn from the patterns and anti-patterns documented

### 🔧 For Implementation
1. **Copy Agent Definitions**: Take agents from `/personas` and adapt them
2. **Follow the Format**: Use the YAML frontmatter structure for consistency
3. **Test in Claude Code**: Try agents in your actual development workflow

### 🎨 For Customization
1. **Modify Existing Agents**: Adjust responsibilities and tools for your needs
2. **Create New Agents**: Use the template to build domain-specific agents
3. **Share Back**: Contribute improvements to help the community

## Overview

The Claude Code Agent Framework enables **systematic, spec-driven software development** through specialized AI agents. By providing precise context through detailed specifications, each agent operates with clarity and purpose - transforming vague requirements into well-executed implementations. Each agent has a specific role, expertise, and set of tools optimized for their domain, following the principle that **clear specifications lead to exceptional results**.

## Core Agents

### 🏗️ Strategic Planner (`@strategic-planner`)
**Role**: Expert AI Software Architect & Collaborative Planner

**Responsibilities**:
- Feature requirements analysis
- Technical design and architecture
- Task planning and decomposition
- Creating specifications in `specs/<feature>/`

**Usage**:
```bash
@strategic-planner plan user authentication feature
@strategic-planner design payment processing system
```

### ⚡ Task Executor (`@task-executor`)
**Role**: Meticulous AI Software Engineer

**Responsibilities**:
- Precise implementation of individual tasks
- Following task checklists with surgical precision
- Test execution and verification
- Maintaining task completion state

**Usage**:
```bash
@task-executor execute specs/user-auth/tasks.md
@task-executor continue implementation autonomously
```

### 🔍 Code Reviewer (`@code-reviewer`)
**Role**: Professional Code Review Expert

**Responsibilities**:
- Quality assurance and security review
- Performance optimization suggestions
- Best practices enforcement
- Post-implementation validation

**Usage**:
```bash
@code-reviewer review recent changes
@code-reviewer security audit
```

### 📐 Steering Architect (`@steering-architect`)
**Role**: AI Project Analyst & Documentation Architect

**Responsibilities**:
- Analyzing existing codebases
- Creating project guidance files (`.docs/`)
- Documenting technology stack and conventions
- Establishing project structure

**Usage**:
```bash
@steering-architect analyze codebase and create project docs
@steering-architect update technology documentation
```

### 🐛 Debugger (`@debugger`)
**Role**: Error Debugging and Troubleshooting Expert

**Responsibilities**:
- Root cause analysis
- Error pattern recognition
- Performance troubleshooting
- Bug fixes and system diagnostics

**Usage**:
```bash
@debugger investigate failing tests
@debugger troubleshoot performance issue
```

### 📊 Data Scientist (`@data-scientist`)
**Role**: Data Analysis and Analytics Expert

**Responsibilities**:
- SQL query optimization
- Statistical analysis
- Data visualization recommendations
- Business intelligence insights

**Usage**:
```bash
@data-scientist analyze user behavior data
@data-scientist create revenue report with SQL
```

### 📋 Product Manager (`@product-manager`)
**Role**: Product Requirements Expert

**Responsibilities**:
- Creating comprehensive PRDs
- User story development
- Feature specification
- Acceptance criteria definition

**Usage**:
```bash
@product-manager create PRD for notification system
@product-manager write user stories for checkout flow
```

### 📄 LLMs.txt Generator (`@llms-txt-generator`)
**Role**: LLM Context Optimization Expert

**Responsibilities**:
- Creating concise llms.txt files
- Optimizing project summaries for LLMs
- Curating essential project information
- Improving Claude Code's context efficiency

**Usage**:
```bash
@llms-txt-generator create llms.txt for this project
@llms-txt-generator update project summary
```

## Agent Definition Format

Each agent follows a standardized format with YAML frontmatter:

```yaml
---
name: agent-name                    # Unique identifier
description: Brief description...   # What the agent does
tools: file_edit, bash, file_search # Available tools
triggers:                          # Proactive activation patterns
  - "error"
  - "bug"
  - "test failure"
proactive: true                    # Can activate automatically
---

# Agent Name

## Role: [Professional Title]

### Mission
[Core purpose and value proposition]

### Core Competencies
- [Skill 1]
- [Skill 2]
...

## Workflow
[Detailed operational procedures]

## Best Practices
[Guidelines and standards]
```

## Adding Agents to Claude Code

### Step 1: Understanding Integration
Claude Code recognizes agents through the `@agent-name` syntax. When you reference an agent, Claude Code:
1. Loads the agent's definition and context
2. Adopts the agent's specialized behavior
3. Uses only the specified tools
4. Follows the defined workflows

### Step 2: Installing Agents
There are several ways to add agents to your Claude Code workflow:

#### Option A: Quick Import (Recommended)
The fastest way to import all personas into Claude Code:
```bash
# Copy all personas to your Claude Code agents directory
cp personas/*.md /Users/<username>/.claude/agents/
```
Once copied, agents are immediately available in all your Claude Code sessions using the `@agent-name` syntax.

#### Option B: Direct Reference
Simply copy the agent definition content and reference it in your conversation:
```
Please act as @strategic-planner and help me design a payment system
```

#### Option C: Project Integration
1. Copy agent definitions to your project
2. Create a `/agents` or `/personas` directory
3. Reference agents in your CLAUDE.md file
4. Use agents throughout development

#### Option D: Global Configuration
Add frequently used agents to your global Claude configuration:
1. Access Claude Code settings
2. Add agent definitions to your workspace
3. Agents become available across all projects

### Step 3: Best Practices for Agent Usage
- **One Agent at a Time**: Activate one agent per task for clarity
- **Clear Handoffs**: Explicitly transition between agents
- **Respect Boundaries**: Don't ask agents to work outside their expertise
- **Provide Context**: Give agents necessary background information

## Creating Your Own Agents

### Step 1: Identify the Need
Ask yourself:
- What repetitive tasks could be specialized?
- What expertise is needed frequently?
- Where do mistakes commonly occur?
- What workflows could be standardized?

### Step 2: Define the Agent
Create a new file in `/personas/your-agent.md`:

```yaml
---
name: your-agent
description: What this agent specializes in
tools: [appropriate tools]
triggers: [activation patterns]
proactive: false
---

# Your Agent Name

## Role: [Title]

### Mission
[What value this agent provides]

### Core Competencies
- [Specific skills]

## Workflow
[Step-by-step procedures]
```

### Step 3: Choose Appropriate Tools
Select from available Claude Code tools:
- `file_edit`: For code modifications
- `file_search`: For codebase exploration
- `bash`: For command execution
- `web_search`: For research
- `file_read`: For analysis

### Step 4: Test and Iterate
1. Test the agent in real scenarios
2. Refine workflows based on results
3. Add error handling procedures
4. Document edge cases

### Step 5: Share and Improve
- Submit PRs with new agents
- Share successful patterns
- Document lessons learned

## Project Structure

```
.
├── llms.txt                   # Concise project summary for LLMs
├── README.md                  # This file
├── CLAUDE.md                  # Claude Code specific instructions
├── .docs/                     # Global project context
│   ├── product.md             # Vision and goals
│   ├── tech.md                # Technology stack
│   └── structure.md           # Conventions
├── specs/                     # Feature specifications
│   └── <feature-name>/
│       ├── requirements.md    # User stories
│       ├── design.md          # Technical design
│       └── tasks.md           # Implementation checklist
└── personas/                  # Agent definitions
    ├── strategic-planner.md
    ├── task-executor.md
    ├── code-reviewer.md
    ├── steering-architect.md
    ├── debugger.md
    ├── data-scientist.md
    ├── product-manager.md
    └── llms-txt-generator.md
```

### File Purposes
- **llms.txt**: Quick project overview following llmstxt.org standard
- **CLAUDE.md**: Specific instructions for Claude Code instances
- **.docs/**: Detailed project documentation for agent context
- **specs/**: Feature-specific planning and implementation guides
- **personas/**: Agent behavior definitions and workflows

## Workflow Patterns

### 1. New Feature Development

```
1. Project Setup
   @steering-architect analyze codebase and create project docs
   @llms-txt-generator create llms.txt

2. Feature Planning
   @product-manager create PRD for [feature]
   @strategic-planner plan [feature] implementation

3. Implementation
   @task-executor execute specs/[feature]/tasks.md

4. Quality Assurance
   @code-reviewer review implementation

5. Issue Resolution
   @debugger fix any failing tests
```

### 2. Data-Driven Development

```
1. Analysis
   @data-scientist analyze user behavior patterns

2. Product Planning
   @product-manager create data-driven PRD

3. Implementation
   @strategic-planner design with insights
   @task-executor implement features

4. Validation
   @data-scientist measure impact
```

### 3. Bug Fix Workflow

```
1. Investigation
   @debugger analyze error logs

2. Fix Planning
   @strategic-planner design fix approach

3. Implementation
   @task-executor implement fix

4. Verification
   @code-reviewer verify fix quality
   @debugger confirm resolution
```

## Agent Collaboration

Agents work together in a coordinated workflow:

1. **Steering Architect** establishes project foundation
2. **LLMs.txt Generator** creates concise project summary
3. **Product Manager** defines what to build
4. **Strategic Planner** designs how to build it
5. **Task Executor** implements the solution
6. **Code Reviewer** ensures quality
7. **Debugger** resolves issues
8. **Data Scientist** provides insights

## Key Features

### Proactive Activation
Agents can activate automatically based on triggers:
- Code changes trigger review
- Errors trigger debugging
- New requirements trigger planning

### Autonomous Mode
Task executor supports autonomous operation:
- Continues through task lists
- Skips manual verification steps
- Only stops for blocking errors

### Quality Standards
All agents enforce:
- Code quality and security
- Testing requirements
- Documentation standards
- Performance optimization

## Integration with Claude Code

### Performance Tips
1. **Context Management**: Use llms.txt to reduce context usage
2. **Agent Focus**: One agent = one responsibility
3. **Clear Communication**: Explicit agent invocation
4. **Workflow Efficiency**: Follow established patterns

### Common Patterns
```bash
# Start new project
@steering-architect analyze this codebase
@llms-txt-generator create project summary

# Add new feature
@product-manager create PRD for user notifications
@strategic-planner design notification system
@task-executor implement notifications

# Fix production issue
@debugger investigate API timeout errors
@task-executor apply performance fix
@code-reviewer verify the solution
```

### Debugging Agents
If an agent isn't working as expected:
1. Check the agent definition syntax
2. Verify tool availability
3. Ensure clear invocation
4. Review context requirements

## Best Practices

### 1. Use the Right Agent
Each agent is optimized for specific tasks. Don't use:
- Strategic Planner for coding
- Task Executor for planning
- Code Reviewer for implementation

### 2. Follow the Workflow
The framework is designed for sequential phases:
- Plan before implementing
- Review after coding
- Debug when issues arise

### 3. Maintain Documentation
Keep project docs current:
- Update `.docs/` as project evolves
- Complete specs before implementation
- Document decisions and learnings
- Refresh llms.txt periodically

### 4. Leverage Automation
Use autonomous features when appropriate:
- Batch similar tasks
- Enable autonomous execution
- Set up proactive triggers

## Getting Started

### Quick Start (Existing Project)
```bash
# 1. Initialize project understanding
@steering-architect analyze codebase and create project docs

# 2. Create project summary
@llms-txt-generator create llms.txt for this project

# 3. Plan your first feature
@strategic-planner plan [your-feature-name]

# 4. Execute implementation
@task-executor execute specs/[your-feature-name]/tasks.md

# 5. Ensure quality
@code-reviewer review recent changes
```

### New Project Setup
```bash
# 1. Create project structure
mkdir -p .docs specs personas

# 2. Copy agent definitions
# Copy from this repository's /personas directory

# 3. Create CLAUDE.md
echo "# Project-specific Claude Code instructions" > CLAUDE.md

# 4. Initialize with agents
@steering-architect create initial project documentation
```

## Advanced Usage

### Spec-Driven Development Flow

To start a spec-driven development flow that leverages the full power of precise context:

```bash
# Product defines requirements
@product-manager create PRD for checkout optimization

# Plan technical approach
@strategic-planner design new checkout flow

# Implement in stages
@task-executor implement checkout UI updates
@task-executor add payment processing
@task-executor integrate shipping calculator

# Ensure quality
@code-reviewer audit security measures
@debugger verify payment edge cases
```

This workflow demonstrates how each agent receives clear, contextual instructions that enable them to perform their specialized tasks with precision and efficiency.

## Examples and Use Cases

### Example 1: E-commerce Checkout Feature
```bash
# Product defines requirements
@product-manager create PRD for checkout optimization

# Plan technical approach
@strategic-planner design new checkout flow

# Implement in stages
@task-executor implement checkout UI updates
@task-executor add payment processing
@task-executor integrate shipping calculator

# Ensure quality
@code-reviewer audit security measures
@debugger verify payment edge cases
```

### Example 2: Performance Optimization
```bash
# Identify issues
@debugger analyze slow API endpoints
@data-scientist query performance metrics

# Plan improvements
@strategic-planner design caching strategy

# Execute fixes
@task-executor implement Redis caching
@task-executor optimize database queries

# Validate results
@data-scientist measure performance improvements
```

### Example 3: New Developer Onboarding
```bash
# Setup project context
@steering-architect explain project architecture
@llms-txt-generator create onboarding summary

# Guide through first task
@product-manager explain feature requirements
@task-executor demonstrate implementation workflow
@code-reviewer show quality standards
```

## Contributing

To enhance the agent framework:

### 1. Agent Improvements
- Update agent definitions in `/personas`
- Add new specialized agents
- Improve existing workflows
- Fix documentation errors

### 2. Workflow Patterns
- Document new collaboration patterns
- Share successful agent combinations
- Create domain-specific workflows

### 3. Best Practices
- Share effective usage strategies
- Document lessons learned
- Create troubleshooting guides

### 4. Tool Integration
- Add new tool capabilities
- Improve tool usage patterns
- Document tool limitations

### Contribution Process
1. Fork this repository
2. Create your enhancement
3. Test with Claude Code
4. Submit a pull request
5. Share your use case

## Troubleshooting

### Common Issues

**Agent Not Responding**
- Verify exact agent name spelling
- Check if agent definition exists
- Ensure proper @ prefix usage

**Wrong Tool Usage**
- Review agent's tool list
- Verify tool availability
- Check tool permissions

**Workflow Confusion**
- One agent at a time
- Clear transitions between agents
- Provide sufficient context

**Performance Issues**
- Use llms.txt for quick context
- Minimize agent switching
- Batch related tasks

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/claude-code)
- [llmstxt.org](https://llmstxt.org) - LLM context optimization
- [Agent Best Practices](./docs/best-practices.md)
- [Community Forums](https://community.anthropic.com)

## License

This framework is designed to work with Claude Code (claude.ai/code) and follows Anthropic's usage guidelines. Feel free to use, modify, and distribute these agent definitions for your projects.