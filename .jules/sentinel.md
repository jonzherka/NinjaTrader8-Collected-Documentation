## 2026-05-10 - [Information Leakage in UI Logs]

**Vulnerability:** Outputting exact exception messages to the UI.
**Learning:** In NinjaTrader C# examples, `NinjaTrader.Code.Output.Process` displays directly to user tabs. Writing exceptions here exposes implementation details.
**Prevention:** Use `NinjaScript.Log(..., LogLevel.Error)` for logging exact exceptions, and generic strings for `NinjaTrader.Code.Output.Process`.
