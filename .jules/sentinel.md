## 2026-05-05 - Fix Information Leakage in UI

**Vulnerability:** Detailed exception messages were being logged directly to the UI using `NinjaTrader.Code.Output.Process()`. This can leak sensitive internal information, stack traces, or other internal configurations when connections fail.
**Learning:** In NinjaTrader scripts/AddOns, avoid directly printing the contents of caught Exceptions to UI elements or standard output tabs (e.g. via `NinjaTrader.Code.Output.Process`). This is a recurring pattern where error messages expose internal details.
**Prevention:** Always use `NinjaScript.Log(error.Message, LogLevel.Error)` to securely log the specific exception message for internal debugging, and then display a generic, non-sensitive error message (e.g., "Could not connect. An error occurred.") to the UI via `NinjaTrader.Code.Output.Process()`.
