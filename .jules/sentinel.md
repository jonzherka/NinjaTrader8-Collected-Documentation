## 2024-05-24 - AddOn UI Information Leakage Pattern

**Vulnerability:** Detailed API/system error messages (like `errorMessage` from `BarsRequest` failures) were being output directly to AddOn UI elements (e.g. `outputBox.Text = string.Format(..., errorCode, errorMessage)`).
**Learning:** In NinjaTrader UI/AddOn contexts, it's very easy to accidentally leak sensitive internal or provider errors directly to user-facing WPF controls instead of standard logs.
**Prevention:** Always log detailed error messages (including exceptions and provider errors) using `NinjaTrader.Code.Output.Process` with `PrintTo.OutputTab1` (or equivalent secure logging) and display only generic, safe messages to any custom UI controls.
