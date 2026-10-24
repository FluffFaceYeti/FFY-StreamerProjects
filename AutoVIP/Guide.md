# AutoVIP for Streamer.bot

Automatically gives VIP to your top supporters and removes it when they drop off. VIPs only change while you're live.

When someone climbs a leaderboard and pushes someone else out, chat sees that they **stole** the VIP badge, and an optional OBS overlay plays a knockout animation with both of their Twitch pictures.

**Credit:** BehavingBeardly

---

## How it works

The top viewers on each leaderboard get VIP, as long as they meet the minimum. By default that's the top 5 on each:

| Leaderboard   | Minimum to qualify          |
|---------------|-----------------------------|
| Watch streak  | 5 streams in a row          |
| Sub streak    | 5 months                    |
| Gifted subs   | 1 gifted sub                |
| Bits cheered  | 100 bits                    |

### Who is skipped

- Mods, lead mods, editors and artists (detected automatically)
- Bots and the broadcaster
- Manual VIPs: anyone on the **Manual VIPs** list, or anyone given VIP by hand

Skipped users never appear on the leaderboards, in `!myrank` or in the saved lists, and never take up a VIP spot. Only normal viewers can win or lose the badge.

> **Note:** AutoVIP never removes a VIP it didn't give.

---

## Steals and lost badges

When a leaderboard is full and someone new climbs into it, the person at the bottom loses their VIP. Chat sees who took it:

```
🎉 xan cheered 2,500 bits and stole a VIP badge from eve!
💔 eve lost their VIP badge because xan stole it!
```

Every leaderboard has its own message:

| Leaderboard   | Message |
|---------------|---------|
| Bits          | xan cheered 2,500 bits and stole a VIP badge from eve! |
| Gifted subs   | xan has gifted 12 subs and stole a VIP badge from eve! |
| Sub streak    | xan hit an 8-month sub streak and stole a VIP badge from eve! |
| Watch streak  | xan hit a 14-stream watch streak and stole a VIP badge from eve! |

When someone loses VIP for another reason, chat is told that too:

```
💔 eve lost their VIP badge because their watch streak ended.
💔 eve lost their VIP badge because their sub streak ended.
💔 eve lost their VIP badge.
```

- A steal only happens within the same leaderboard.
- If someone's own streak ends, that's never counted as a steal.
- While a leaderboard isn't full yet, everyone who qualifies just gets VIP and nobody loses theirs.
- If more than 3 people lose VIP at once (for example after a reset), they're listed in one message instead.
- Steals are spotted from the second VIP refresh after installing, once AutoVIP knows who was on each leaderboard.

---

## Commands

### Everyone

| Command   | Description                   |
|-----------|-------------------------------|
| `!myrank` | See your leaderboard ranks    |

### Mods only

| Command                       | Description                          |
|-------------------------------|--------------------------------------|
| `!refreshvip`                 | Update VIPs now                      |
| `!setgifted <user> <amount>`  | Fix someone's gifted sub total       |
| `!topwatchstreak`             | Show the watch streak leaderboard    |
| `!topsubstreak`               | Show the sub streak leaderboard      |
| `!topgifters`                 | Show the gifted subs leaderboard     |
| `!topbits`                    | Show the bits leaderboard            |
| `!topvips`                    | Show all leaderboards                |
| `!teststeal`                  | Shows a pretend steal in chat and on the overlay. Nobody's VIP changes |

`!teststeal` uses your real bits leaderboard. If the list is full, it pretends the person just outside it cheered their way in. If it isn't full yet, it pretends whoever typed `!teststeal` stole the badge from the lowest-ranked person.

---

## Settings

All settings are at the top of the **AUTOVIP** code. Click **Save and Compile** after changing anything.

### The basics

| Setting                  | Description |
|--------------------------|-------------|
| `BROADCASTER_LOGIN`      | **Change this first:** your Twitch channel name, in lower case, e.g. `"yourchannelname"` |
| `ENABLE_SUB_STREAK`, `ENABLE_WATCH_STREAK`, `ENABLE_SUB_GIFTERS`, `ENABLE_CHEER_BITS` | `true` or `false` to switch each leaderboard on or off |
| `TOP_N_SUB_STREAK`, `TOP_N_WATCH_STREAK`, `TOP_N_SUB_GIFTERS`, `TOP_N_CHEER_BITS` | How many VIP spots each leaderboard gives (default `5`) |
| `MIN_WATCH_STREAK`, `MIN_SUB_STREAK`, `MIN_SUB_GIFTERS`, `MIN_CHEER_BITS` | The minimum to qualify for each leaderboard |
| `VIP_CAP`                | The most VIPs AutoVIP will give out. Twitch allows Affiliates 60 and Partners 100. Keep it at or above all the `TOP_N_` values added together |
| `MANUAL_EXCLUDE_LOGINS`  | Manual VIPs: names AutoVIP leaves alone. Replace `ManualVIPUsername1` and the others with real names, or remove them |
| `IGNORE_LOGINS`          | Bots and accounts that are never tracked |

