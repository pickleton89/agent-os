# Changelog

All notable changes to Agent OS will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.3.5] - 2025-01-09

### Completed
- **Phase 1: Claude Code Agents Update** - Successfully transformed file-creator.md from Ruby/Rails to Python/PocketFlow paradigm
  - **Complete Template Overhaul**: Replaced all Ruby/Rails Agent OS templates with Python/FastAPI/PocketFlow equivalents
    - Mandatory docs/design.md with 8-step methodology and Mermaid diagrams
    - PocketFlow project structure templates (main.py, flow.py, nodes.py)
    - Pydantic schema templates (schemas/requests.py, schemas/responses.py)
    - Python utility templates (utils/call_llm.py)
  - **Python Project Structure**: Added comprehensive Python packaging and development templates
    - pyproject.toml with uv/FastAPI/PocketFlow dependencies and ruff/ty configuration
    - requirements.txt fallback, README.md with uv instructions, .python-version
    - Test templates for both PocketFlow nodes and FastAPI endpoints
  - **Design Document Integration**: Enhanced agent behaviors for PocketFlow workflows
    - Priority enforcement for design document creation before implementation
    - Validation of 8-step methodology sections and Mermaid diagram formatting
    - PocketFlow project structure conventions integration

### In Progress
- **Phase 2: Workflow Integration** - Updating remaining Claude Code agents (2 of 3 complete)
  - ✅ **context-fetcher.md Enhancement**: Added comprehensive PocketFlow project structure awareness
    - PocketFlow file type recognition (docs/design.md, main.py, flow.py, nodes.py, schemas/, utils/)
    - Design-first workflow priority with mandatory design document detection
    - Python configuration awareness (pyproject.toml, requirements.txt, .python-version)
    - Smart extraction examples for Node classes, Flow definitions, and utility functions
  - ✅ **git-workflow.md Enhancement**: Integrated Python tooling and PocketFlow development practices
    - Automatic Python project detection (pyproject.toml, main.py/flow.py/nodes.py structure)
    - Pre-commit quality gates with ruff linting, ty type checking, and pytest testing
    - Python-enhanced commit workflow with quality validation and status reporting
    - Python/PocketFlow PR template with code quality sections and component tracking
    - Smart constraints preventing commits with failing type checks
  - 🔄 **Next**: test-runner.md - Add PocketFlow testing patterns and pytest integration

## [1.3.4] - 2025-01-09

### Added
- **Claude Code Agents Update Plan** - Created comprehensive strategic plan for Python/PocketFlow alignment
  - Analyzed all 5 claude-code agents against new Python-based paradigm requirements
  - Identified critical gaps: file-creator.md needs complete Ruby/Rails to Python/FastAPI overhaul
  - Planned 3-phase implementation timeline for transforming agents to PocketFlow-optimized tools
  - Documented integration requirements for ruff/ty linting, pytest testing, and design-first workflows

## [1.3.3] - 2025-01-09

### Fixed
- **Command Path References** - Updated all command files to use correct `instructions/core/` paths
  - Fixed `commands/plan-product.md` path reference to point to `instructions/core/plan-product.md`
  - Fixed `commands/create-spec.md` path reference to point to `instructions/core/create-spec.md`
  - Fixed `commands/execute-tasks.md` path reference to point to `instructions/core/execute-tasks.md`
  - Fixed `commands/analyze-product.md` path reference to point to `instructions/core/analyze-product.md`
- **Agent OS Command Integration** - Commands now properly connect to PocketFlow-integrated instruction files
  - Resolves issue where commands referenced old directory structure before core/meta reorganization
  - Ensures users access enhanced LLM/AI workflow capabilities when running Agent OS commands

### Completed
- **Agent OS + PocketFlow Integration** - Major integration project now functionally complete
  - All core workflows, standards, templates, and command connectivity successfully unified
  - PocketFlow methodology fully integrated with design document validation and type safety
  - Modern Python stack prioritization maintained (uv + Ruff + ty + pytest)

## [1.3.2] - 2025-01-09

### Added
- **Selective Context Loading** - Enhanced `instructions/core/execute-tasks.md` with context-fetcher subagent integration
  - Step 2.7: Best practices review using context-fetcher for relevant sections only
  - Step 2.8: Code style review using context-fetcher for language-specific rules
