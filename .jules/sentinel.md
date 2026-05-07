## 2026-05-07 - Hardcoded public key in configuration file
**Vulnerability:** A hardcoded public API key (`pk_...`) was found in `context7.json`, which is tracked in version control.
**Learning:** Even though the file is for external indexing and the key may be a "public" key, hardcoding secrets in version-controlled config files (especially in a repository lacking backend source code that normally consumes such files) is an architectural oversight that can lead to unintended exposure and misuse of the key.
**Prevention:** Always use placeholder strings (e.g., `YOUR_PUBLIC_KEY`) in committed configuration or metadata files. Documentation and configuration files intended for external tools should not store active credentials directly in git history.
