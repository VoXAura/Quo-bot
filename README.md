![Language](https://img.shields.io/badge/Lang-Python%203.13.7-red)
![discord.py Version](https://img.shields.io/badge/Lib-Discord.py%202.6.0-red)
![Db](https://img.shields.io/badge/Db-PostgreSQL-red)
![Library](https://img.shields.io/badge/ORM-Tortoise%20ORM-red)

<img align="right" src="https://cdn.discordapp.com/avatars/1380834150428442704/a83b721a79ce566b9f3c4addc978370d.webp?size=2048" alt="Logo" width="25%" style="border-radius: 50%;">

## Quo - The Ultimate Discord Bot for Esports Management

Quo is the ultimate open-source Discord bot designed specifically for esports servers. Our goal is to empower esports communities by simplifying and streamlining the organization and management of scrims, tournaments, and other events.
> The source here is completed and almost working codebase of original src.

---
## Quo - History :
Though Quo might look different in several aspects, the core codebase and every single part of it — every line of code and even the smallest changes — are all brought to us by a legend who is no longer with us. However, he passed down a legacy that we strive to protect until the end, no matter what. Our first iteration might be different from what we are now, but we have grown tremendously and learned so much along the way. [Rohit (Quotient's developer)](https://github.com/deadaf) may not be with us anymore, yet the code he left behind will continue to live on forever. We will do everything in our power to protect that legacy, continue contributing to this community, and forever keep Rohit's project alive in people's memory.

# "How is it Connected to Quotient" :
Quotient was the premier esports bot that seemed like something crafted through countless nights of effort and support from millions of users in the esports community. After hearing the unfortunate and shocking shutdown of the original ["Quotient-bot"](https://github.com/quotientbot/quotient), just like all those close to the developer, we were saddened and felt helpless at that moment. However, not long ago, we had the idea of trying to run Quotient on our own (since the bot was already open-sourced and essentially complete, except for a few fixes).
[I (Quo's developer)](https://github.com/VoXAura) initially sought help from fellow developers to get this bot running independently, but none came forward to help, so I had to tackle it alone. It took time, but I was satisfied with the result, and thus Quotient's open-sourced code laid the foundation for the beginning of "Quo."

## 🚀 Installation & Setup

### 1. **Clone the Repository**
```bash
git clone https://github.com/VoXAura/Quo-Bot.git
cd Quo-Bot
```

### 2. **Install Python Dependencies**
- Recommended Python version: **3.11**
- Install with pip:
```bash
pip install -r requirements.txt
```
- Or with Poetry:
```bash
pip install poetry
poetry install --no-dev
```

#### **Running on External Hosting Sites (e.g., Railway, Replit, Heroku, etc.)**
- If you face issues spliting the main file & downloading requirements, install them in this order:
  1. `pip install -r basicrequire.txt`
  2. `pip install -r dbrequire.txt`
  3. `pip install -r minimalrequire.txt`
  4. `pip install -r requirements.txt`
- After all requirements are installed, you can change the config for requirements (if your host allows) to `rrs.txt` for faster or custom installs.

### 3. **Configure Environment (via `src/config.py`)**
- All configuration is done directly in `src/config.py`.
- Set your PostgreSQL, Discord token, webhook URLs, and other settings in this file.
- Example fields to set:
```
POSTGRESQL = { ... }
DISCORD_TOKEN = "..."
SHARD_LOG = "..."
ERROR_LOG = "..."
PUBLIC_LOG = "..."
SERVER_PORT = 1234
SOCKET_URL = "..."
SOCKET_AUTH = "..."
PREMIUM_ROLE = ...
SERVER_ID = ...
VOTER_ROLE = ...
OCR_SPACE_API_KEY = "..."
```

### 4. **Database Setup**
- The bot uses **PostgreSQL**. Make sure your database is running and accessible.
- Tortoise ORM will auto-generate schemas on first run.
- **Tip:** You can use [Supabase](https://supabase.com/) for easy PostgreSQL hosting.

### 5. **Run the Bot**
```bash
python src/bot.py 
```
or 
```bash
python run.py 
```

### 6. **(Optional) Run with Docker**
- Build and run with Docker:
```bash
docker build -t quo-bot .
docker run quo-bot
```

---

## 🧩 Features & Commands

Quo is modular! Each feature is a cog. Here are the main modules and their highlights:

### **Esports Management** (`cogs.esports`)
- `smanager` - Scrims manager: open/close registration, slotlist, reminders, ban/allow teams, etc.
- `tourney` - Tournament manager: create/manage tournaments, slot management, etc.
- `idp` - Share room ID/password with auto-delete.
- `easytag` - Easy teammate tagging in registration.
- `tagcheck` - Enforce mention requirements in channels.
- `slotmanager` - Advanced slot management for scrims/tourneys.
- `banlog` - Ban logging for scrims.
- `ssverify` - Smart screenshot verification for results.
- `ssidp` - Automatic IDP panel setup for ocr enabled screenshot IDP fetcher
- `senddrop` - Used to send multiple drop panels in a scrims.

### **Events & Logging** (`cogs.events`)
- Command logging, error handling, voting, scheduled tasks, and more.

### **Moderation** (`cogs.mod`)
- `selfclean` - Clean bot messages.
- `clear` - Purge messages (by user, embeds, files, bots, etc.).
- `kick`, `ban`, `unban` - Member moderation.
- `role`/`rrole` - Add/remove roles to users, humans, bots, or all.
- `lock`/`unlock` - Lockdown channels or server.
- `maintenance` - Maintenance mode for the server.

### **Premium** (`cogs.premium`)
- `pstatus` - Check premium status.
- `premium` - View/claim premium.
- `pmanage` - Manage premium (status, info, transfer, claim).

### **Miscellaneous** (`cogs.quomisc`)
- `source` - Get source code link for commands.
- `invite` - Bot/server invite links.
- `setup`/`qsetup` - Setup the bot in your server.
- `about`, `stats`, `contributors` - Bot info, stats, contributors.
- `prefix`, `color`, `footer` - Customization commands.
- `dashboard` - Dashboard link.
- `report` - To report any bugs or issues.
- `sticky` - To set custom sticky message(s).

### **Dev-Only** (`cogs.quomisc.dev`)
- `listservers` - To list servers in which bot is present.
- `leaveserver` - To leave(s) servers in which bot is via argument such as "server_id" & "serial_order".
- `blacklist` - add or remove users to blacklist.
- `sync` - to sync slash cmds globally or guild wise.
- `botupdate` - to push bot update globally.
- `cmds` - Number of times you have used cmds of bot.
- `history` - to view last 15 used cmd throughout the bot globally.
- `pctl` or `premiumctl` - Premium control commands.
- `rempremium` - Used to remove premium access from users & servers.
  
### **Utility** (`cogs.utility`)
- `reminder` - Set reminders for yourself.
- `autorole` - Manage autoroles for humans/bots.
- `embed`, `quickembed` - Send custom embeds.
- `snipe` - Snipe deleted messages.
- `tag` - Custom tags (create, edit, delete, claim, search, stats, etc.).
- `category` - Manage channel categories (delete, hide, unhide, nuke).
- `autopurge` - Auto-purge messages in channels.

### **Reminders** (`cogs.reminder`)
- Background reminders and timer management for users and events.

---

## ⚠️ Potential Issues & Troubleshooting

- **Emoji errors:**
  - If you see errors related to emojis, you can configure or update emoji IDs and names in `src/utils/emote.py`.
  - Some emoji issues may be internal to Discord or the bot; contact support if unsure.
- **Database issues:**
  - Ensure your PostgreSQL configuration in `src/config.py` is correct.
  - You can use [Railway](https://railway.app/) for easy database hosting.
- **Scrims-related errors:**
  - Some advanced scrims functions may error due to Discord API or setup. If you encounter issues, [contact support](https://dsc.gg/quohq) for help.
- **Tournament CSV Generation:**
  - To configure tournament CSV file generation, you must change the server/channel ID in `src/cogs/esports/views/tourney/main.py` at **line 300**.
  - Make sure the channel ID you set exists in your server and the bot is present in that channel, or CSV export will fail.

---

## 🏗️ Project Structure
```
quo/
  src/
    bot.py           # Main entry point
    config.py        # Main config
    cogs/            # All bot features (cogs)
    core/            # Core bot logic
    models/          # Database models
    utils/           # Utilities (see emote.py for emoji config)
    ...
```

---

## 📝 How to Contribute
- Open an issue for discussion before submitting a PR.
- Join our [Support Server](https://dsc.gg/quohq) for help or to chat with the devs.

---

## 📞 Contact & Support
- [Support Server](https://dsc.gg/quohq)
- [Invite Quo to your server](https://discord.com/oauth2/authorize?client_id=746348747918934096&scope=applications.commands%20bot&permissions=536737213566)
- Contact bot developer [VoXAura (1384911821290340352)](https://discord.com/users/1384911821290340352) to use the public Quo bot in your server.

---

## 🪪 License
This project is licensed under the [Mozilla Public License 2.0 (MPL-2.0)](https://www.mozilla.org/en-US/MPL/2.0/). See the [LICENSE](https://github.com/VoXAura/Quo-bot/blob/main/LICENSE) file for details.

---

### Contributors 👥
<a href="https://github.com/VoXAura/Quo-Bot/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=VoXAura/Quo-Bot" />
</a>