- **Focused Test Verification** - New Step 7.5 for task-specific testing before full test suite
  - Uses test-runner subagent for targeted test execution
  - Verifies feature-specific tests pass before running comprehensive suite
- **Pre-flight Check Integration** - Added centralized pre-flight validation to execute-tasks workflow

### Enhanced
- **Task Understanding** - Updated Step 1 to "Task Assignment and Understanding"
  - Enhanced multi-task analysis with comprehensive task dependency tracking
  - Better scope analysis across multiple selected tasks
  - Improved deliverable identification for complex task sequences
- **PocketFlow Integration Maintained** - Preserved all existing LLM/AI detection and design document validation
  - Conditional execution based on PocketFlow component detection
  - Design-first enforcement for LLM/AI implementations
  - Modern Python stack prioritization (uv + Ruff + ty + pytest)

### Improved
- **Context Efficiency** - Reduced context usage through selective loading while maintaining quality
- **Testing Workflow** - Progressive testing approach (focused → comprehensive)
- **Multi-task Support** - Better handling of multiple parent tasks in single execution
- **Subagent Integration** - Consistent use of specialized agents for specific operations

## [1.3.1] - 2025-08-02

### Added
- **Date-Checker Subagent** - New specialized Claude Code subagent for accurate date determination using file system timestamps
  - Uses temporary file creation to extract current date in YYYY-MM-DD format
  - Includes context checking to avoid duplication
  - Provides clear validation and error handling

### Changed
- **Create-Spec Instructions** - Updated `instructions/core/create-spec.md` to use the new date-checker subagent
  - Replaced complex inline date determination logic with simple subagent delegation
  - Simplified step 4 (date_determination) by removing 45 lines of validation and fallback code
  - Cleaner instruction flow with specialized agent handling date logic

### Improved
- **Code Maintainability** - Date determination logic centralized in reusable subagent
- **Instruction Clarity** - Simplified create-spec workflow with cleaner delegation pattern
- **Error Handling** - More robust date determination with dedicated validation rules

## [1.3.0] - 2025-08-01

### Added
- **Pre-flight Check System** - New `meta/pre-flight.md` instruction for centralized agent detection and initialization
- **Proactive Agent Usage** - Updated agent descriptions to encourage proactive use when appropriate
- **Structured Instruction Organization** - New folder structure with `core/` and `meta/` subdirectories

### Changed
- **Instruction File Structure** - Reorganized all instruction files into subdirectories:
  - Core instructions moved to `instructions/core/` (plan-product, create-spec, execute-tasks, execute-task, analyze-product)
  - Meta instructions in `instructions/meta/` (pre-flight, more to come)
- **Simplified XML Metadata** - Removed verbose `<ai_meta>` and `<step_metadata>` blocks for cleaner, more readable instructions
- **Subagent Integration** - Replaced manual agent detection with centralized pre-flight check across all instruction files to enforce delegation and preserve main agent's context.
- **Step Definitions** - Added `subagent` attribute to steps for clearer delegation of work to help enforce delegation and preserve main agent's context.
- **Setup Script** - Updated to create subdirectories and download files to new locations

### Improved
- **Code Clarity** - Removed redundant XML instructions in favor of descriptive step purposes
- **Agent Efficiency** - Centralized agent detection reduces repeated checks throughout workflows
- **Maintainability** - Cleaner instruction format with less XML boilerplate
- **User Experience** - Clearer indication of when specialized agents will be used proactively

### Removed
- **CLAUDE.md** - Removed deprecated Claude Code configuration file (functionality moved to pre-flight system, preventing over-reading instructions into context)
- **Redundant Instructions** - Eliminated verbose ACTION/MODIFY/VERIFY instruction blocks

## [1.2.0] - 2025-07-29

### Added
- **Claude Code Specialized Subagents** - New agents to offload specific tasks for improved efficiency:
  - `test-runner.md` - Handles test execution and failure analysis with minimal toolset
  - `context-fetcher.md` - Retrieves information from files while checking context to avoid duplication
  - `git-workflow.md` - Manages git operations, branches, commits, and PR creation
  - `file-creator.md` - Creates files, directories, and applies consistent templates
- **Agent Detection Pattern** - Single check at process start with boolean flags for efficiency
- **Subagent Integration** across all instruction files with automatic fallback for non-Claude Code users

