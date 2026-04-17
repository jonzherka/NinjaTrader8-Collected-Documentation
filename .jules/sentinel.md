## 2024-05-15 - Prevent Error Information Leakage to WPF UI in Add Ons

**Vulnerability:** A WPF `TextBlock` control (`outputBox.Text`) in an Add On window example directly displayed raw API error messages (`errorMessage` parameter from a `BarsRequest` callback) which could expose sensitive path, internal system structure, or API details.
**Learning:** In WPF UI components like Add On tabs or custom windows, displaying raw generic exception or callback error messages directly to UI components creates an information leakage risk. Even seemingly benign data API errors can contain stack traces or sensitive internal paths.
**Prevention:** Always log detailed/raw error messages securely (e.g., using `NinjaTrader.Code.Output.Process(..., PrintTo.OutputTab1)` or `NinjaScript.Log()`) and provide a sanitized, generic error message to the user interface controls.
