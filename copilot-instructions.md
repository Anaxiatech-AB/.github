# Anaxiatech AB — Organization Copilot Instructions

These instructions apply to **all repositories** in the Anaxiatech-AB organization.

## Company Context

**Anaxiatech AB** is a Swedish technology company specializing in AI-powered infrastructure inspection tools. Our primary product, Crackz, detects cracks in concrete structures for harbor and maritime infrastructure.

- **Industry**: Infrastructure inspection, maritime engineering
- **Location**: Sweden
- **Website**: https://anaxiatech.se
- **Contact**: theresia.lundgren@anaxiatech.se

## Technology Standards

### Language & Runtime
- **Python 3.13** — Required across all projects
- **Package Manager**: `uv` exclusively — never use `pip` or `conda` directly
- **Type Checking**: mypy with strict mode for public APIs
- **Linting**: Ruff (100 char line length, 4 spaces, Google-style docstrings)

### Development Practices
- **Testing**: pytest with minimum 75% coverage
- **Logging**: Loguru (`from loguru import logger`) — never use `print()` in production code
- **Configuration**: Pydantic v2 models for type-safe configuration
- **Documentation**: MkDocs with Material theme
- **Containers**: Docker with multi-stage builds

### Code Quality
- Add type hints to all public interfaces
- Use `pathlib.Path` for all file paths (cross-platform)
- Follow single responsibility principle
- Make minimal, surgical changes
- Write platform-agnostic code (Windows, Linux, macOS)

### Git Conventions
- **Branching**: Feature branches (`feat/`, `fix/`, `docs/`, `refactor/`) — never push to `main` directly
- **Commits**: Conventional commits (`feat:`, `fix:`, `docs:`, `perf:`, `test:`, `ci:`, `chore:`)
- **Merge strategy**: Squash merge for linear history
- **Semantic release**: Commit types drive version bumping and changelog generation

### CLI Standards (Typer)
- Use `typer.secho()` with colors for user-facing messages (green=success, red=error, yellow=warning, cyan=info)
- Use `logger` for operational/technical information
- Never use `print()`, `typer.echo()`, or Rich `console.print()` in CLI commands

### Security
- Never commit secrets, API keys, or credentials
- Use environment variables for sensitive configuration
- Follow least-privilege principles

## Domain Knowledge

### Infrastructure Inspection
- **Target structures**: Harbors, bridges, quays, concrete infrastructure
- **Detection targets**: Cracks, surface defects, deterioration
- **Users**: Inspection teams, infrastructure engineers, maritime authorities
- **Compliance**: Enterprise deployment requirements, data privacy

### AI/ML Stack
- **Framework**: PyTorch Lightning with segmentation-models-pytorch
- **Architecture**: U-Net with ResNet encoders for semantic segmentation
- **Data**: Structured splits (train/val/test/raw) with paired image/mask datasets
- **Deployment**: Docker containers with optional GPU support

## Response Guidelines

- Respond in the same language as the user (Swedish or English)
- Prioritize production-readiness over cleverness
- Consider enterprise deployment constraints
- Follow existing project conventions visible in the codebase
- Reference project documentation when available (CONTEXT.md, PLAYBOOK.md, docs/)
