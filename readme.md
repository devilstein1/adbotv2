<div align="center">

<img src="https://i.pinimg.com/736x/e7/d2/47/e7d24774fc8864ec7b22eff90d58bada.jpg" width="200" />

# 📢 Telegram Adbot

**Automated ad forwarding & broadcasting for Telegram, at scale.**

[![Python](https://img.shields.io/badge/Python-3.13-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Telethon](https://img.shields.io/badge/Telethon-MTProto-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://docs.telethon.dev/)
[![pyTelegramBotAPI](https://img.shields.io/badge/pyTelegramBotAPI-Bot%20API-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://github.com/eternnoir/pyTelegramBotAPI)

---

A Telegram bot that automatically forwards or sends your ad messages to **hundreds of groups and forum topics** using your own Telegram accounts. Give it a message link, pick a send mode, and let it handle the rest on full autopilot.

[Get Access](#-get-access) · [Features](#-features) · [Quick Start](#-quick-start) · [Commands](#-commands--reference) · [Admin Guide](#-admin-guide)

---

### 👤 Author

<a href="https://t.me/rejerk"><img src="https://img.shields.io/badge/Telegram-@rejerk-26A5E4?style=for-the-badge&logo=telegram&logoColor=white" /></a>

### 💰 Get Access

This is a **premium tool**. To purchase access, contact the vault bot on Telegram:

<a href="https://t.me/stein_vault_bot"><img src="https://img.shields.io/badge/Buy%20Access-@stein__vault__bot-00C853?style=for-the-badge&logo=telegram&logoColor=white" /></a>

</div>

---

## ✨ Features

- 🔁 **Auto-forward or copy-send** ads to all your joined groups & forum topics
- 🧑‍🤝‍🧑 **Multi-account support** letting you run different ads on different accounts simultaneously
- 🎯 **Smart targeting** with auto-scan or saved campaign lists
- ⚡ **Parallel mode** to blast 10 groups at once for maximum speed
- 📡 **Live tracking** with real-time delivery links in a tracking channel
- 📋 **Log bot integration** for full delivery reports via your own bot
- 🔄 **Auto-resume** that survives crashes & reboots and picks up right where it left off
- 🛡️ **Spam protection** with SpamBot checks before every run and auto-pause on FloodWait
- 🧰 **Campaign system** to save & reuse target lists with `/set`, `/platform`, `/reset`

---

## 📦 Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | ![Python](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white) |
| Userbot Client | ![Telethon](https://img.shields.io/badge/Telethon-MTProto-2CA5E0?logo=telegram&logoColor=white) |
| Bot Framework | ![pyTelegramBotAPI](https://img.shields.io/badge/pyTelegramBotAPI-Bot%20API-26A5E4?logo=telegram&logoColor=white) |
| Timezone | `pytz` |

---

## 🚀 Quick Start

```bash
# Clone the repo
git clone https://github.com/devilstein1/adbotv2.git
cd adbotv2

# Install dependencies
pip install -r requirements.txt

# Run the bot
python adbotv2.py
```

On first run you'll be prompted for:
1. **Bot token** from [@BotFather](https://t.me/BotFather)
2. **Owner ID** (your numeric Telegram user ID)
3. **Owner username** (your Telegram @handle)

---

# 📖 User Guide

<details>
<summary><b>🔐 Before You Begin</b></summary>

You need two things before you can use this bot:

1. **Premium access** : the bot owner must activate your account. Without premium, the bot will reply with _"You need premium to use this bot."_ every time you try anything. Contact the owner to get a plan.

2. **At least one Telegram account added to the bot** : this is the account that will actually send your ads in groups. It's your personal Telegram account (or a secondary one). You'll log into it through the bot using OTP.

</details>

<details>
<summary><b>💎 Premium Plans</b></summary>

Your plan determines how many Telegram accounts you can connect to the bot at the same time. Each account runs independently, so you can run different ads on different accounts simultaneously.

| Plan | Max Accounts | What it means |
|------|-------------|---------------|
| 🥉 Bronze | 1 | You can add 1 Telegram account and run 1 ad at a time |
| 🥈 Silver | 2 | You can add 2 accounts and run 2 ads at the same time |
| 🥇 Gold | 3 | 3 accounts, 3 simultaneous ads |
| 💎 Platinum | 4 | 4 accounts, 4 simultaneous ads |
| ⚙️ Custom | 1 to 12 | Owner decides how many accounts you get |

Each account is called a "slot." If you have Silver, you have Slot 1 and Slot 2. Each slot can hold one Telegram account and run one ad independently.

Your premium also has an **expiry date**. You'll receive a warning 6 hours before it expires. When it expires, all your running ads stop immediately and you lose access until the owner renews it.

</details>

<details>
<summary><b>📱 The Main Menu (<code>/start</code>)</b></summary>

Send `/start` to the bot at any time. This opens the main menu and also **resets any ongoing setup process** (if you got stuck mid-setup, `/start` cleans everything up).

The menu shows these buttons:

```
┌──────────────────┬──────────────────┐
│  ➕ Add account   │  ⚙️ Settings     │
├──────────────────┴──────────────────┤
│            🤖 Adbot                  │
├──────────────────┬──────────────────┤
│  ▶️ Start All    │  ⏹ Stop All      │
└──────────────────┴──────────────────┘
```

| Button | Description |
|--------|-------------|
| **➕ Add account** | Opens the account login flow. Add a real Telegram account by phone number + OTP |
| **⚙️ Settings** | Log bot setup, username, message delay, cycle delay |
| **🤖 Adbot** | Main feature. Shows all account slots with live status (🟢/🔴) |
| **▶️ Start All** | Bulk-restart all accounts using their last-used settings |
| **⏹ Stop All** | Emergency stop. Kills every running ad across all accounts |

</details>

<details>
<summary><b>➕ Adding a Telegram Account</b></summary>

This is the first thing you need to do after getting premium.

### Step 1 : Tap ➕ Add account
If you've already used all your plan slots, you'll see: _"You've reached your plan limit (N account(s))."_ You need to either upgrade your plan or remove an existing account.

### Step 2 : Send your phone number
Type the full phone number **with country code**. Examples:
- `+919876543210` (India)
- `+12025551234` (USA)
- `+447911123456` (UK)

**What if this number was already added before?**
The bot will warn you: _"This session already exists."_ You'll see two options:
- **Make Forcefully** deletes the old session and creates a new one. If that account was running an ad, the ad stops.
- **Cancel** goes back with no changes made.

### Step 3 : Enter the OTP
Telegram sends a login code to the phone number (usually via Telegram itself, or SMS). Enter the numeric code in the bot. Just the digits, nothing else.

### Step 4 : 2FA password (only if enabled)
If your Telegram account has two-step verification turned on, the bot will ask for your 2FA password. Type it and send.

### Step 5 : Done
The bot says _"✅ Session is ready."_ Your account is now connected. The bot automatically:
- Sets the account's bio to something like _"Adbot For @yourusername. Powered By @ownerusername"_
- Joins any group folders the owner has configured

You can now go to 🤖 Adbot and start running ads with this account.

</details>

<details>
<summary><b>🤖 The Adbot Panel (Account Slots)</b></summary>

Tap **🤖 Adbot** from the main menu. You'll see a list of your account slots. Each slot shows:

- **🟢** = this account is currently running an ad
- **🔴** = this account is idle (not running)
- **Phone number** = the phone number of the connected account (or just a slot number if empty)

**Example** (Gold plan with 3 slots, slot 1 running):
```
🟢 +919876543210
🔴 +447911123456
🔴 3
◀ Back
```

Tap any slot to open its management panel.

</details>

<details>
<summary><b>🎛️ Per-Account Management Panel</b></summary>

When you tap an account slot, you see this panel:

```
┌──────────────────────────────────────┐
│            📤 Run ADS                │
├──────────────────────────────────────┤
│       🟢 Running / 🔴 Stopped       │
├──────────────────┬───────────────────┤
│    ✏️ Name       │     📝 Bio        │
├──────────────────┼───────────────────┤
│    🖼 Photo      │     📡 Track Ch   │
├──────────────────┼───────────────────┤
│    ▶️ Fwd Link   │     📋 Send Link  │
├──────────────────┴───────────────────┤
│             ◀ Back                   │
└──────────────────────────────────────┘
```

Here is what every button does:

### 📤 Run ADS
Starts the full ad run setup wizard. You configure a message link, choose send/forward mode, set cycles, pick targets, and launch. Full step-by-step walkthrough in the next section.

**Cannot tap this if the slot is already running.** You'll see: _"This Adbot slot is already running."_ Stop it first.

### 🟢 Running / 🔴 Stopped (Toggle)
- If the account is **running** (🟢), tapping this **stops** it immediately. The ad delivery halts and the button switches to 🔴.
- If the account is **stopped** (🔴), tapping this does nothing. To start it, use 📤 Run ADS or ▶️ Start All.

### ✏️ Name
Changes the **first name** and **last name** on the Telegram account.

After you tap this, the bot asks you to send the new name. You have two options:
- Send just a first name: `John`
- Send first + last name separated by `|` or a new line: `John|Smith` or:
  ```
  John
  Smith
  ```

The change happens instantly on Telegram. Anyone looking at this account's profile will see the new name.

### 📝 Bio
Changes the **bio / about text** on the Telegram account.

After you tap this, send any text and it becomes the account's bio. Maximum 70 characters (Telegram's limit). Example:
```
Promoting the best deals | DM for collab
```

This overwrites whatever bio was there before, including the auto-set "Adbot For @..." bio.

### 🖼 Photo
Changes the **profile picture** on the Telegram account.

After you tap this, **send a photo** (not a file, not text, an actual photo from your gallery or camera). The bot uploads it as the account's new profile picture.

**Important:** Send a photo as a photo (the image preview way), not as a document/file.

### 📡 Track Ch (Track Channel)
Sets a **tracking channel** for this specific account.

**What is a tracking channel?**
It's a Telegram channel where the bot posts a clickable link every time an ad is successfully sent to a group. You get a live feed of every delivery.

**How to set it up:**
1. Create a Telegram channel (or use an existing one)
2. Make sure the **Telegram account in this slot** is an admin of that channel (not your main account, the account connected to the bot)
3. Tap 📡 Track Ch
4. Send the channel's @username (e.g. `@mytrackingchannel` or just `mytrackingchannel`)

**What happens after:**
Every time this account sends an ad to a group, a message like this appears in your tracking channel:
```
Sent: https://t.me/somegroup/12345
```
You can tap that link to go directly to the sent message and verify it was posted.

**If the track channel send fails** (e.g. account is no longer admin), it's silently ignored. Your ad delivery is NOT affected.

### ▶️ Fwd Link (Forward via Message Link)
A **quick-start shortcut** that immediately begins forwarding a message to all groups.

1. Tap this button
2. Send a `t.me/...` message link (e.g. `https://t.me/mychannel/456`)
3. The bot immediately starts **forwarding** that message to all groups this account has joined, running forever (infinite cycles) until you stop it

No need to go through the full Run ADS wizard. Useful when you want to quickly launch a forward campaign.

**Cannot use this if the slot is already running.** Stop it first.

### 📋 Send Link (Copy-Send via Message Link)
Exactly like ▶️ Fwd Link above, but instead of **forwarding** (which shows "Forwarded from Channel Name"), it **copies** the message content and sends it as a brand new message. Recipients don't see where it came from.

1. Tap this button
2. Send a `t.me/...` message link
3. The bot immediately starts **copy-sending** that message to all groups, running forever until you stop it

**Difference between Forward and Send:**
- **Forward** = recipients see _"Forwarded from @yourchannel"_ at the top. Your channel gets exposure.
- **Send (Copy)** = the message appears as if the account typed it themselves. No forwarding label. Looks more natural but your channel name isn't shown.

</details>

<details>
<summary><b>📤 Running Ads (The Full Setup Wizard)</b></summary>

This is what happens when you tap **📤 Run ADS** on any account slot.

### Step 1 : Provide the ad message

The bot says: _"📤 Send Link of post or forward message here."_

You have two ways to provide your ad:

**Option A : Send a link**
Copy the link to any Telegram message and paste it. Examples:
- Public channel message: `https://t.me/mychannel/123`
- Private channel message: `https://t.me/c/1234567890/456`

**Option B : Forward the message**
Open the message in Telegram, tap "Forward", and forward it to this bot. The bot automatically extracts the link from the forwarded message.

### Step 2 : Choose Send or Forward mode

Two buttons appear:
- **📤 Send** copies the text and media from the message and sends them as a new message (no "Forwarded from" label)
- **↗️ Forward** forwards the original message (shows "Forwarded from @channelname")

**When to use Send:** when you want the message to look like it was written by the account itself. More natural, less likely to be flagged as spam by group admins.

**When to use Forward:** when you want people to see where the message came from and visit your channel. Good for channel promotion.

### Step 3 : Set the number of cycles

The bot asks: _"📤 Cycles no."_

A **cycle** = one complete round of sending your ad to ALL target groups/topics. Enter a number:
- `1` sends to every target once, then stops
- `5` sends to every target 5 times (with a cycle delay between each round)
- `0` runs forever, keeps repeating until you manually stop it

**Example:** If you have 200 target groups and set cycles to 3:
- Cycle 1: sends to all 200 groups (with message delay between each)
- (cycle delay pause)
- Cycle 2: sends to all 200 groups again
- (cycle delay pause)
- Cycle 3: sends to all 200 groups again
- Done, stops automatically

### Step 4 : Choose run mode and toggle parallel

You'll see:
```
✅ Settings saved:
🔗 Link: https://t.me/mychannel/123
📤 Mode: Send
🔁 Cycles: 0

Choose Auto Or Manual.
Auto prefered.

Parallel Not applied
```

Three buttons:
- **🔄 Auto** the bot scans all groups your account is in and picks targets automatically
- **✋ Manual** you provide the exact list of targets
- **🔴 Parallel / 🟢 Parallel** toggles parallel mode on/off

#### What is Parallel Mode?
- **Off (default, recommended):** The bot sends to one group, waits for the message delay, sends to the next group, waits, and so on. Slow but safe.
- **On:** The bot sends to 10 groups at the same time in a batch, waits 5 minutes, sends the next 10, and so on. Much faster when you have hundreds of targets. Between cycles, it rests for 65 minutes. **Higher risk of Telegram flagging your account for spam.**

Tap the Parallel button to toggle it. When it shows 🟢 Parallel, parallel mode is on.

### Step 5A : Auto Mode > Choose target type

If you chose Auto, you'll see:
- **📌 Topics Only** only sends to forum groups (groups that have topics/threads). Skips regular groups entirely.
- **📌 Topics + Groups** sends to both regular groups AND forum topics.

**When to use Topics Only:** when your ad is topic-specific (e.g. you want to post in "Buy/Sell" or "Promotions" topics inside forum groups).

**When to use Topics + Groups:** when you want maximum reach across every group and every matching topic.

### Step 5B : Auto Mode > Enter the title keyword

The bot asks: _"📤 Title (e.g. insta, tele) — groups with this in name:"_

Type a **keyword**. The bot will match this keyword against topic names in forum groups. Only topics whose title contains your keyword will be targeted.

**Examples:**
- Type `sell` → targets topics like "Buy & Sell", "Selling", "For Sale"
- Type `promo` → targets topics like "Promotions", "Self Promo", "Promo Zone"
- Type `ad` → targets topics like "Ads", "Advertising", "Ad Board"

For regular groups (if you chose Topics + Groups), ALL regular groups are included regardless of this keyword. The keyword only filters forum topics.

### Step 5C : Manual Mode > Provide your targets

If you chose Manual, the bot asks you to send your target list. Send groups and channels in any of these formats, one per line or comma-separated:

| Format | Example | What it targets |
|--------|---------|----------------|
| Full topic link | `https://t.me/somegroup/94` | That specific topic in the group |
| Private channel link | `https://t.me/c/1234567/89` | That specific topic/message thread |
| @username | `@somegroup` | The group's general chat |
| Username without @ | `somegroup` | Same as above |
| Username + topic ID | `somegroup/94` | That specific topic (ID 94) |

You can mix formats:
```
https://t.me/group1/42
@group2
group3/17
t.me/c/987654/3
```

### Step 6 : Launch!

After all settings are confirmed, the bot shows a summary:
```
✅ Adbot started.

🤖 Account: Adbot 1
🔗 Link: https://t.me/mychannel/123
📤 Mode: Send
🔁 Cycles: 0
🎯 Target: Topics + Groups
🏷 Title: promo
```

Then it starts running. You'll see the account's button switch to 🟢 Running in the Adbot panel.

The bot also tells you how many targets it found: _"📊 Targets found: 247"_

</details>

---

## 🔧 Commands / Reference

### `/start`
Opens the main menu. Also **clears any stuck state**. If you were in the middle of setting up an ad, adding an account, or changing settings and things got confusing, just send `/start` to reset everything and return to the clean main menu.

**Works for:** Premium users only. Non-premium users see _"You need premium to use this bot."_

### `/stop`
Emergency stop. Immediately stops **every ad running on every account** you own. If you have 3 accounts running, all 3 stop. The bot tells you how many were stopped: _"⏹ Stopped 3 adbot(s)."_

If nothing is running, you'll see: _"No running adbots to stop."_

**When to use:** When you want to halt everything quickly without going through the Adbot panel for each account.

### `/set <campaign_name>`
Saves a list of target group links under a name so you can reuse it.

**How to use:**
1. First, send a message (in any chat, even to yourself in Saved Messages) containing your target links, **one per line**:
   ```
   https://t.me/group1/123
   https://t.me/group2/456
   t.me/c/789/42
   https://t.me/anothergroup/7
   ```
2. Then **reply** to that message with:
   ```
   /set mycampaign
   ```
3. The bot saves it: _"Saved campaign "mycampaign" with 4 link(s)."_

**Rules:**
- You must **reply** to a message. You can't just type `/set name` alone (the bot will tell you to reply)
- The replied message must contain at least one valid `t.me/...` link
- Each link should be on its own line
- You can overwrite an existing campaign by using the same name again
- Campaign names can be anything: `my_groups`, `crypto`, `english_topics`, etc.

### `/platform <campaign_name>`
Activates a saved campaign. After this, your next ad run will **only send to the links in that campaign** instead of scanning all your groups.

**Example:**
```
/platform mycampaign
```
Response: _"Campaign "mycampaign" activated (4 links). Next adbot run will use these targets."_

If the campaign doesn't exist: _"Campaign "mycampaign" not found. Use /show to see your campaigns."_

**Important:** This only affects **new** ad runs started after the command. Already-running ads are not affected. The campaign stays active until you use `/reset` or set a different one.

### `/reset`
Deactivates any active campaign. Your next ad run will go back to **full scan mode** (scanning all groups your account has joined).

If no campaign was active: _"No active campaign to reset."_

### `/show`
Lists all campaigns you've saved with the link count and which one is active:
```
Your campaigns:
  english_groups : 12 link(s) (active)
  crypto_topics : 8 link(s)
  hindi_promos : 23 link(s)
```

If you have no campaigns: _"No saved campaigns. Use /set <name> to create one."_

### `/help`
Shows a quick reference of all available commands and what they do.

<details>
<summary><b>📂 Campaigns (Full Walkthrough)</b></summary>

Campaigns let you **skip the auto-scan** and use a **fixed list of targets** instead. This is incredibly useful when:

- You already know which groups you want to target
- You want to target specific topics by their exact links
- Auto-scan is picking up groups you don't want
- You want to run the same targets every day without re-scanning

### Creating a Campaign (Example)

Let's say you want to create a campaign called "crypto" with 3 groups:

**Step 1:** Open Saved Messages (or any chat) and send this message:
```
https://t.me/cryptotrading/42
https://t.me/bitcoingroup/17
https://t.me/c/1234567890/89
```

**Step 2:** Reply to your own message with:
```
/set crypto
```

**Step 3:** Bot confirms: _"Saved campaign "crypto" with 3 link(s)."_

### Activating the Campaign

```
/platform crypto
```

Now start an ad run on any account. Instead of scanning 500+ groups, the bot will **only** target those 3 links. If any link fails (group not found, account not a member), that link is silently skipped.

### Going Back to Full Scan

```
/reset
```

Now ad runs will scan all groups again as usual.

### Updating a Campaign

Just use `/set` again with the same name. Reply to a new message with the updated links:
```
/set crypto
```
The old list is replaced with the new one.

</details>

<details>
<summary><b>⚙️ Settings (Detailed Walkthrough)</b></summary>

From `/start` → **⚙️ Settings**:

```
📋 Log bot
👤 Adbot Account Setting
⏱ Message delay
🔁 Cycle delay
◀ Back
```

### 📋 Log Bot : What It Is and Why You Need It

A **log bot** is a separate Telegram bot (that you own) which receives real-time delivery reports. Every time your ad is sent to a group, the log bot sends you a message like:
```
Message sent to: https://t.me/somegroup/12345

Adbot By @ownerusername
```

You can tap the link to see the actual sent message in the group.

**Without a log bot**, you have no way to see where your ads were delivered. You're flying blind. **Set one up before running any ads.**

**How to Set Up a Log Bot:**

1. Open Telegram and go to [@BotFather](https://t.me/BotFather)
2. Send `/newbot` and follow the steps to create a new bot
3. BotFather gives you a **token** that looks like `7123456789:AAHdqTcvCH1vGWJxfSeofSAs0K5PALDsaw`
4. **Important:** Open a chat with your new bot and send it `/start`. This is required so the bot can send messages to you
5. Go to Adbot: `/start` → ⚙️ Settings → 📋 Log bot
6. Paste the token
7. If valid, you'll see: _"✅ Log bot set: @YourLogBot"_ and receive a test message from the log bot

**If your log bot token expires or gets revoked**, the adbot notifies you once: _"⚠️ Your logbot token is revoked. Please register it again."_ Your ads keep running, you just won't get logs until you fix the token.

### 👤 Adbot Account Setting : Username

This sets your username which appears in the bio of all your connected accounts. The bio is automatically set to:
```
Adbot For @yourusername. Powered By @ownerusername
```

**How to change it:**
1. Tap 👤 Adbot Account Setting
2. Send your username (without @), e.g.: `myusername`
3. Bot confirms and updates the bio on all your connected accounts

If you already have a Telegram username, the bot tries to auto-detect it. You'll see: _"✅ Auto-assigned username: @myusername"_

### ⏱ Message Delay

This is the **gap in seconds** between sending your ad to one group and the next group.

**Why it matters:**
- **Short delay (e.g. 60s):** Faster delivery, but higher risk of Telegram flagging your account for spam
- **Long delay (e.g. 600s):** Slower delivery, but much safer for your account

**How to change it:**
1. Tap ⏱ Message delay
2. Bot shows your current delay and the allowed range (e.g. 60 to 600 seconds)
3. Send a number in seconds, e.g. `120` for 2 minutes between each message

**Example:** If you have 100 targets and set a 120-second delay, one full cycle takes about 100 × 120 = 12,000 seconds ≈ 3.3 hours.

The owner sets the minimum and maximum bounds. You cannot go below the minimum (to protect accounts) or above the maximum.

#### 🔁 Cycle Delay

This is the **gap in seconds** between finishing one complete cycle and starting the next.

**What happens during the cycle gap:**
1. The account disconnects from Telegram
2. Waits for the cycle delay duration
3. Reconnects to Telegram
4. Starts the next cycle

This disconnect/reconnect helps avoid long-running connection issues.

**How to change it:**
1. Tap 🔁 Cycle delay
2. Bot shows your current delay and allowed range
3. Send a number in seconds

**Example:** If you set cycles to 0 (infinite) and cycle delay to 300 seconds (5 minutes), the bot sends to all groups, waits 5 minutes, sends to all groups again, waits 5 minutes, and so on forever.

</details>

<details>
<summary><b>▶️ Start All / ⏹ Stop All (Detailed)</b></summary>

### ⏹ Stop All
Tapping this or typing `/stop` does the same thing: it goes through every running ad on every account you own and kills them all instantly.

**What exactly happens:**
- Every running ad is flagged to stop
- The background tasks are cancelled
- All account buttons update from 🟢 to 🔴
- You see: _"⏹ Stopped N adbot(s)."_

The accounts themselves are NOT logged out or removed. They just stop sending ads.

### ▶️ Start All
This is a **bulk restart** feature. It goes through all your accounts and restarts each one using the **last run configuration** that was used for that slot.

**What is "last run config"?**
Every time you start an ad run (through Run ADS, Fwd Link, or Send Link), the bot saves the settings you used:
- Message link
- Send or Forward mode
- Number of cycles
- Title keyword
- Target mode (topics only / topics + groups)
- Parallel on/off

When you tap Start All, the bot looks up these saved settings for each slot and re-launches with the same parameters.

**What if a slot was never used?**
The bot tells you: _"Slot N has no previous run config. Start it manually first."_

**What if some slots are already running?**
They are skipped. Only stopped slots are started.

**Typical use case:**
1. You set up all your accounts with the right settings and run them
2. Later you use Stop All (or /stop) to halt everything
3. Next day, you tap Start All to resume everything without reconfiguring

</details>

<details>
<summary><b>🔄 Auto-Restart After Bot Reboot</b></summary>

If the bot's server crashes, restarts, or has a power outage, your running ads are **not lost**. When the bot starts back up, it automatically detects which ads were interrupted and resumes them.

**How it works:**
- When an ad starts running, a small resume file is created on disk
- When an ad finishes normally (cycles completed) or you stop it, the file is deleted
- If the bot restarts and finds these files still there, it knows those ads were interrupted and re-launches them

**What gets checked before resuming:**
- Is the Telegram session file still there?
- Does the user still have active premium?
- Is the session still assigned to the user?

If any check fails, the resume file is deleted and that ad is not restarted.

**This does NOT happen if you manually stopped the ad.** Manual stops delete the resume file, so the bot knows not to restart it.

</details>

<details>
<summary><b>⚠️ What Happens When Things Go Wrong</b></summary>

### Your account gets spam-limited
Before starting an ad run, the bot checks your account against Telegram's @SpamBot. If it says your account is limited:
- The ad does **not** start
- You get notified: _"⚠️ Session XYZ is limited/spammed (spambot). Not removed."_
- The bot owner also gets notified
- Your account is **not** deleted. It usually recovers after some hours/days

### Your account gets logged out or frozen
If Telegram invalidates your session (you logged in from somewhere else, account frozen, account deactivated):
- The session file is moved to a "spammed" folder
- The session is removed from your account
- Both you and the owner get notified
- You need to re-add the account using ➕ Add account

### Telegram rate-limits your account (FloodWait)
If Telegram says "slow down", the bot automatically waits the required time and then continues. Your ad run is paused temporarily, not stopped. No action needed from you.

### A target group/topic is unreachable
If the bot can't send to a specific group (not a member, group was deleted, topic was closed), it silently skips that target and continues with the rest. Your log bot receives a warning about the skipped target.

### The bot itself crashes mid-run
Your ads auto-resume when the bot restarts (see Auto-Restart section above).

</details>

<details>
<summary><b>💡 Tips & Best Practices</b></summary>

1. **Always set up a log bot first.** Without it, you can't see where your ads are being delivered
2. **Start with a high message delay** (300+ seconds) and decrease it slowly. This reduces the risk of getting spam-limited
3. **Use Send mode for groups that hate forwarded messages.** Many group admins auto-delete forwarded messages
4. **Use Forward mode when promoting a channel.** People can see and tap the channel name
5. **Use campaigns for consistent targeting.** If you have a fixed list of 50 good groups, save them as a campaign and reuse them every time
6. **Track Channel is great for monitoring.** You can glance at the channel to see if deliveries are happening without checking the log bot
7. **Don't run parallel mode on new or recently-limited accounts.** Use sequential (parallel off) to be safe
8. **If something feels stuck, send `/start`.** It resets everything and brings you back to a clean state
9. **Set cycles to 0 only if you're sure.** Infinite cycling means it keeps going until you stop it or premium expires
10. **Keep your 2FA password safe.** The bot does NOT store your 2FA password after login

</details>

---

# 🛠️ Admin Guide

> **This section is for the bot owner/operator only.**

<details>
<summary><b>⚙️ First-Time Setup</b></summary>

When you run `adbotv2.py` for the first time, it asks you three things in the terminal:

1. **Bot token** : create a bot via [@BotFather](https://t.me/BotFather) and paste the token
2. **Owner ID** : your numeric Telegram user ID (find it using bots like `@userinfobot` or `@myidbot`)
3. **Owner username** : your Telegram username (with or without @)

These are saved in `bot_settings.json`. You won't be asked again unless the file is deleted.

### Starting the Bot
```
pip install -r requirements.txt
python adbotv2.py
```

You'll see `Bot is running` in the terminal. The bot is now live and accepting messages.

### What Runs in the Background
When the bot starts, several background processes run automatically:
- **Premium expiry checker** checks every 5 minutes if any user's premium has expired
- **Connection health monitor** checks every 5 minutes if running accounts are still connected to Telegram
- **Auto-resume** on startup only, checks for interrupted ad runs and resumes them
- **Scheduled exit** after 70 days of continuous runtime, the bot stops itself (safety measure)

</details>

<details>
<summary><b>👑 The <code>/admin</code> Command</b></summary>

Send `/admin` in the bot chat. Only you (the owner) can use this. All other users are silently ignored.

You'll see:

```
➕ Add premium
➖ Remove premium
⏱ Message time
📁 Join folder
🖼 Assign pic
```

### ➕ Add Premium : Give a User Access

This is how you onboard new customers.

**Step 1 : Enter user ID**
The bot asks for a numeric user ID. The user can find their ID using bots like `@userinfobot`. Example: `8096295080`

**Step 2 : Choose time period**
```
📅 1 week
📅 15 days
📅 1 month
📅 2 months
📅 3 months
```
This is how long their premium lasts from now.

**Step 3 : Choose plan**
```
🥉 Bronze    (1 account)
🥈 Silver    (2 accounts)
🥇 Gold      (3 accounts)
💎 Platinum  (4 accounts)
⚙️ Custom    (you decide)
```

**Step 4 : (Custom plan only) Enter account count**
If you chose Custom, enter how many accounts they get (1 to 12). Maximum is 12.

**Step 5 : Review and confirm**
You see a summary with the user's ID, plan, and time period. Tap ✅ Confirm or ❌ Cancel.

**What happens after confirm:**
- Premium is activated for that user
- The user receives: _"✅ You have been added/upgraded to Gold premium. ⏱ Plan ends: 27 Apr 2026, 03:30 PM UTC"_
- If the user already had any Telegram sessions from a previous plan, they're automatically re-assigned
- If the user already has premium, this **replaces** the old plan (it doesn't extend or stack)

### ➖ Remove Premium : Revoke a User's Access

**Step 1:** Bot shows a list of all premium users with their IDs. Tap the one you want to remove.

**Step 2:** Confirm removal.

**What happens:**
- All their running ads are stopped immediately
- All their temp run files are deleted (so they won't auto-resume)
- The user receives: _"❌ You have been removed from premium."_
- Their Telegram session files are **NOT** deleted. If you give them premium again later, their sessions are still usable
- The user can no longer use the bot at all (every command says "You need premium")

### ⏱ Message Time : Set Global Delays

Controls the default delay values that all users start with.

**Step 1:** Choose what to change:
- **⏱ Message Time** the gap between sending to one group and the next
- **🔁 Cycle GAP TIME** the gap between finishing one full cycle and starting the next

**Step 2:** Enter the value **in minutes** (not seconds). Examples:
- `4` = 240 seconds (4 minutes between each message)
- `1.5` = 90 seconds
- `18` = 1080 seconds (18 minutes between cycles)

The current values are shown before you change them.

**Note:** Individual users can override these values via their Settings menu, but only within the bounds you define (see "Setting Min/Max Bounds" below).

#### Setting Min/Max Bounds for User Overrides

Users can change their own message and cycle delays, but you control the limits. Open `bot_settings.json` in a text editor and add these keys:

```json
{
  "bot_token": "...",
  "owner_id": "...",
  "owner_username": "...",
  "message_gap_sec": 250,
  "cycle_gap_sec": 1100,
  "min_message_gap": 60,
  "max_message_gap": 600,
  "min_cycle_gap": 60,
  "max_cycle_gap": 600
}
```

- `min_message_gap` / `max_message_gap` control the range users can set for their message delay (in seconds). Default: 60 to 600.
- `min_cycle_gap` / `max_cycle_gap` control the range users can set for their cycle delay (in seconds). Default: 60 to 600.

If a user tries to set a delay outside these bounds, they'll see an error: _"Value must be between 60 and 600 seconds."_

You can edit `bot_settings.json` while the bot is running. It re-reads the file every time it's needed.

### 📁 Join Folder : Mass-Join Groups

Makes **all registered Telegram accounts** (across all users) join a Telegram folder invite link.

**What is a folder invite link?**
Telegram lets you create a folder of chats and share it as a link like `https://t.me/addlist/ABC123DEF`. When someone joins, they get all the groups/channels in that folder added to their account.

**How to use:**
1. Create a folder of groups on your own Telegram account
2. Share the folder as a link
3. In the bot, tap 📁 Join folder
4. Paste the link: `https://t.me/addlist/ABC123DEF`
5. The bot goes through every registered session and makes them join

You'll see: _"✅ Folder "ABC123" joined. ✅ Success: 8  ❌ Failed: 2"_

**Why use this:** It's the fastest way to get all accounts into the same set of groups. Without this, each user would have to manually join groups from each account.

### 🖼 Assign Pic : Mass Profile Picture

Sets the **same profile picture** on **all registered accounts** (across all users).

**How to use:**
1. Tap 🖼 Assign pic
2. Send a photo (not a file, an actual image)
3. The bot applies it to each account one by one

For each account:
- **Success:** _"✅ Applied to John"_ (shows the account's first name, clickable)
- **Frozen/Invalid account:** _"🗑 abc123: frozen/invalid. Removed."_ The account is auto-removed
- **Other error:** _"❌ abc123: connection timeout"_

At the end: _"✅ Done! Applied to all accounts."_

</details>

<details>
<summary><b>📁 Files & What They Store</b></summary>

| File | What's inside | Safe to edit while running? |
|------|--------------|---------------------------|
| `bot_settings.json` | Bot token, owner ID/username, global delay settings, min/max bounds | ✅ Yes (re-read on each use) |
| `sessions.json` | List of all Telegram sessions (unique_name, phone number, Telegram ID) | ❌ No (bot overwrites it) |
| `premium.json` | All premium users: user ID, plan, expiry timestamp, assigned sessions | ❌ No (bot overwrites it) |
| `user_sessions.json` | Maps user ID → list of their session names | ❌ No (bot overwrites it) |
| `account_settings.json` | Per-user settings: username, delays, campaigns, track channels, last run configs | ❌ No (bot overwrites it) |
| `logs.json` | Log bot tokens for each user | ❌ No (bot overwrites it) |
| `sessions/` folder | Actual Telegram `.session` files (SQLite databases) | ❌ Never touch these |
| `spammed/` folder | Sessions moved here when detected as spam-limited or invalid | Can delete manually to clean up |
| `temp_runs/` folder | Runtime state files and auto-resume files | Can delete `resume_*` files to prevent auto-resume |

### The `temp_runs/` Folder
Contains two types of files:
- `run_{user_id}_{slot}_{timestamp}.json` is live run state, deleted when the run finishes
- `resume_{user_id}_{slot}.json` is an auto-resume file, deleted when the run finishes or user stops it

If you want to **prevent** a specific ad from auto-resuming after a restart, delete its `resume_*.json` file before starting the bot.

</details>

<details>
<summary><b>📶 Connection Health Monitor</b></summary>

A background thread runs every **5 minutes** and goes through every currently-running ad account. For each one, it checks:

1. Is the Telegram client still connected?
2. If not, try to reconnect

If reconnection fails, it logs the error to the console but does **not** stop the ad. It will try again on the next 5-minute check.

Telegram connections can drop due to network issues, server maintenance, etc. The health monitor ensures accounts reconnect automatically without the user having to restart their ad.

</details>

<details>
<summary><b>🔄 Auto-Restart (How It Works Technically)</b></summary>

**When an ad starts:**
A file is created: `temp_runs/resume_{user_id}_{slot_idx}.json` containing all the run parameters (link, mode, cycles, title, target mode, parallel).

**When an ad ends normally or is stopped by the user:**
The resume file is deleted.

**When the bot starts up:**
The `_auto_resume_jobs()` function scans `temp_runs/` for any `resume_*.json` files. For each one:

1. **Check session exists** : is the `.session` file still in the `sessions/` folder?
2. **Check premium** : does the user still have active, non-expired premium?
3. **Check assignment** : is the session still assigned to this user?

If all checks pass, the ad is re-launched with the saved parameters. You'll see in the terminal:
```
Auto-resume: resuming job for user 12345, slot 0, session abc123
Auto-resume: resumed 2 job(s).
```

If any check fails, the resume file is deleted and the ad is skipped. You'll see:
```
Auto-resume: session abc123 no longer exists, skipping.
Auto-resume: user 12345 no longer premium, skipping.
```

</details>

<details>
<summary><b>⏰ Scheduled Exit (70-Day Limit)</b></summary>

The bot automatically stops after **70 days** of continuous runtime. This is a safety measure to prevent stale processes, memory leaks, or session issues.

When the 70-day limit hits:
1. All running ads are stopped
2. Bot polling is stopped
3. The async event loop is shut down
4. Terminal shows: _"Scheduled exit reached. Stopping adbot tasks and polling."_

**To continue:** Just restart `python adbotv2.py`. All ads that were running will auto-resume (via the resume files).

</details>

<details>
<summary><b>🛡️ Spam Detection & Account Protection</b></summary>

### SpamBot Check (Before Every Run)
Before any ad starts sending, the bot contacts Telegram's @SpamBot on behalf of the account and checks for restrictions. If the account is spam-limited:
- The run is **aborted** before sending anything
- Both you and the user are notified
- The account is **NOT removed** (it usually recovers after hours/days)

### Mid-Run Spam Detection
If spam limitation is detected during a run (send fails + spambot confirms):
- The run stops immediately
- Both you and the user are notified
- The account stays in the system

### Invalid Session Detection
If the Telegram session becomes invalid during a run (logged out, account frozen, deactivated, unauthorized):
- The session file is moved to the `spammed/` folder
- The session is removed from the user's account
- Both you and the user are notified with the reason

### AuthKeyDuplicated Detection
If the same session is being used by another process/device simultaneously:
- The run stops
- User is notified: _"Session is active elsewhere (AuthKeyDuplicated). Stop the other process."_
- The account is **NOT removed** (it's still valid, just busy elsewhere)

</details>

<details>
<summary><b>🔔 Notifications You'll Receive as Owner</b></summary>

You automatically receive messages from the bot when:
- A session is created (shows unique name, phone, Telegram ID, username)
- A session becomes invalid and is removed
- A user's account is spam-limited
- An AuthKeyDuplicated error occurs
- A session is forcefully recreated by a user

These help you monitor the health of all sessions across all users without having to check anything manually.

</details>

---

<div align="center">

### ⚠️ Disclaimer

This tool is provided for **educational and authorized use only**. The author is not responsible for any misuse or violations of Telegram's Terms of Service. Use responsibly.

---

Made with ❤️ by [@rejerk](https://t.me/rejerk)

<a href="https://t.me/stein_vault_bot"><img src="https://img.shields.io/badge/Get%20Access-@stein__vault__bot-00C853?style=flat-square&logo=telegram&logoColor=white" /></a>

</div>
