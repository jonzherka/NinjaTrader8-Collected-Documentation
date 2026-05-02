## 2024-05-02 - Information Leakage via NinjaTrader Output Process
**Vulnerability:** Information Leakage in C# Examples
**Learning:** In NinjaTrader scripts, detailed exception messages were being directly outputted to the user interface using `NinjaTrader.Code.Output.Process()`. This leaks internal information. The proper pattern is to use `NinjaScript.Log(..., LogLevel.Error)` to log sensitive details to the system log, and output a generic, safe string to `Output.Process()`.
**Prevention:** Always verify that error outputs to the NinjaTrader UI (`Output.Process`) use generic messages. Detailed `Exception.Message` strings should only go to `NinjaScript.Log()`.
