## 2024-04-27 - UI Information Leakage in Add-Ons

**Vulnerability:** NinjaTrader add-ons displaying detailed API errors (including error codes and internal messages) directly to UI elements (e.g., `outputBox.Text = errorMessage;`) instead of securely logging them.

**Learning:** When building custom Add-On UI windows in NinjaTrader, errors are sometimes directed to the UI output rather than the application's standard log window. This leaks internal state, API details, and potentially sensitive system information to end users.

**Prevention:** Always log detailed exceptions and API error messages securely using `NinjaTrader.Code.Output.Process(..., PrintTo.OutputTab1)`. Only display generic, non-sensitive error messages to UI controls (like TextBoxes or TextBlocks) bound to user-facing windows.
