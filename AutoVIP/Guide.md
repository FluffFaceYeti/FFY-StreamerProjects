# AutoVIP for Streamer.bot

Automatically gives VIP to your top supporters and removes it when they drop off. VIPs only change while you're live.

When someone climbs a leaderboard and pushes someone else out, chat sees that they **stole** the VIP badge. An optional OBS overlay plays the steal with both of their Twitch pictures, and can also show your leaderboards, a champions board, each viewer's `!myrank` card, an end of stream recap, and boards that pop up on a timer.

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

### How each leaderboard is counted

| Leaderboard | How it's counted |
|-------------|------------------|
| Watch streak | Everyone who is **in your chat** during a stream keeps their streak going, even if they never type, so lurkers count too. AutoVIP checks who's in chat every 5 minutes while you're live (needs the **Auto VIP Refresh** timer on). Chatting or sharing a Twitch watch streak also counts. Miss a stream and it goes back to 0. If your stream crashes and you go live again within 30 minutes, it counts as the same stream |
| Sub streak | Updated when someone resubs and shares their streak in chat. If someone stops subscribing, their streak ends (AutoVIP checks with Twitch when VIPs refresh) |
| Gifted subs | Uses Twitch's lifetime gift total for your channel when the gifter shares it. If they hide it, AutoVIP counts their gifts itself. The number never goes down. Anonymous gifts aren't counted |
| Bits cheered | Uses Twitch's lifetime bits for your channel, or AutoVIP's own count if that's higher |

Stats from before you installed AutoVIP fill in the next time that viewer gifts, cheers, resubs or shares their watch streak. Use `!setgifted` to fix gifted subs straight away.

### Who is skipped

- Mods, lead mods, editors and artists (detected automatically)
- Bots and the broadcaster
- Anyone on the **VIP block list** (`VIP_BLOCK_LIST`)
- Manual VIPs: anyone on the **Manual VIPs** list, or anyone given VIP by hand

Skipped users never appear on the leaderboards, in `!myrank`, in the stream recap or in the saved lists, and never take up a VIP spot. Only normal viewers can win or lose the badge.

> **Note:** AutoVIP never removes a VIP it didn't give.

---

## Steals and lost badges

When a leaderboard is full and someone new climbs into it, the person at the bottom loses their VIP. Chat sees who took it:

```
🎉 xan cheered 2,500 bits and stole a VIP badge from eve!
```

That one message says who won and who lost, so chat only sees one line per steal.

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

