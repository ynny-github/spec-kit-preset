## EARS Notation Override

This project uses **EARS (Easy Approach to Requirements Syntax)**.

When generating the **Functional Requirements** section,
use EARS patterns below instead of the `FR-NNN: System MUST...` format shown
in the default template. Use `REQ-NNN` as the identifier prefix.

### EARS Patterns

| Pattern | Template | Use when |
|---------|----------|----------|
| Ubiquitous | `The system SHALL [response]` | Always-active behavior |
| Event-driven | `WHEN [trigger], the system SHALL [response]` | User actions or external events |
| State-driven | `WHILE [state], the system SHALL [response]` | Behavior under a persistent condition |
| Unwanted behavior | `IF [precondition], WHEN [trigger], the system SHALL [response]` | Error and exception handling |
| Optional feature | `WHERE [feature is included], the system SHALL [response]` | Optional capabilities |
| Complex | `WHILE [state], IF [precondition], WHEN [trigger], the system SHALL [response]` | Combined conditions |

### Example

- **REQ-001**: WHEN a user submits the login form, the system SHALL
  validate credentials and grant access within 2 seconds.
- **REQ-002**: IF invalid credentials are provided, WHEN a user submits
  the login form, the system SHALL display an error message and lock the
  account after 5 consecutive failures.
- **REQ-003**: WHILE a session is active, the system SHALL refresh the
  session token every 30 minutes.
- **REQ-004**: The system SHALL encrypt all stored passwords using a
  recognised hashing algorithm.
