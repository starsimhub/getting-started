# Getting started with AI-assisted development

## Claude Code in VS Code

[Claude Code](https://docs.anthropic.com/en/docs/claude-code) is Anthropic's AI coding assistant that runs directly in your terminal and IDE. It can read your codebase, edit files, run commands, and help you build and debug software.

### Installation

1. Install [Node.js](https://nodejs.org/) (v18+).
2. Install Claude Code:

   ```bash
   npm install -g @anthropic-ai/claude-code
   ```

3. In VS Code, install the [Claude Code extension](https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code).
4. Open the Claude Code panel (Ctrl+Shift+P, then "Claude Code: Open").
5. Follow the prompts to authenticate with your Anthropic account.

### Usage

- Open the Claude Code panel in VS Code and type your request in natural language.
- Claude Code can read and edit files, run terminal commands, search your codebase, and more.
- Use `/help` within Claude Code for a full list of commands.

## Installing the Starsim AI plugin

The [starsim-ai](https://github.com/starsimhub/starsim_ai) plugin gives Claude Code specialized knowledge about the Starsim framework -- including architecture, style conventions, and API patterns.

Install it with:

```bash
claude plugin add starsim-ai --url https://github.com/starsimhub/starsim_ai
```

Once installed, Claude Code will automatically use the plugin's skills when you're working on Starsim projects. This includes guidance on:

- Simulation setup and configuration
- Disease models, networks, and interventions
- Calibration and analysis
- Starsim coding style and conventions