| Command | Who | What it does |
|---------|-----|--------------|
| `!myrank` | Everyone | Shows the viewer where they stand on each board, and how far they are from a VIP spot |
| `!topvips` | Mods | Shows every leaderboard in turn |
| `!topwatchstreak` `!topsubstreak` `!topgifters` `!topbits` | Mods | Shows one leaderboard |
| `!vipchamps` | Mods | Shows the number one on every board |
| `!viprecap` | Mods | Shows the end of stream recap |
| `!refreshvip` | Mods | Checks and updates VIPs straight away (only while you're live) |
| `!setgifted <user> <amount>` | Mods | Corrects someone's gifted sub total |
| `!teststeal` | Mods | Plays a pretend steal in chat and on the overlay. Nobody's VIP changes |

You can change who's allowed to use each command in Streamer.bot's **Commands** tab.

`!teststeal` uses your real bits leaderboard. If the list is full, it pretends the person just outside it cheered their way in. If it isn't full yet, it pretends whoever typed `!teststeal` stole the badge from the lowest-ranked person.

With the overlay on, the leaderboards, `!vipchamps`, `!viprecap` and `!myrank` show on screen instead of in chat.

---

## Installation

1. **Download** the **AutoVIP** file from this page.
2. Open it with Notepad (right-click → **Open with** → **Notepad**), press **Ctrl+A** then **Ctrl+C**.
3. In Streamer.bot, click **Import** at the top, paste into the **Import String** box and click **Import**. You'll get an **AutoVIP** group of actions and commands.
4. Check your Twitch broadcaster account is connected under **Platforms** → **Twitch** → **Accounts**. AutoVIP gives and removes VIPs as the broadcaster.
5. In the **Actions** tab, open the **AUTOVIP** action and double-click **Execute C# Code**. Set `BROADCASTER_LOGIN` to your channel name, change the other settings to suit you (see **Settings** below), click **Compile**, then **Save and Compile**.

The commands and the **Auto VIP Refresh** timer switch themselves on the first time AutoVIP runs.

---

## Settings

All settings are at the top of the **AUTOVIP** code, in sections marked `// SETTINGS`. Click **Save and Compile** after changing anything.

### The basics

| Setting                  | Description |
|--------------------------|-------------|
| `BROADCASTER_LOGIN`      | **Change this first:** your Twitch channel name, in lower case, e.g. `"yourchannelname"` |
| `ENABLE_WATCH_STREAK`, `ENABLE_SUB_STREAK`, `ENABLE_SUB_GIFTERS`, `ENABLE_CHEER_BITS` | `true` or `false` to switch each leaderboard on or off |
| `TOP_N_WATCH_STREAK`, `TOP_N_SUB_STREAK`, `TOP_N_SUB_GIFTERS`, `TOP_N_CHEER_BITS` | How many VIP spots each leaderboard gives (default `5`) |
| `MIN_WATCH_STREAK`, `MIN_SUB_STREAK`, `MIN_SUB_GIFTERS`, `MIN_CHEER_BITS` | The minimum to qualify for each leaderboard |
| `VIP_CAP`                | The most VIPs AutoVIP will give out. Twitch allows Affiliates 60 and Partners 100. Keep it at or above all the `TOP_N_` values added together |
| `GRACE_PERIOD_DAYS`      | Days someone keeps VIP after dropping off a leaderboard. `0` removes it straight away |
| `MANUAL_EXCLUDE_LOGINS`  | Manual VIPs and editors: names AutoVIP leaves alone. Replace `ManualVIPUsername1` and the others with real names (one per line), or remove them |
| `IGNORE_LOGINS`          | Bots and accounts that are never tracked |
| `VIP_BLOCK_LIST`         | Viewers who should never get VIP. They're never tracked, never on the boards and never given VIP. Replace `BlockedUsername1` with real names (one per line), or remove it |

### Watch streaks, resets and data

| Setting                  | Description |
|--------------------------|-------------|
| `STREAM_RESTART_MINUTES` | If you go live again within this many minutes of ending (e.g. after a crash), it counts as the same stream, so nobody loses their watch streak. Default `30`. `0` turns it off |
| `RESET_PERIOD_MONTHS`    | `0` never resets, or set a period such as `6`, `12`, `24`… |
| `RESET_START_DATE`       | When reset periods start, e.g. `"2026-01-01"`. Use `""` to start from the first run |
| `RESET_KEEPS_DATA`       | `true` ranks on the current period only and keeps all-time data. `false` wipes everything on reset |
| `INCLUDE_LIFETIME_DATA`  | `true` uses Twitch's lifetime numbers. `false` counts only since the last reset |

### Chat messages

| Setting                  | Description |
|--------------------------|-------------|
| `ANNOUNCE_NEW_VIPS`      | `true` posts in chat when someone earns VIP. `false` turns off every VIP message |
| `ANNOUNCE_STEALS`        | `true` posts a message when someone steals a VIP badge |
| `STEAL_WATCH_STREAK`, `STEAL_SUB_STREAK`, `STEAL_SUB_GIFTERS`, `STEAL_CHEER_BITS` | The steal messages. `{new}` = who got VIP, `{old}` = who lost it, `{amount}` = their bits, subs or streak. `""` turns one off |
| `ANNOUNCE_LOST_VIPS`     | `true` posts a message when someone loses their VIP badge |
| `LOST_WATCH_STREAK`, `LOST_SUB_STREAK`, `LOST_OTHER` | The lost badge messages. `{old}` = who lost it. `""` turns one off |
| `LOST_STOLEN`            | An extra message for the person whose badge was stolen. `""` (off) by default, because the steal message already says it. To switch it on, e.g. `"💔 {old} lost their VIP badge because {new} stole it!"` |

### Overlay and !myrank

| Setting                  | Description |
|--------------------------|-------------|
| `STEAL_OVERLAY`          | `true` sends each steal to the OBS overlay |
| `LEADERBOARD_OVERLAY`    | `true` shows the leaderboards, champions and recap on the overlay. `false` posts the leaderboards in chat instead |
| `LEADERBOARD_SIZE`       | How many names each leaderboard shows (default `10`). Set **Names on each board** on the settings page's **Boards** tab to the same number |
| `LEADERBOARD_PICTURES`   | How many of the top names on each board show their Twitch picture (default `3`) |
| `ENABLE_MYRANK`          | `true` turns on the `!myrank` command |
| `MYRANK_OVERLAY`         | `true` shows `!myrank` as a card on the overlay. `false` answers in chat |
| `SPECIAL_MYRANK_REPLIES` | Your own `!myrank` replies for particular viewers, e.g. `["exampleviewer"] = "@{user} your rank is: Chief Snack Officer!"` |

---

## The OBS overlay (optional)

You don't need the overlay for AutoVIP to work. The chat messages work without it.

### The files

They're in the **Overlay** folder. Keep them together in the same folder, and put any sounds or pictures you want to use in that folder too. Don't rename the files.

| File | What it's for |
|------|---------------|
| `AutoVIP Overlay.html` | The overlay itself. You don't open this one; OBS uses it |
| `AutoVIP Overlay Settings.html` | Open it in your web browser to design the overlay, with a live preview, and copy its OBS links |
| `Streamer.bot Connection Test.html` | Checks the overlay can reach Streamer.bot if something isn't working, and finds the right Address and Port for you |

### What it can show

| Part | What you control |
|------|------------------|
| **Steals** | 5 animations or random, speed lines, flash and shake, the banner wording, sound, colours, fonts, position and size |
| **Per stat** | Bits, gifted subs, sub streak and watch streak can each have their own steal animation, message, timing, sound and colours |
| **Leaderboards** | `!topvips` and the single boards: 5 to 60 names per page, board order, names, skipping boards, timing, an optional champions board at the end, header, photo, sound, colours, fonts, position, size and 11 animations |
| **Champs** | `!vipchamps`: the number one on every board with their picture and a crown. Title, subtitle, timing and its own look |
| **!myrank** | A card with the viewer's rank on every board and how far they are from a VIP spot. Timing and its own look |
| **Recap** | Plays when you switch to your ending scene: 8 styles, timing, title, highlight, and 7 boxes you can switch on or off, reorder and reword. Mods, editors and manual VIPs are left out |
| **Auto show** | Boards that pop up on a timer, only while you're live if you like. Add as many as you want, each with its own board, timer, position and size, all in one link or each with its own link for different scenes |

### Step 1: Switch on Streamer.bot's WebSocket Server

1. In Streamer.bot, go to **Servers/Clients** → **WebSocket Server**.
2. Set the **Address**:

| | **One PC** (Streamer.bot and OBS on the same PC) | **Two PCs** (e.g. Streamer.bot on a gaming PC, OBS on a streaming PC) |
|---|---|---|
| Address | `127.0.0.1` | `0.0.0.0` (this lets the other PC connect) |
| Port | `8080` | `8080` |

3. Tick **Auto Start**, then click **Start Server**. If you changed something, click **Stop Server** then **Start Server**.
4. **Two PCs only:** if Windows asks about the firewall, click **Allow**.

> **Leave the port as `8080`.** Don't change it to `4455`: that's OBS's own port, and the overlay won't work with it.

The overlay goes in the OBS you stream from. Streamer.bot on two PCs? Run AutoVIP in only one of them.

### Step 2: Design your overlay

1. On the PC you stream from, open **`AutoVIP Overlay Settings.html`** in your web browser (double-click it). Two PCs? Copy the whole **Overlay** folder onto the streaming PC first.
2. On the **General** tab, under **Streamer.bot connection**: leave the **Address** as `127.0.0.1` on one PC, or put in the Streamer.bot PC's IP on two PCs. Add a password only if you switched on **Authentication** in Step 1.
3. Go through the tabs (**Steals**, **Per stat**, **Boards**, **Champs**, **!myrank**, **Recap**, **Auto**) and pick your looks. The preview on the right shows each one. Click a **Preview** button to hear the sound too.
4. To use a sound or picture, click **Browse...** and pick it from the **Overlay** folder.
5. If you changed **Names on each board** on the **Boards** tab, set `LEADERBOARD_SIZE` in the code to the same number.

### Step 3: Add it to OBS

Each part has its own **Copy link** button at the top of its tab. For each part you want:

1. Click **Copy link** on that part's tab.
2. In OBS, add a **Browser** source, untick **Local file**, and paste the link into **URL**.
3. Set **Width** to `2560` and **Height** to `1440`, tick **Control audio via OBS**, and click **OK**.
4. Right-click the source → **Transform** → **Fit to screen**. It's see-through until something happens.

> **Copy the link AFTER you've picked your sounds and settings.** Everything, including the sound, is saved inside the link. Changed something later? Copy the link again, clear the URL box in OBS and paste the new link in.

**Auto show:** set it up on the **Auto** tab and add its link as its own browser source. Use the Auto tab's main link for all your auto shows, or each show's own link to put it in a different scene (not both, or it pops up twice). To run a show only while its scene is on screen, tick **Shutdown source when not visible** in that browser source's properties.

**End of stream recap:** put its browser source only in your ending scene, and follow the steps on the **Recap** tab so it plays when you switch to that scene.

**Hearing the sounds yourself:** with **Control audio via OBS** ticked, the sound goes to your stream through the OBS mixer. To hear it too, open the mixer's **Advanced Audio Properties** and set the browser source to **Monitor and Output**.

### Step 4: Test it

1. Type `!teststeal` in chat as a mod or the broadcaster. A pretend steal plays on screen. Nobody's VIP changes.
2. Type `!topvips` to show the leaderboards, and `!myrank` to see your own card.
3. Auto show: set **First one after** to `1` on the **Auto** tab, copy the link into OBS again, and one should pop up a minute later (while you're live, if **Only while live** is ticked). Set it back afterwards.

### If something isn't working

The settings page has a **Help** tab with quick fixes for the common problems. If the overlay shows *"Can't reach Streamer.bot..."* in the top-left corner, open **`Streamer.bot Connection Test.html`** on the streaming PC with Streamer.bot open, and click **Test the connection**.

| Problem | Fix |
|---------|-----|
| WebSocket Server isn't started | Step 1: tick **Auto Start** and click **Start Server** |
| Port set to `4455` | That's OBS's port. Use Streamer.bot's WebSocket Server port, usually `8080` |
| Two PCs, still refusing | Step 1: the address must be `0.0.0.0`, and the firewall must allow it. Step 2: the Address must be the Streamer.bot PC's IP |
| "Streamer.bot wants a password" | Put the WebSocket Server's password on the settings page's **General** tab, or switch Authentication off |
| **Test sound** works but OBS is silent | You picked the sound after copying the link. Copy the link again and paste it into OBS |
| No sound on stream | Tick **Control audio via OBS** on the browser source, and check it isn't muted in the mixer |
| Nothing happens on a steal | Check `STEAL_OVERLAY = true;` in the AUTOVIP code, then type `!teststeal` |

---

## Getting an update

1. Download the new files and copy them over the old ones. Keep your sounds and pictures in the **Overlay** folder.
2. Copy your settings and Manual VIPs list from the top of the **AUTOVIP** code somewhere safe.
3. In Streamer.bot, import the new **AutoVIP** file. If Streamer.bot keeps your old actions instead of replacing them, delete the old **AutoVIP** actions and commands first, then import.
4. Put your settings back at the top of the code and click **Save and Compile**.
5. Open the settings page and **copy every link again**, one for each OBS browser source. Clear each URL box in OBS and paste the new link in.

Your viewers' stats are saved separately and aren't lost. Old OBS links keep working, but only with the old settings: new features and fixed sounds only reach OBS through a fresh link.

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
