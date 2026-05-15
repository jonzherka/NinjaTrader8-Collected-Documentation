## 2026-05-15 - Prevent Information Leakage in Generic Catch Blocks
**Vulnerability:** Detailed exception messages were being logged directly to the UI using `NinjaTrader.Code.Output.Process`, exposing potentially sensitive internal information or stack details to end users.
**Learning:** In C# Add On snippets, generic catch blocks must securely log detailed errors (e.g., `error.Message`) to the system log via `NinjaScript.Log()` with `LogLevel.Error`, while only displaying generic, non-sensitive error messages to the UI.
**Prevention:** Always sanitize UI output in error handlers. Use `NinjaScript.Log("Detailed error: " + error.Message, LogLevel.Error)` for logs and `NinjaTrader.Code.Output.Process("Generic error occurred.", PrintTo.OutputTab1)` for UI output.
