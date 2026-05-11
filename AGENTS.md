## Error Handling Conventions
- **Always preserve `log.Error` lines when fixing error paths** — improve the
message (e.g., append `err.Error()`), never silently delete them. Operator
pod logs are a primary debugging channel alongside CR status.
- **When modifying one branch of an `if err != nil` block, inspect all sibling
branches** for the same issue or for related consistency improvements.
- **Format**: `log.Error(err, fmt.Sprintf("... description ...: %s", err.Error()))` —
always include the error string in the format message.
## Test Coverage
- When fixing any branch of an `if err != nil` block, add or update tests for
**every branch in that block**, not just the one you changed.
