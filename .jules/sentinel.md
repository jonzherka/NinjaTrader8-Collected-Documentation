## 2026-05-14 - [MEDIUM] Fix Information Leakage in UI Logs
**Vulnerability:** Raw exception details (`error.Message`) were being logged directly to the UI using `NinjaTrader.Code.Output.Process`, potentially leaking sensitive internal error information to users.
**Learning:** In C# Add-On snippets, catching exceptions and writing their details to UI output tabs can inadvertently expose stack traces, internal paths, or API specifics.
**Prevention:** Always log detailed error messages securely to the system log using `NinjaScript.Log("message", LogLevel.Error)` and display a generic, non-sensitive error message to the UI via `NinjaTrader.Code.Output.Process`.
