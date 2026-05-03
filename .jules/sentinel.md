## 2025-01-29 - [Exception Information Leakage in UI Output]
**Vulnerability:** Detailed API or exception error messages were being leaked to the UI via `NinjaTrader.Code.Output.Process`.
**Learning:** `NinjaTrader.Code.Output.Process` is meant for user-facing output and can inadvertently expose stack trace or system information if used to print raw `Exception.Message` strings in `catch` blocks.
**Prevention:** Always use `NinjaScript.Log("message", LogLevel.Error)` to securely log detailed API/exception errors to the system log, and display only generic, non-sensitive error messages to the UI via `NinjaTrader.Code.Output.Process`.
