# spec-kit-preset-ears-notation

A [spec-kit](https://github.com/github/spec-kit) preset that makes `/speckit.specify` generate functional requirements in **EARS (Easy Approach to Requirements Syntax)** notation.

## What it does

- Replaces the default `FR-NNN: System MUST...` requirement format with EARS patterns
- Uses `REQ-NNN` as the identifier prefix
- Injects a pattern reference guide into the `/speckit.specify` command
- Provides an EARS-formatted spec template

## EARS Patterns

| Pattern | Template |
|---------|----------|
| Ubiquitous | `The system SHALL [response]` |
| Event-driven | `WHEN [trigger], the system SHALL [response]` |
| State-driven | `WHILE [state], the system SHALL [response]` |
| Unwanted behavior | `IF [precondition], WHEN [trigger], the system SHALL [response]` |
| Optional feature | `WHERE [feature is included], the system SHALL [response]` |
| Complex | `WHILE [state], IF [precondition], WHEN [trigger], the system SHALL [response]` |

## Installation

```bash
# From GitHub (pin to a release tag for stability)
specify preset add --from https://github.com/ynny-github/spec-kit-preset-ears-notation/archive/refs/tags/v1.0.0.zip

# Or from main branch
specify preset add --from https://github.com/ynny-github/spec-kit-preset-ears-notation/archive/refs/heads/main.zip
```

Or at project init time:

```bash
specify init --here --integration claude \
  --preset https://github.com/ynny-github/spec-kit-preset-ears-notation/archive/refs/heads/main.zip
```

## Usage

After installation, use `/speckit.specify` as normal. The generated spec will have EARS-formatted requirements:

```markdown
- **REQ-001**: WHEN a user submits the login form, the system SHALL validate credentials.
- **REQ-002**: IF invalid credentials are provided, WHEN a user submits the login form,
  the system SHALL display an error message.
- **REQ-003**: WHILE a session is active, the system SHALL refresh the token every 30 minutes.
- **REQ-004**: The system SHALL encrypt all stored passwords.
```

## Updating

```bash
specify preset remove ears-notation
specify preset add --from https://github.com/ynny-github/spec-kit-preset-ears-notation/archive/refs/tags/v1.1.0.zip
```

## License

MIT
