## 2026-05-17 - Secure Error Handling in UI Components
**Vulnerability:** Information Exposure (CWE-209) via exception stack traces and detailed error messages written to user-facing output tabs (NinjaTrader.Code.Output.Process).
**Learning:** In NinjaTrader add-ons, using `NinjaTrader.Code.Output.Process` writes directly to the user's UI. Outputting `error.Message` or `error.ToString()` here can leak sensitive environment, network, or internal logic details when a connection or other operation fails.
**Prevention:** Catch blocks in UI or Add-On code must log the detailed `error.Message` using `NinjaScript.Log(error.Message, LogLevel.Error)` for internal auditing, and display only a generic, safe string (e.g., 'Connection failed.') to the user via `NinjaTrader.Code.Output.Process`.
