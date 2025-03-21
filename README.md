# Architect - Development Documentation Generator

## Overview

Architect is a framework for generating comprehensive project documentation optimized for AI-assisted development. It provides structured templates and workflows for creating essential documentation through interaction with Large Language Models (LLMs).

### TLDR Quick Setup (Claude 3.5 + Architect Mini Version)

1. Download these template files (store them in a .docs folder in your project root):

   - [architect-mini.md](architect-mini.md)
   - [tasks-pattern.md](tasks-pattern.md)
   - [tasks-example.md](tasks-example.md)
   - [technical-approach-pattern.md](technical-approach-pattern.md)
   - [technical-approach-example.md](technical-approach-example.md)

2. Update `architect-mini.md` DOCS_PATH (top of file):

- If followed point 1 then value would be `.docs/` to complete `${DOCS_PATH}tasks-pattern.md`

3. Share amended `architect-mini.md` with Claude 3.5 capable client with following MCP support:

- [Sequential thinking](https://github.com/arben-adm/mcp-sequential-thinking)
- [Brave search](https://github.com/arben-adm/brave-mcp-search)

4. Interact with the guided 5-step process to generate your documentation
5. Use the produced docs with the [mini-coding-workflow.md](coding-workflow/mini-coding-workflow.md) prompt in your IDE of choice

- Update it as follows:

  - BUILD_COMMAND (top of file), if intend to use yarn this would be `yarn build`
  - TEST_COMMAND (top of file), if intend to use yarn this would be `yarn test`

6. (Optional) Setup specific tech rules in for your IDE (for cursor see [MDC-Examples](mdc-files/))

For examples of the documents produced see:

- [technical-approach](technical-approach-example.md)
- [tasks](tasks-example.md)

## Versions

### Architect (Full)

- [architect.md](architect.md)
- Complete documentation suite including:
  - Product Requirements Document (PRD)
  - Technical Approach Document
  - Task List
  - Architecture, User Flow, and Data Schema Diagrams
- Ideal for full project setups

### Architect (Mini)

- [architect-mini.md](architect-mini.md)
- Streamlined version generating:
  - Technical Approach Document
  - Task List
- Perfect for smaller projects or components

## Requirements

- Claude 3.5 Sonnet or higher
- Claude Desktop with MCP capabilities, Cursor IDE 0.46+ (or similar IDE with MCP)
- [Sequential thinking](https://github.com/arben-adm/mcp-sequential-thinking)
- [Brave search](https://github.com/arben-adm/brave-mcp-search)
- Mermaid diagram support (for full version)

## Setup

1. Create documentation folder structure:

```bash
project-root/
├── docs/
    ├── tasks-pattern.md
    ├── tasks-example.md
    ├── technical-approach-pattern.md
    ├── technical-approach-example.md
    ├── prd-pattern.md (full version only)
    └── prd-example.md (full version only)
```

2. Configure your environment:

   - Update DOCS_PATH in the system prompt
   - Set up MCP tools for Claude Desktop
   - Add appropriate .cursorrules if using Cursor IDE

## Usage

1. Share the appropriate architect prompt (full or mini) with your AI assistant

2. Provide your project description, for example:

   Example - quick starter which invites revision on building a scraping tool

   ```markdown
   "I want to build a python based scraping tool that will capture data from x.com about available AI tools"
   ```

   Example - creating a boiler plate MCP project in cursor ide

   ```markdown
   Following the @architect-mini.md workflow, we will create guidance documentation for a boilerplate MCP server project that is designed to be reused and speed up the creation of mcp server implemenations. This boiler plate project should create an empty MCP server with request/response handler ready for reuse. You can refer to the @MCP Typescript SDK documentation for guidance.
   ```

   Example - a detailed product vision and problem statement for use with architect full suite

   ```markdown
   Problem statement:
   I enjoy eating street food but find it hard to know what local options there are and what they serve. I dont have time to follow all the social channels to find out about my options and know where and when they will be serving. I would also like to be able to see reviews and follow other peoples recommendations of local street food vendors.

   Product vision:
   A web directory of local street food vendors that users can follow to find out where and when they will be serving food, images of their food, what's on their menu and customer reviews of their food. This can be seen in differing levels of detail via a interactive google map - designed to share key information quickly and easily, and vendor profile pages where more detailed information can be sought. The vendor information is sourced from vendor profiles on social media platforms via automated processes and is regularly updated - requiring no effort on behalf of the vendor.
   ```

3. Follow the guided process:

   - Review and approve generated context
   - Validate feature prioritization
   - Confirm technical approach
   - Review generated documentation

4. Ready for coding workflow

   - Use generated docs in your new project
   - Use one of the coding workflow system prompts [coding-workflow-readme](coding-workflow/README.md)
   - Follow the workflow readme to run the process

## Best Practices

- Watch for the 👷 emoji to confirm prompt context retention
- Ensure the produced tasks.md has checkboxes against both the requirements and acceptance criteria
  - these are key for tracking task progress in code assist IDEs
- Share relevant documentation/links during constraint gathering
- Expect multiple revisions rather than perfect one-shot generation
- Explicitly request adherence to specific rules if needed
- If using cursor add [mermaid_best_practices.md](mermaid-diagram-guidelines.md) as a project rule
  - avoids syntax errors with ERD diagrams

## Adapt to your use cases

- This framework is adaptable and flexible
- The current example and templates work for a generic level of complexity
- If you require more detail or different formating:
  - alter the corresponding pattern and example md files to your taste
  - add additional documents to generation process
- Maybe add additional steps to the analysis step i.e. add a github search through MCP

## Alternative LLM Usage

While optimized for Claude 3.5+ with MCP, the system can work with other LLMs with some modifications and additional prompt reinforcment:

- Remove MCP-specific instructions
- Provide explicit guidance for Mermaid diagrams
- Expect more iterative interactions
- Reinforce template adherence

## Contributing

Areas for improvement:

- Token usage optimization
- GitHub MCP search integration
- Universal LLM adaptations
- Additional documentation patterns
- IDE ecosystem integrations
