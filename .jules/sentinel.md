## 2024-05-18 - Prevent Leaking Exception Details
**Vulnerability:** Exception details were logged/printed directly to the output without sanitizing/suppressing them. Specifically, `error.ToString()` was used, which exposes stack traces and potentially internal code or variable state in an application.
**Learning:** Raw exception strings should never be logged or displayed to user-facing or debug-facing interfaces where they can be accessed improperly.
**Prevention:** Use `error.Message` or custom error messages instead of `.ToString()` when handling exceptions.
