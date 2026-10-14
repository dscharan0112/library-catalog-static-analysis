# Static Code Analysis Report

## Project: Library Catalog System

### Tools Used
- Pylint
- Flake8
- Bandit

### Issues Identified

| No. | Issue | Type | Line | Fix Approach |
|---|---|---|---|---|
| 1 | Unused `csv` import | Code quality | 6 | Remove the import if it is not required. |
| 2 | Bare `except` clause | Error handling | 26 | Catch the specific exception expected. |
| 3 | Unused `late_fee` variable | Code quality | 31 | Remove it if unnecessary or use it in the calculation. |
| 4 | Incorrect comparison with `None` | Code quality | 32 | Use `is None` instead of `== None`. |
| 5 | Unused `days` variable | Code quality | 41 | Remove it if unnecessary or use it correctly. |
| 6 | Unsafe use of `eval()` | Security | 42 | Replace `eval()` with a safer parsing method appropriate for the input. |
| 7 | Exceptions silently ignored | Security / reliability | 26 | Handle errors explicitly rather than silently passing. |
| 8 | Missing newline at end of file | Formatting | 73 | Add a newline at the end of the Python file. |

### Conclusion
Static analysis identified code-quality, error-handling, formatting, and security concerns. The findings should be reviewed and corrected while preserving the expected library catalog functionality. All changes must be verified by rerunning the program and the analysis tools.
## Fixes Applied

1. Removed the unused `csv` import.
2. Replaced the mutable default argument with `None`.
3. Replaced the bare `except` with explicit validation for unknown book IDs.
4. Replaced the unsafe `eval()` expression with direct arithmetic.
5. Corrected the comparison to use `is None`.
6. Removed unused variables.
7. Replaced MD5 with SHA-256 for patron identifier hashing.
8. Replaced the predictable random PIN generator with the `secrets` module.
9. Replaced shell-command execution with safe file handling.
10. Used a context manager to close exported files reliably.
11. Removed the hard-coded librarian access token from the program.
12. Added a main guard to prevent execution when the module is imported.

## Verification

The corrected program was run again, and the static analysis tools were rerun to check for remaining issues. Final scores and remaining warnings should be recorded from the actual tool output.