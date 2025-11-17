# Contributing to IMDS Credential Server

Thank you for your interest in contributing to the IMDS Credential Server! This document provides guidelines for contributing to this project.

## Development Workflow

This project uses an automated release process based on [Conventional Commits](https://www.conventionalcommits.org/) and [Release Please](https://github.com/googleapis/release-please). When you merge commits to the `main` branch, releases are automatically created based on the commit messages.

## Commit Message Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification for commit messages. This enables automatic version bumping and changelog generation.

### Commit Message Format

Each commit message consists of a **header**, an optional **body**, and an optional **footer**:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

The type must be one of the following:

- **feat**: A new feature (triggers a MINOR version bump)
- **fix**: A bug fix (triggers a PATCH version bump)
- **docs**: Documentation only changes
- **style**: Changes that do not affect the meaning of the code (white-space, formatting, etc)
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **perf**: A code change that improves performance
- **test**: Adding missing tests or correcting existing tests
- **build**: Changes that affect the build system or external dependencies
- **ci**: Changes to CI configuration files and scripts
- **chore**: Other changes that don't modify src or test files
- **revert**: Reverts a previous commit

### Scope (Optional)

The scope should be the name of the component affected (e.g., `server`, `auth`, `config`, `docker`, etc.).

### Subject

The subject contains a succinct description of the change:

- Use the imperative, present tense: "change" not "changed" nor "changes"
- Don't capitalize the first letter
- No dot (.) at the end

### Breaking Changes

Breaking changes must be indicated in the footer with `BREAKING CHANGE:` or by appending `!` after the type/scope:

```
feat!: remove support for Node 6

BREAKING CHANGE: Node 6 is no longer supported
```

Breaking changes trigger a MAJOR version bump.

### Examples

#### Feature with scope
```
feat(auth): add support for OIDC authentication

Implements OpenID Connect authentication provider
with support for multiple identity providers.

Closes #123
```

#### Bug fix
```
fix: prevent credentials from being cached indefinitely

The credential cache now respects the TTL from AWS STS
instead of using a fixed 1-hour expiration.
```

#### Breaking change
```
feat!: change default port from 8080 to 80

BREAKING CHANGE: The default port has been changed from 8080 to 80.
Users must explicitly set the port to 8080 if they want to keep
the old behavior.
```

#### Documentation update
```
docs: update README with ko build instructions

Add detailed instructions for building container images
using ko and publishing to GitHub Container Registry.
```

## Pull Request Process

1. **Fork and Clone**: Fork the repository and clone it locally
2. **Branch**: Create a feature branch from `main`
   ```bash
   git checkout -b feat/my-new-feature
   ```
3. **Commit**: Make your changes and commit with conventional commit messages
4. **Push**: Push your branch to your fork
5. **PR**: Open a Pull Request against the `main` branch

## Release Process

Releases are fully automated using [Release Please](https://github.com/googleapis/release-please):

1. When commits are pushed to `main`, Release Please analyzes the commit messages
2. It creates or updates a Release PR with:
   - Version bumps based on commit types
   - Updated CHANGELOG.md
   - Updated version in relevant files
3. When the Release PR is merged:
   - A GitHub Release is created
   - Container images are built and pushed to GitHub Container Registry
   - Go binaries are built for multiple platforms and attached to the release
   - SBOMs are generated and attached
   - All artifacts are signed with Cosign

### Version Bumping Rules

- `fix:` commits trigger a PATCH version bump (0.0.X)
- `feat:` commits trigger a MINOR version bump (0.X.0)
- `feat!:` or `BREAKING CHANGE:` trigger a MAJOR version bump (X.0.0)
- Other commit types don't trigger version bumps but are included in the changelog

## Development Setup

### Prerequisites

- Go 1.19 or later
- Docker (optional, for container builds)
- [ko](https://ko.build/) (optional, for container builds)

### Building

```bash
# Build the binary
go build -o imds-credential-server .

# Run tests
go test ./...

# Build container image with ko
ko build --local .
```

### Testing

Before submitting a PR, ensure:

1. All tests pass: `go test ./...`
2. Code is formatted: `go fmt ./...`
3. Code passes linting: `golangci-lint run` (if configured)
4. Your commits follow the conventional commit format

## Code Style

- Follow standard Go conventions
- Use `gofmt` for formatting
- Add comments for exported functions and types
- Keep functions focused and small
- Write tests for new functionality

## Security

- Never commit secrets or credentials
- Use environment variables for configuration
- Follow the principle of least privilege
- Report security vulnerabilities privately to the maintainers

## Getting Help

If you have questions or need help:

1. Check the [README](README.md) and documentation
2. Search existing [issues](https://github.com/blairdrummond/imds-credential-server/issues)
3. Open a new issue with a clear description of your question or problem

## License

By contributing to this project, you agree that your contributions will be licensed under the same license as the project (see LICENSE file).