## 2026-05-08 - [Exception Message Leakage in UI]

**Vulnerability:** Found detailed exception messages (`error.Message`) being passed to the UI via `NinjaTrader.Code.Output.Process`.
**Learning:** Passing detailed error information directly to UI elements can leak sensitive internal state or system paths to the end user.
**Prevention:** Securely log detailed API or exception errors to system logs using `NinjaScript.Log` and display only generic, non-sensitive error messages to the UI.
