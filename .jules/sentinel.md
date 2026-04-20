## 2024-05-18 - API Error Details Leakage via UI

**Vulnerability:** The sample AddOn code in `other_uses_for_an_addon.md` was found to be exposing detailed API error codes and messages directly to the UI elements (`outputBox.Text`) when a BarsRequest failed. This allows sensitive system or API details to be leaked to end-users.
**Learning:** Found an instance where an error state during a request caused the error response (including backend details via API variables) to be printed directly onto a UI control. This presents a direct violation of the principle to fail securely without leaking internal information.
**Prevention:** Always log detailed error outputs (such as `errorCode` and `errorMessage` or `Exception.Message`) using secure internal logging (e.g., `NinjaTrader.Code.Output.Process(..., PrintTo.OutputTab1)`) and output a generic user-friendly message to UI controls.
