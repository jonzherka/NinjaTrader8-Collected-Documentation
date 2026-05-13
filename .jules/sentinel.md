## 2026-05-13 - Exception Leakage in NinjaTrader UI Output
**Vulnerability:** Exact exception messages were being logged to the UI output tab using `NinjaTrader.Code.Output.Process`, which can lead to information disclosure.
**Learning:** In NinjaTrader snippets, it is common to output execution details to the UI. However, catch blocks must avoid printing the raw exception messages to these UI tabs.
**Prevention:** Use `NinjaScript.Log(error.Message, LogLevel.Error)` for accurate auditing of errors and provide a generic fallback message to the UI via `Output.Process` to protect internal system context.
