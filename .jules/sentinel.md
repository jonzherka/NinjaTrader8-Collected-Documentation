## 2024-05-24 - Prevent internal API error disclosure to UI
**Vulnerability:** Information Disclosure
**Learning:** Returning raw API error messages directly to the UI (e.g., `errorMessage` returned from an asynchronous callback) can inadvertently expose internal architecture or system information to end users.
**Prevention:** Always sanitize API responses meant for the UI. Log the detailed error string safely using internal backend mechanisms (e.g., `NinjaTrader.Code.Output.Process`), and present only a generic, user-friendly message to the UI controls (e.g., "An error occurred while requesting bars.").