### Resets and data

| Setting                  | Description |
|--------------------------|-------------|
| `RESET_PERIOD_MONTHS`    | `0` never resets, or set a period such as `6`, `12`, `24`… |
| `RESET_START_DATE`       | When reset periods start, e.g. `"2026-01-01"`. Use `""` to start from the first run |
| `RESET_KEEPS_DATA`       | `true` ranks on the current period only and keeps all-time data. `false` wipes everything on reset |
| `INCLUDE_LIFETIME_DATA`  | `true` uses Twitch's lifetime numbers. `false` counts only since the last reset |
| `GRACE_PERIOD_DAYS`      | Days someone keeps VIP after dropping off a leaderboard. `0` removes it straight away |

### Chat messages

| Setting                  | Description |
|--------------------------|-------------|
| `ANNOUNCE_NEW_VIPS`      | `true` posts in chat when someone earns VIP. `false` turns off every VIP message |
| `ANNOUNCE_STEALS`        | `true` posts a message when someone steals a VIP badge |
| `STEAL_CHEER_BITS`, `STEAL_SUB_GIFTERS`, `STEAL_SUB_STREAK`, `STEAL_WATCH_STREAK` | The steal messages. `{new}` = who got VIP, `{old}` = who lost it, `{amount}` = their bits, subs or streak. `""` turns one off |
| `ANNOUNCE_LOST_VIPS`     | `true` posts a message when someone loses their VIP badge |
| `LOST_STOLEN`, `LOST_WATCH_STREAK`, `LOST_SUB_STREAK`, `LOST_OTHER` | The lost badge messages. `{old}` = who lost it, `{new}` = who stole it. `""` turns one off |
| `ENABLE_MYRANK`          | `true` turns on the `!myrank` command |
| `STEAL_OVERLAY`          | `true` sends each steal to the OBS overlay. `false` turns it off |

---

## The OBS steal overlay (optional)

An animation for steals: the winner's Twitch picture charges in, knocks the loser off the screen, takes their VIP badge and finishes in the middle with a banner, e.g. *"xan stole eve's VIP badge!"*.

You don't need the overlay for AutoVIP to work. The chat messages work without it.

### The files

They're in the **Overlay** folder. Keep all of them together in the same folder (and put your sound file in there too, if you use one):

| File | What it's for |
|------|---------------|
| `AutoVIP Steal Overlay.html` | The overlay itself. This is what OBS shows |
| `AutoVIP Overlay Settings.html` | A settings page you open in your web browser to pick colours, animation, wording and sound, with a live preview |
| `Streamer.bot Connection Test.html` | A helper that tells you why the overlay can't connect, if it can't |

### How it works

There are **two separate connections** between Streamer.bot and OBS, and they do different jobs:

| Connection | Direction | What it does | Where it's set up |
|------------|-----------|--------------|-------------------|
| **OBS connection** | Streamer.bot → OBS | Lets Streamer.bot control OBS (scenes, sources and so on) | Streamer.bot: **Stream Apps** → **OBS Studio** |
| **WebSocket Server** | Overlay → Streamer.bot | Lets the overlay hear about steals from AutoVIP | Streamer.bot: **Servers/Clients** → **WebSocket Server** |

The overlay is a web page running inside OBS, so it uses the **WebSocket Server** to listen to Streamer.bot. Both need to be set up.

---

### Step 1: Connect Streamer.bot to OBS

*Skip this if Streamer.bot is already connected to OBS.*

1. **In OBS:** go to **Tools** → **WebSocket Server Settings**.
2. Tick **Enable WebSocket server**, then click **Show Connect Info**. It shows your **Server IP**, **Server Port** and **Server Password**.
3. **In Streamer.bot:** go to **Stream Apps** → **OBS Studio**, right-click the empty list and click **Add**.
4. Copy the **Server IP**, **Server Port** and **Server Password** from OBS into it, tick **Auto Connect**, and click **OK**.

### Step 2: Switch on Streamer.bot's WebSocket Server

1. **In Streamer.bot:** go to the **Servers/Clients** tab → **WebSocket Server**.
2. Set it up depending on your setup:

| | **One PC** (Streamer.bot and OBS on the same PC) | **Two PCs** (e.g. Streamer.bot on a gaming PC, OBS on a streaming PC) |
|---|---|---|
| Address | `127.0.0.1` | `0.0.0.0` (this lets the other PC connect) |
| Port | `8080` | `8080` |

3. Tick **Auto Start**, then click **Start Server**. If you changed something, click **Stop Server** then **Start Server**.
4. **Two PCs only:** if Windows asks about the firewall, click **Allow**.

> Don't use port `4455` here: that's OBS's own port from Step 1.

### Step 3: Pick your look on the settings page

1. Open **`AutoVIP Overlay Settings.html`** in your web browser (double-click it).
2. The **left-hand column** has all the options, in boxes from top to bottom:

