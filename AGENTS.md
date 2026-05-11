
## Error Handling Conventions
- **Always preserve error log lines when fixing error paths** — improve the
message when appropriate, never silently delete them. Operator
pod logs are a primary debugging channel alongside CR status.
- **When modifying one branch of a condition block chain, inspect all sibling
branches** for the same issue or for related consistency improvements.
- **Format**: always include the error string in the format message. -
## Test Coverage
- When fixing any branch of a conditional block chain, add or update tests for
**every branch in that block**, not just the one you changed.
