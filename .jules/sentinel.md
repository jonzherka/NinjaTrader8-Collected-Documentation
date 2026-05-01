## 2024-05-24 - Secure Exception Handling Pattern
**Vulnerability:** Information Leakage
**Learning:** Outputting exception messages directly to the UI (e.g., via `NinjaTrader.Code.Output.Process`) can leak sensitive internal details like connection strings, file paths, or API errors. In NinjaTrader, `NinjaScript.Log` should be used to log the detailed error internally while generic messages are displayed to users.
**Prevention:** In generic catch blocks, always log `Exception.Message` (never `Exception.ToString()` to avoid stack traces) securely using `NinjaScript.Log()` and output a generic string to the UI.
