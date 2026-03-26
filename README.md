# NinjaTrader 8 Collected Documentation

Welcome to the **NinjaTrader 8 Collected Documentation** repository. This repository serves as a centralized, high-quality knowledge base for NinjaTrader 8 (NT8) development, primarily focusing on NinjaScript, C#, Add-Ons, and the core API.

It has been specifically structured and optimized for **[Context7](https://context7.com/)** to be used natively by AI agents, LLMs, and MCP (Model Context Protocol) servers like Cursor, Claude Code, and Windsurf.

## 🚀 Purpose

1. **Human Developers**: Provide an easy-to-read, well-structured markdown collection of NT8 development concepts, classes, and interfaces.
2. **AI Agents / Context7**: Serve as a strict, hallucination-free knowledge base that AI agents can query to generate accurate C# and NinjaScript code.

## 📂 Repository Structure

The documentation is organized by functional areas within NinjaTrader 8:

- **`3.0 Add On/`**: Comprehensive documentation on building Add-Ons, including UI integration, workspaces, tabs, custom controls, and core NinjaTrader components.
- **Root Files**: Contains the primary index files (e.g., `add_on.md`), Context7 configuration (`context7.json`), and the official NT8 Help Guide PDF.

### Key Sections:
- **Account Data**: Managing and subscribing to `Account` updates.
- **Connection**: Handling the `Connection` class for real-time and playback data.
- **Market Data**: Requesting history (`BarsRequest`), `FundamentalData`, `MarketDepth`, and more.
- **UI & Workspaces**: Interfaces like `INTTabFactory`, `IWorkspacePersistence`, and interacting with `NTWindow`, `NTTabPage`, and the `ControlCenter`.
- **Strategies**: Deep dives into `StrategyBase` and starting/stopping ATM strategies programmatically.

## 🛠️ Context7 Compatibility

This repository has been formatted strictly for **Context7 Verification**.
- **Frontmatter**: Every `.md` document contains YAML frontmatter defining its `title`, `pathName`, `parent`, `section`, and `status`.
- **UI Components**: Employs specific tags like `{% callout type="note" %}` and `{% table %}` to ensure beautiful rendering on Context7.com and clear parsing by AI tools.
- **AI Instructions**: Please see `AGENTS.md` for explicit rules on how LLMs should navigate and parse the C# snippets contained herein.

## 📄 License

This repository is licensed under the MIT License. See the `LICENSE` file for details.
