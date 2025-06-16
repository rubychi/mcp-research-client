# MCP: Research (CLI Client)

This project is a hands-on implementation from the [MCP: Build Rich-Context AI Apps with Anthropic](https://www.deeplearning.ai/short-courses/mcp-build-rich-context-ai-apps-with-anthropic/).

It demonstrates how to use the Model Context Protocol (MCP) to build AI applications that can access tools, data, and prompts from external sources in a standardized way.

For the MCP server, see [mcp-research-server](https://github.com/rubychi/mcp-research-server).

## Overview

The Model Context Protocol (MCP) is an open protocol developed by Anthropic that standardizes how large language models (LLMs) access external tools and data. MCP uses a client-server architecture, making it easy to integrate new tools and connect to external systems such as arXiv, GitHub, Google Docs, or local files.

This project provides an MCP client chatbot that connects to MCP servers (as configured in `server_config.json`) and allows you to interact with their tools, resources, and prompts from the command line.

## Features

- **MCP Client Chatbot:** Connects to one or more MCP servers and exposes their tools, resources, and prompts interactively.
- **Server Configuration:** Easily configure which MCP servers to connect to via `server_config.json`.
- **Prompt and Tool Discovery:** List and use available tools and prompts from connected servers.
- **Interactive CLI:** Query, use tools, and execute prompts from the terminal.

## Project Structure

```
.
├── mcp_chatbot.py         # Main entry point: interactive MCP client chatbot
├── server_config.json     # MCP server connection configuration
├── pyproject.toml         # Project metadata and dependencies
├── uv.lock                # Dependency lock file
├── .python-version        # Python version specifier
├── .gitignore
├── .env.example          # Example environment variable file
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.11.11
- [uv](https://github.com/astral-sh/uv) (for dependency management)

### Installation

1. **Clone this repository:**
   ```bash
   git clone git@github.com:rubychi/mcp-research-client.git
   ```

2. **Create a virtual environment:**
   ```bash
   uv venv .venv
   ```

3. **Activate the environment:**
   ```bash
   source .venv/bin/activate
   ```

4. **Run the MCP Chatbot:**
   ```bash
   uv run mcp_chatbot.py
   ```

### Usage

- The chatbot will connect to the MCP servers specified in `server_config.json` and allow you to:
  - List available tools and prompts
  - Query resources (e.g., research topics, paper info)
  - Use tools and execute prompts interactively
- CLI commands:
  - `@folders` — List available research topics
  - `@<topic>` — Get information about a specific topic
  - `/prompts` — List available prompts
  - `/prompt <name> <arg1=value1>` — Execute a prompt with arguments
  - Type any query to interact with the connected LLM and tools
  - Type `quit` to exit

## Configuration

- Edit `server_config.json` to add or modify MCP server connections.
- Copy `.env.example` to `.env` in the project root and fill in your values (e.g., `ANTHROPIC_API_KEY`).

## References

- [Course: MCP: Build Rich-Context AI Apps with Anthropic (DeepLearning.AI)](https://www.deeplearning.ai/short-courses/mcp-build-rich-context-ai-apps-with-anthropic/)
- [Anthropic](https://www.anthropic.com/)
- [DeepLearning.AI](https://www.deeplearning.ai/)