### Changed
- **Instruction Files** - All updated to support conditional agent usage:
  - `execute-tasks.md` - Uses git-workflow (branch management, PR creation), test-runner (full suite), and context-fetcher (loading lite files)
  - `execute-task.md` - Uses context-fetcher (best practices, code style) and test-runner (task-specific tests)
  - `plan-product.md` - Uses file-creator (directory creation) and context-fetcher (tech stack defaults)
  - `create-spec.md` - Uses file-creator (spec folder) and context-fetcher (mission/roadmap checks)
- **Standards Files** - Updated for conditional agent usage:
  - `code-style.md` - Uses context-fetcher for loading language-specific style guides
- **Setup Scripts** - Enhanced to install Claude Code agents:
  - `setup-claude-code.sh` - Downloads all agents to `~/.claude/agents/` directory

### Improved
- **Context Efficiency** - Specialized agents use minimal context for their specific tasks
- **Code Organization** - Complex operations delegated to focused agents with clear responsibilities
- **Error Handling** - Agents provide targeted error analysis and recovery strategies
- **Maintainability** - Cleaner main agent code with operations abstracted to subagents
- **Performance** - Reduced context checks through one-time agent detection pattern

### Technical Details
- Each agent uses only necessary tools (e.g., test-runner uses only Bash, Read, Grep, Glob)
- Automatic fallback ensures compatibility for users without Claude Code
- Consistent `IF has_[agent_name]:` pattern reduces code complexity
- All agents follow Agent OS conventions (branch naming, commit messages, file templates)

## [1.1.0] - 2025-07-29

### Added
- New `mission-lite.md` file generation in product initialization for efficient AI context usage
- New `spec-lite.md` file generation in spec creation for condensed spec summaries
- New `execute-task.md` instruction file for individual task execution with TDD workflow
- Task execution loop in `execute-tasks.md` that calls `execute-task.md` for each parent task
- Language-specific code style guides:
  - `standards/code-style/css-style.md` for CSS and TailwindCSS
  - `standards/code-style/html-style.md` for HTML markup
  - `standards/code-style/javascript-style.md` for JavaScript
- Conditional loading blocks in `best-practices.md` and `code-style.md` to prevent duplicate context loading
- Context-aware file loading throughout all instruction files

### Changed
- Optimized `plan-product.md` to generate condensed versions of documents
- Enhanced `create-spec.md` with conditional context loading for mission-lite and tech-stack files
- Simplified technical specification structure by removing multiple approach options
- Made external dependencies section conditional in technical specifications
- Updated `execute-tasks.md` to use minimal context loading strategy
- Improved `execute-task.md` with selective reading of relevant documentation sections
- Modified roadmap progress check to be conditional and context-aware
- Updated decision documentation to avoid loading decisions.md and use conditional checks
- Restructured task execution to follow typical TDD pattern (tests first, implementation, verification)

### Improved
- Context efficiency by 60-80% through conditional loading and lite file versions
- Reduced duplication when files are referenced multiple times in a workflow
- Clearer separation between task-specific and full test suite execution
- More intelligent file loading that checks current context before reading
- Better organization of code style rules with language-specific files

### Fixed
- Duplicate content loading when instruction files are called in loops
- Unnecessary loading of full documentation files when condensed versions suffice
- Redundant test suite runs between individual task execution and overall workflow

## [1.0.0] - 2025-07-21

### Added
- Initial release of Agent OS framework
- Core instruction files:
  - `plan-product.md` for product initialization
  - `create-spec.md` for feature specification
  - `execute-tasks.md` for task execution
  - `analyze-product.md` for existing codebase analysis
- Standard files:
  - `tech-stack.md` for technology choices
  - `code-style.md` for formatting rules
  - `best-practices.md` for development guidelines
- Product documentation structure:
  - `mission.md` for product vision
  - `roadmap.md` for development phases
  - `decisions.md` for decision logging
  - `tech-stack.md` for technical architecture
- Setup scripts for easy installation
- Integration with AI coding assistants (Claude Code, Cursor)
- Task management with TDD workflow
- Spec creation and organization system

[1.3.1]: https://github.com/buildermethods/agent-os/compare/v1.3.0...v1.3.1
[1.3.0]: https://github.com/buildermethods/agent-os/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/buildermethods/agent-os/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/buildermethods/agent-os/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/buildermethods/agent-os/releases/tag/v1.0.0
