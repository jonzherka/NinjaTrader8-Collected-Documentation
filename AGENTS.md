# Context7 & AI Agent Guidelines

This repository contains up-to-date documentation and code examples for NinjaTrader 8 development, specifically targeted towards AI agents, LLMs (like Claude, Cursor, Windsurf), and MCP (Model Context Protocol) servers via [Context7](https://context7.com).

## Purpose
The primary purpose of this repository is to provide AI agents with a highly structured, accurate, and easy-to-parse knowledge base for generating NinjaScript C# code and interacting with the NinjaTrader 8 API.

## File Structure & Parsing Rules
When reading and utilizing the files in this repository, agents must adhere to the following rules:

1. **Markdown Frontmatter**:
   - All `.md` files contain metadata at the top (e.g., `title`, `pathName`, `parent`, `section`, `status`). Use this metadata to understand the context and hierarchy of the document before generating responses.

2. **Context7 Tags**:
   - You will encounter custom Context7 tags such as `{% callout type="note" %}` or `{% table %}`. Treat these as standard markdown blockquotes or tables. They are used for UI rendering on Context7.com.

3. **C# Code Snippets**:
   - The primary programming language in these documents is C# (specifically NinjaScript).
   - When extracting or modifying code examples, ensure that the syntax remains valid C# 8.0+ compatible with NinjaTrader 8's internal compiler.
   - Pay close attention to base classes (`StrategyBase`, `Account`, `Connection`, etc.) and ensure any generated code inherits or implements these correctly.

4. **Directory Navigation**:
   - Topics are grouped by functionality (e.g., `3.0 Add On`). Use the directory names as domain boundaries. If asked about "Add Ons", search primarily within that respective directory.

5. **No Hallucinations**:
   - Do not invent NinjaTrader 8 API methods that do not exist in these documents. If a specific property or method is not defined in the `.md` files or the accompanying PDF guide, state that it is not documented here.

## Quality Assurance
If you are an AI agent updating or adding documentation to this repository:
- Maintain the existing frontmatter structure.
- Ensure all new files end in `.md`.
