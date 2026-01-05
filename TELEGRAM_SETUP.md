# CLAWDBOT Telegram Setup Guide

## Quick Start

```bash
# Install is complete. Run the gateway:
./scripts/clawdbot gateway --port 18789
```

## Create Your Telegram Bot

1. **Open Telegram** and search for @BotFather
2. **Send `/newbot`** to create a new bot
3. **Follow the prompts:**
   - Name: "My ClawDBot" (or whatever you want)
   - Username: Must end in "bot" (e.g., "my_clawdbot_bot")
4. **Copy the API token** (format: `123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11`)

## Configure Your Bot

Edit `~/.clawdbot/clawdbot.json` and replace the placeholder:

```json
{
  "telegram": {
    "enabled": true,
    "botToken": "YOUR_ACTUAL_BOT_TOKEN_HERE"
  }
}
```

## Bot Settings (Recommended)

In BotFather, run these commands for better experience:

```
/setprivacy          → Disable (so bot sees all messages in groups)
/setjoingroups       → Enable (so bot can be added to groups)
/setcommands         → Send the commands list below
```

Suggested commands for BotFather:
```
start - Start a conversation
help - Show help message
session - Create a new session
status - Show connection status
```

## Run the Gateway

```bash
# Terminal 1: Start the gateway
./scripts/clawdbot gateway --port 18789

# Terminal 2: Send a test message (after configuring the bot)
./scripts/clawdbot send --to @your_bot_username --message "Hello from ClawDBot!"
```

## Testing Your Bot

1. Start the gateway: `./scripts/clawdbot gateway --port 18789`
2. Open Telegram and message your bot with `/start`
3. The bot should respond!

## Useful Commands

```bash
# Health check
./scripts/clawdbot health

# View status
./scripts/clawdbot status

# Send a message
./scripts/clawdbot send --to +15551234567 --message "Hello!"

# Run in development mode (isolated config)
./scripts/clawdbot --dev gateway --port 19001
```

## Files

- Config: `~/.clawdbot/clawdbot.json`
- State: `~/.clawdbot/state/`
- Binary: `/Users/bioinfo/apps/clawdbot/dist/entry.js`
- Launcher: `/Users/bioinfo/scripts/clawdbot`
