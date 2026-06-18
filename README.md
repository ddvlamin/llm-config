# AI Assistant Configurations

A centralized repository for managing configurations for multiple AI assistant CLIs using [GNU Stow](https://www.gnu.org/software/stow/).

## Supported CLIs
- **Claude Code CLI**: Global config in `~/.claude/`
- **Mistral Vibe CLI**: Global config in `~/.vibe/`
- **Codex CLI**: Global config in `~/.codex/`
- **Gemini CLI**: Global config in `~/.gemini/`
- **OpenCode CLI**: Global config in `~/.config/opencode/`

## Prerequisites
- [GNU Stow](https://www.gnu.org/software/stow/) must be installed.
  - macOS: `brew install stow`
  - Linux: `sudo apt install stow` (or equivalent)

## Usage

### 1. Clone the repository
```bash
git clone https://github.com/ddvlamin/llm-config.git
cd llm-config/.ai-dotfiles
```

### 2. Apply configurations
To symlink all configurations to your home directory:
```bash
stow claude vibe codex gemini
```

To apply only specific ones:
```bash
stow claude
stow vibe
```

### 3. Verification
Verify the symlinks were created correctly:
```bash
ls -la ~ | grep -E ".claude|.vibe|.codex|.gemini"
```

## Security Warning
**NEVER** commit your API keys or sensitive data.
- Claude: `.claude/.claude.json` is ignored.
- Vibe: `.vibe/.env` is ignored.
- Codex: `.codex/auth.json` is ignored.
- Gemini: `.gemini/auth.json` and `.gemini/.env` are ignored.
- Antigravity: `.gemini/anitgravity-cli/antigravity-oauth-token`

Keep your secrets in these local-only files.