| Box | What's in it |
|-----|--------------|
| **Animation** | The style: Knockout, Slam, Yoink, Rocket, Bowling or Random. Plus speed lines, flash, screen shake and overall size |
| **Banner** | The wording (`{new}` = who stole it, `{old}` = who lost it, `{amount}` = their bits, subs or streak), the bits/subs line, and how long it stays |
| **Sound** | Click **Browse...** to pick an mp3, wav or ogg. Set the volume and when it plays (on the hit, when the loser appears, or when the badge lands). **Test sound** plays it |
| **Colour themes** | One click: Beardly Orange, Twitch purple, Ice blue, Toxic green, Hot pink, Gold, Black & white |
| **Colours** | Your own colour for every part |
| **Streamer.bot connection** | At the **bottom** of the column. **Address**, **Port** and **Password** of Streamer.bot's WebSocket Server |

3. The **preview** on the right updates as you change things.
4. **Streamer.bot connection** (scroll to the bottom of the left column):
   - **One PC:** leave the Address as `127.0.0.1` and the Port as `8080`.
   - **Two PCs:** set the **Address** to the IP address of the PC running **Streamer.bot**. To find it, open **Command Prompt** on that PC, type `ipconfig`, and look for **IPv4 Address**, e.g. `192.168.0.10`.
   - **Password:** only if you switched on **Authentication** in Step 2. Otherwise leave it empty.
5. Click **Copy OBS link** (under the preview).

> **Sound files:** keep the sound in the same folder as the overlay. If it isn't, the page tells you where to copy it, or you can click **Put the sound inside the link** (for short sounds).

### Step 4: Add it to OBS

1. **In OBS:** add a **Browser** source to your scene.
2. **Untick** **Local file**.
3. Paste the link from Step 3 into **URL**.
4. Set **Width** to `2560` and **Height** to `1440`.
5. Tick **Control audio via OBS** if you're using a sound, so it shows in your audio mixer.
6. Click **OK**. The overlay is see-through when nothing is happening, so leave it covering the whole screen.

**Two PCs:** do this in OBS on the **streaming PC**, and copy the overlay files (and your sound) onto that PC first.

### Step 5: Test it

Type `!teststeal` in chat. You should see the knockout on screen and the steal messages in chat. Nobody's VIP changes.

### Changing it later

Open the settings page again, change what you want, click **Copy OBS link**, then in OBS double-click the Browser source and paste the new link into **URL**.

You can also change only the colours from inside OBS: copy the **Custom CSS** block from the bottom of the settings page into the Browser source's **Custom CSS** box.

---

### If it won't connect

If the overlay shows *"Can't reach Streamer.bot..."* in the top-left corner:

1. Open **`Streamer.bot Connection Test.html`** in your web browser, on the PC that runs OBS, with Streamer.bot open.
2. Click **Test the connection**. It tells you what's wrong and what to put on the settings page.

Common causes:

| Problem | Fix |
|---------|-----|
| WebSocket Server isn't started | Step 2: tick **Auto Start** and click **Start Server** |
| Port set to `4455` | That's OBS's port. Use Streamer.bot's WebSocket Server port, usually `8080` |
| Two PCs, still refusing | Step 2: the address must be `0.0.0.0`, and the firewall must allow it. Step 3: the Address must be the Streamer.bot PC's IP |
| "Streamer.bot wants a password" | Put the WebSocket Server's password in the settings page's **Password** box, or switch Authentication off |
| Connected, but nothing happens on a steal | Check `STEAL_OVERLAY = true;` in the AUTOVIP code, then type `!teststeal` |

---

## Saved data

Everything is saved in Streamer.bot's **Global Variables** tab.

**Each viewer** (Persisted User Globals → Twitch → their name): `bitsCheeredTotal`, `giftedSubsTotal`, `subStreak`, `watchStreak` and `isAutoVip`. You can edit their numbers there by hand.

**Full rankings** (Persisted Globals), updated on every refresh:

- `AutoVIP - WatchStreakList`
- `AutoVIP - SubStreakList`
- `AutoVIP - GiftedSubsList`
- `AutoVIP - BitsList`
- `AutoVIP - CurrentVIPsList`

Re-importing AutoVIP never touches this data.

---

## Installation

1. In Streamer.bot, click **Import** and import the **AutoVIP-Public** file.
2. Open the **AUTOVIP** code, set `BROADCASTER_LOGIN` to your channel name, change the other settings to suit you, and click **Save and Compile**.
3. Enable the **AutoVIP commands** and the **Auto VIP Refresh** timer.
4. Optional: set up the OBS steal overlay (see **The OBS steal overlay** above).

**Updating from an older AutoVIP?** Streamer.bot may keep your old actions instead of replacing them. Delete the old **AutoVIP** actions and commands first, then import. Your viewers' stats are saved separately and aren't lost. Copy your settings and Manual VIPs list somewhere safe before deleting, so you can put them back.
