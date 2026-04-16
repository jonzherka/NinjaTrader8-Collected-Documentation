## 2024-05-18 - UI Information Leakage Pattern in AddOn Error Handling

**Vulnerability:** In custom NinjaTrader AddOn development (specifically within `BarsRequest.Request` callbacks shown in documentation), API error codes and internal error messages were being directly bound/displayed to UI elements (like `outputBox.Text`).

**Learning:** Due to the event-driven and UI-heavy nature of NinjaTrader AddOns, it is a common anti-pattern for developers to write direct passthroughs of backend error states (`errorMessage`, `Exception.ToString()`) to WPF `TextBlocks` or `TextBoxes` for convenience, leading to potential data exposure, internal workings leakage, or path exposure to the end user.

**Prevention:** Always implement a secure boundary between backend error handling and the UI presentation layer in AddOn examples. Detailed exceptions and API errors should be securely logged via `NinjaTrader.Code.Output.Process(..., PrintTo.OutputTab1)`, while UI controls should only receive generic, non-sensitive error messages (e.g., "An error occurred").