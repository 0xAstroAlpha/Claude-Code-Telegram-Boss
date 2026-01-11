<div align="center">

![Claude Code](https://img.shields.io/badge/Claude-Code-0075FF?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)

[![GitHub Sponsor](https://img.shields.io/badge/Sponsor-❤️-ea4aaa?style=for-the-badge&logo=github-sponsors)](https://github.com/sponsors/0xAstroAlpha)
[![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-☕-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/astroalpha)

[![GitHub Stars](https://img.shields.io/github/stars/0xAstroAlpha/Claude-Code-Telegram-Boss?style=flat-square&logo=github)](https://github.com/0xAstroAlpha/Claude-Code-Telegram-Boss/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/0xAstroAlpha/Claude-Code-Telegram-Boss?style=flat-square&logo=github)](https://github.com/0xAstroAlpha/Claude-Code-Telegram-Boss/network/members)
[![GitHub Issues](https://img.shields.io/github/issues/0xAstroAlpha/Claude-Code-Telegram-Boss?style=flat-square&logo=github)](https://github.com/0xAstroAlpha/Claude-Code-Telegram-Boss/issues)
[![Contributors](https://img.shields.io/github/contributors/0xAstroAlpha/Claude-Code-Telegram-Boss?style=flat-square&logo=github)](https://github.com/0xAstroAlpha/Claude-Code-Telegram-Boss/graphs/contributors)

# 🤖 Claude Code Telegram Boss

**Control Claude Code CLI remotely via Telegram**

*Turn your Telegram into a powerful remote coding terminal with Claude AI*

[Installation](#-installation) •
[Features](#-features) •
[Usage](#-usage) •
[Configuration](#️-configuration) •
[Security](#-security)

</div>

<img src="docs/ScreenShot.jpeg" alt="Claude Code Telegram Boss" width="600"/>

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🧠 **Persistent Sessions** | Conversations maintain context across messages |
| 📁 **File Navigation** | Browse directories with `/ls`, `/cd`, `/pwd` commands |
| 🔧 **Tool Integration** | Full access to Claude Code's toolkit (Read, Write, Bash, etc.) |
| 💬 **Interactive Q&A** | Inline buttons for quick responses to Claude's questions |
| 📊 **Real-time Progress** | See tool execution status with detailed previews |
| 🔐 **Enterprise Security** | User whitelist, path sandboxing, rate limiting |
| 📱 **Mobile-First** | Designed for on-the-go coding from your phone |

## 🚀 Installation

### Prerequisites

- **Python 3.10+** 
- **Claude Code CLI** installed and authenticated:
  ```bash
  npm install -g @anthropic-ai/claude-code
  claude login
  ```
- **Telegram Bot Token** from [@BotFather](https://t.me/BotFather)

### Quick Start

```bash
# Clone the repository
git clone https://github.com/0xAstroAlpha/Claude-Code-Telegram-Boss.git
cd Claude-Code-Telegram-Boss

# Install dependencies
pip install poetry
poetry install

# Configure environment
cp .env.example .env
# Edit .env with your settings

# Start the bot
./start_bot.sh
```

### Persistent Background Service (macOS)

```bash
# Copy LaunchAgent
cp com.vibecode.claude-bot.plist ~/Library/LaunchAgents/

# Load and start
launchctl load ~/Library/LaunchAgents/com.vibecode.claude-bot.plist
launchctl start com.vibecode.claude-bot
```

## 📖 Usage

### Commands

| Command | Description |
|---------|-------------|
| `/start` | Initialize bot and show welcome message |
| `/help` | Display available commands |
| `/new` | Start a fresh Claude session |
| `/continue` | Resume previous session |
| `/ls` | List files in current directory |
| `/cd <dir>` | Change working directory |
| `/pwd` | Show current directory |
| `/projects` | Browse available projects |
| `/status` | Check session status and usage |
| `/git` | Git integration menu |

### Natural Language

Simply chat with Claude naturally:

```
You: Create a Python FastAPI server with user authentication
Claude: I'll create that for you...

You: Add rate limiting to the endpoints
Claude: Done! I've added rate limiting using slowapi...
```

### File Uploads

Send code files or images directly to chat for:
- Code review
- Bug analysis
- Screenshot interpretation
- Documentation extraction

## ⚙️ Configuration

### Required Environment Variables

```env
# Telegram Configuration
TELEGRAM_BOT_TOKEN=your_bot_token_here
ALLOWED_USERS=["123456789"]  # Your Telegram user ID

# Working Directory
APPROVED_DIRECTORY=/path/to/your/projects
```

### Optional Settings

```env
# Security Options
TRUST_CLAUDE_COMPLETELY=false     # Bypass all validation
DISABLE_PATH_VALIDATION=false     # Allow access outside sandbox
DISABLE_DANGEROUS_PATTERN_CHECK=false  # Allow shell patterns

# Rate Limiting
RATE_LIMIT_REQUESTS=10
RATE_LIMIT_WINDOW_SECONDS=60

# Claude Tools
CLAUDE_ALLOWED_TOOLS=["Read", "Write", "Edit", "Bash", "Glob", "Grep", "LS"]
```

## 🔐 Security

### Multi-Layer Protection

1. **User Whitelist** - Only authorized Telegram users can interact
2. **Path Sandboxing** - Claude can only access approved directories
3. **Tool Validation** - Each tool call is validated before execution
4. **Rate Limiting** - Prevents abuse and controls costs
5. **Audit Logging** - All actions are logged for review

### Trust Modes

| Mode | Security Level | Use Case |
|------|---------------|----------|
| Default | 🔒 Maximum | Production environments |
| `DISABLE_PATH_VALIDATION=true` | ⚠️ Medium | Development with trusted users |
| `TRUST_CLAUDE_COMPLETELY=true` | 🔓 Minimal | Personal use only |

## 🏗️ Architecture

```
claude-code-telegram-boss/
├── src/
│   ├── bot/              # Telegram bot handlers
│   │   ├── handlers/     # Command & message handlers
│   │   ├── features/     # Optional features
│   │   └── utils/        # Formatting & utilities
│   ├── claude/           # Claude integration
│   │   ├── facade.py     # Main integration layer
│   │   ├── monitor.py    # Tool validation
│   │   └── session.py    # Session management
│   ├── config/           # Configuration
│   └── security/         # Auth, rate limiting, validators
├── data/                 # SQLite database
└── docs/                 # Documentation
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 💖 Support & Donations

If this project helps you, consider supporting development:

| Method | Address/Link |
|--------|--------------|
| 🇻🇳 **Vietnam** | Vietcombank: `0071001215286` (LE BA THANG) |
| 💳 **PayPal** | `wikigamingmovies@gmail.com` |
| 💚 **USDT (TRC20)** | `TNGsaurWeFhaPPs1yxJ3AY15j1tDecX7ya` |
| 💛 **USDT (BEP20)** | `0x463695638788279F234386a77E0afA2Ee87b57F5` |
| 💜 **Solana (SOL)** | `HkgpzujF8uTBuYEYGSFMnmGzBYmEFyajzTiZacRtXzTr` |

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Anthropic](https://www.anthropic.com/) for Claude AI
- [python-telegram-bot](https://python-telegram-bot.org/) for the excellent Telegram library
- [RichardAtCT/claude-code-telegram](https://github.com/RichardAtCT/claude-code-telegram) for inspiration

---

<div align="center">

**[⬆ Back to Top](#-claude-code-telegram-boss)**

Made with ❤️ by the Vibecoder community

</div>