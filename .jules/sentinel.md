## 2026-05-18 - Prevent Exception Information Leakage to UI

**Vulnerability:** Outputting `Exception.Message` directly to the UI (e.g., via `NinjaTrader.Code.Output.Process`) risks leaking sensitive internal application details or paths to end users.
**Learning:** In C# Add-on snippets, UI logging methods must only receive generic, non-sensitive error messages. To avoid obscuring errors for debugging, the full error details must be securely sent to the system logs using `NinjaScript.Log(..., LogLevel.Error)`.
**Prevention:** Always use `NinjaScript.Log` for detailed technical errors and generic strings for user-facing outputs in catch blocks.
