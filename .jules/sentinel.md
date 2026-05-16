## 2026-05-16 - Prevent Information Leakage in Generic Catch Blocks
**Vulnerability:** Outputting `error.Message` in generic exception blocks to the UI via `NinjaTrader.Code.Output.Process()` risks leaking sensitive application state or stack trace details to end users.
**Learning:** In NinjaTrader Add-Ons, the UI Output tab is user-facing. `Output.Process` should only display safe, generic messages. Detailed exception information must be securely logged to the system Log tab using `NinjaScript.Log("message", LogLevel.Error)`.
**Prevention:** When handling exceptions, separate logging logic: use `NinjaScript.Log()` for detailed error recording and `NinjaTrader.Code.Output.Process()` with a hardcoded generic string for user feedback.
