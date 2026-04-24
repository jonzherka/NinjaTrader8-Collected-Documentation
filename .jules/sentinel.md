## 2024-05-18 - UI Information Leakage in AddOns

**Vulnerability:** Detailed error messages and exception details (like stack traces or API error codes/messages) are directly assigned to UI elements (like WPF TextBlock or outputBox) in `other_uses_for_an_addon.md`.
**Learning:** Developers building NinjaTrader add-ons often incorrectly log errors directly to the user interface instead of a secure log. This is a common pattern in the NinjaTrader environment where `.Text` assignments to UI components map directly to API error payloads.
**Prevention:** Always log detailed error messages securely using `NinjaTrader.Code.Output.Process(..., PrintTo.OutputTab1)` and present generic, non-sensitive error messages to the UI elements (e.g. `An error occurred.`).
