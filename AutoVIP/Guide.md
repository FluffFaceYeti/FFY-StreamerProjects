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

## The OBS steal overlay

An optional animation for steals: the winner's Twitch picture charges in, knocks the loser off the screen, takes their VIP badge and finishes in the middle with a banner, e.g. *"xan stole eve's VIP badge!"*.

The files are in the **Overlay** folder. Keep all of them in the same folder:

| File | What it is |
|------|------------|
| `AutoVIP Steal Overlay.html` | The overlay for OBS |
| `AutoVIP Overlay Settings.html` | A settings page with a live preview, for colours, animation, wording and sound |
| `Streamer.bot Connection Test.html` | Finds out why the overlay can't connect, if it can't |

### Setting it up

1. **Switch on Streamer.bot's WebSocket Server:** **Servers/Clients** tab → **WebSocket Server**. Use address `127.0.0.1` and port `8080`, tick **Auto Start**, then click **Start Server**. Don't use `4455`: that's OBS's own WebSocket.
2. **Open `AutoVIP Overlay Settings.html`** in your web browser. Pick your animation, colours, wording and sound, and watch the preview.
3. Click **Copy OBS link**.
4. **In OBS:** add a **Browser** source, untick **Local file**, paste the link into **URL**, and set the size to **2560 x 1440**. Tick **Control audio via OBS** if you're using a sound.
5. Type `!teststeal` in chat to see it work.

To change something later, open the settings page again, make the change, copy the new link and paste it into the Browser source.

### What you can change on the settings page

- **Animation:** Knockout (flies off the corner), Slam (squashed from above), Yoink (badge snatched, dizzy), Rocket (launched upwards), Bowling (rolled off the side), or Random. Speed lines, the flash and the screen shake can each be switched off.
- **Colours:** one-click themes (Beardly Orange, Twitch purple, Ice blue, Toxic green, Hot pink, Gold, Black & white) or your own colour for every part.
- **Banner:** your own wording with `{new}`, `{old}` and `{amount}`, whether the bits/subs line shows, how long it stays, and the overall size.
- **Sound:** click **Browse...** to pick an mp3, wav or ogg, set the volume, and choose whether it plays on the hit, when the loser appears or when the badge lands. Keep the sound in the overlay's folder, or use **Put the sound inside the link** for short sounds.
- **Connection:** the WebSocket address, port and password, if yours aren't the defaults.

The settings page also gives a **Custom CSS** block for the colours, which you can paste into the Browser source's **Custom CSS** box instead if you'd rather keep **Local file** ticked.

### Connecting Streamer.bot to OBS

If you haven't already, connect Streamer.bot to OBS:

1. **In OBS:** **Tools** → **WebSocket Server Settings**. Tick **Enable WebSocket server**, then click **Show Connect Info**. It shows the **Server IP**, **Server Port** and **Server Password**.
2. **In Streamer.bot:** **Stream Apps** → **OBS Studio** → right-click → **Add**. Copy the Server IP, Server Port and Server Password from OBS into it, tick **Auto Connect**, and click **OK**.

This lets Streamer.bot control OBS. The overlay itself talks to Streamer.bot's **WebSocket Server** (step 1 above), which is a different connection, so make sure both are set up.

### Dual-PC setups

If Streamer.bot runs on one PC and OBS on another (e.g. a gaming PC and a streaming PC):

1. **On the Streamer.bot PC:** in **Servers/Clients** → **WebSocket Server**, set the address to `0.0.0.0` so the other PC can connect, keep port `8080`, then click **Stop Server** and **Start Server**. If Windows asks about the firewall, click **Allow**.
2. **Find the Streamer.bot PC's IP address:** open Command Prompt on it, type `ipconfig`, and look for **IPv4 Address**, e.g. `192.168.0.10`.
3. **On the settings page:** under **Streamer.bot connection**, set the **Address** to that IP, then copy the OBS link again.
4. **On the OBS PC:** use that link in the Browser source. Copy the overlay files (and your sound) to the OBS PC too.
5. **Connect Streamer.bot to the OBS PC:** on the OBS PC, open OBS → **Tools** → **WebSocket Server Settings** → **Show Connect Info**, and copy its **Server IP**, **Server Port** and **Server Password** into Streamer.bot's **Stream Apps** → **OBS Studio** connection.

### If it won't connect

Open `Streamer.bot Connection Test.html` in your web browser on the PC that runs OBS, with Streamer.bot open, and click **Test the connection**. It tells you what's wrong and what to put in the settings. The most common cause is the WebSocket Server not being started.

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
4. Optional: set up the OBS steal overlay (see above).

**Updating from an older AutoVIP?** Streamer.bot may keep your old actions instead of replacing them. Delete the old **AutoVIP** actions and commands first, then import. Your viewers' stats are saved separately and aren't lost. Copy your settings and Manual VIPs list somewhere safe before deleting, so you can put them back.
