# Yama Discord Bot (standalone)

AI chat (main-chat channel, web search, link reading), AI moderation, captcha verification panel and staff commands.

## Run on Railway
1. Push this folder to a GitHub repo, then Railway → New Project → Deploy from GitHub repo.
2. Variables tab: set `DISCORD_TOKEN` and `OPENROUTER_API_KEY`.
   (`firebase-applet-config.json` is already included, or set `FIREBASE_CONFIG` to its JSON instead.)
3. Start command is `npm start` (already set in `railway.json`).
4. Stop any other copy of this bot (Render, Vercel...). Two copies with one token = double replies.

## Discord developer portal
Bot → Privileged Gateway Intents: turn on **Server Members** and **Message Content**.

## Bot permissions
View Channels, Send Messages, Embed Links, Attach Files, Read Message History, Manage Messages,
Manage Roles, Manage Channels, Manage Nicknames, Moderate Members, Ban Members, Kick Members.
Put the bot's role **above** any role it must give or manage (verified role, members it mutes).

## First-time setup (in Discord, staff only)
- `?vcrole @role`, `?vpd <text>`, `?verifypanel #channel`  → verification
- `?aichat #channel` → main AI chat   |   `?aimod on`, `?modlog #channel` → AI moderation
- `?help` shows every command

## Local run
```
npm install
cp .env.example .env   # fill it in
npm start
```
