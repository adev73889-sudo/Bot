# Yama Discord Bot (standalone)

AI chat (main-chat channel, web search, link reading), AI moderation, captcha verification panel and staff commands.

## Run on Railway
1. Push this folder to a GitHub repo, then Railway → New Project → Deploy from GitHub repo.
2. Variables tab: set `DISCORD_TOKEN` and `OPENROUTER_API_KEY`.
   (`firebase-applet-config.json` is already included, or set `FIREBASE_CONFIG` to its JSON instead.)
3. Start command is `npm start` (already set in `railway.json`).
4. **Run only ONE copy of the bot** (stop Render/Vercel/etc). Two copies = double replies. The code has guards, but one copy is the safe setup.

## Discord developer portal
Bot → Privileged Gateway Intents: turn on **Server Members** and **Message Content**.

## Bot permissions
View Channels, Send Messages, Embed Links, Attach Files, Read Message History, Manage Messages,
Manage Roles, Manage Channels, Manage Nicknames, Moderate Members, Ban Members, Kick Members.
Put the bot's role **above** any role it must give or manage (verified role, members it mutes).

## First-time setup (in Discord, staff only)
- `?vcrole @role`, `?vpd <text>`, `?verifypanel #channel`  → verification
- `?aichat #channel` → main AI chat   |   `?aimod on`, `?modlog #channel` → AI moderation
- `?aichat on|off` → AI chat on/off (moderation stays live) · `?aimod links on|off`, `?aimod spam on|off`, `?linkallow add <domain>`
- `?help` shows every command

## Games (everyone)
- `start chess` or `?chess` → pick **vs AI** or **PvP** (both players confirm). A match channel is created that everyone can watch but only the two players can type in. Type moves like `e2e4`, `e4`, `Nf3`, `O-O` or `resign`.
- `start coinflip` or `?coinflip` → same lobby flow, best of 3.
- The bot needs **Manage Channels**. If the bot restarts mid-game, delete the leftover `chess-...` / `coinflip-...` channel by hand.

## Notes
- The AI only answers when you @mention it, reply to it, or call it by name at the start of a message.
- Reading images/videos/PDFs and making images use OpenRouter vision/image models (`VISION_MODEL`, `IMAGE_MODEL`). Change them if a model name stops working.

## Local run
```
npm install
cp .env.example .env   # fill it in
npm start
```
