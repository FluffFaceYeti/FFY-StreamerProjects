# Mod_Appreciation

Show your mods some love. It tracks your mods' watch streaks, sub streaks, gifted subs and bits like AutoVIP does, and adds ways for you and your chat to thank them: viewer thank-yous, a Mod of the Stream, a thank-you at the end of every stream, streak milestones and more.

```
Mia: !modchamps
Chat: 🏆 Mod Champs: Watch Streak: Mia (42 streams) | Most Thanked: Sam (67 thanks) | Chat Guard: Bea (118 timeouts and bans) | ...
Bob: !thankmod @Mia
Chat: ❤️ @Bob thanked @Mia! They've been thanked 12 times.
```

- **It never changes anyone's badges.** It can't give or take mod or VIP on Twitch. It only reads stats and shows them in chat and on the overlay.
- **It's its own system.** It has its own action, commands and saved stats, and it never changes anything AutoVIP uses.
- **You don't need AutoVIP.** If you have it, your mods can start with their AutoVIP numbers.
- **No list of names to keep up to date.** It notices who has the sword when they chat, and only uses that to decide who shows on its boards.
- Twitch only.

---

## Installing

1. In Streamer.bot, click **Import** in the bar at the top, drag and drop the **`Mod_Appreciation`** file into the box, and click **Import**.

Done. The commands are switched on and the triggers are set up. Your mods appear as soon as they chat.

Everything you can change is at the very top of the code. Open the **Mod_Appreciation** action in the **Actions** tab, double-click **Execute C# Code**, edit the `Settings` part, and click **Save and Compile**.

---

## The commands

| Command | Who can use it | What it does |
|---|---|---|
| `!modchamps` | Mods | The top mod on every board. |
| `!modtop` | Mods | The top mods on a board, e.g. `!modtop guard`. On its own, it shows the first board. |
| `!modrank` | Mods | A mod's stats and place on each board. Add a name to see someone else's, e.g. `!modrank @Mia`. |
| `!modrecap` | Mods | How the mods got on this stream, or last stream if you're between streams. |
| `!thankmod @name` | Everyone | Thanks a mod. Each viewer can thank the same mod once every 30 minutes. |
| `!appreciatemod @name message` | Only you | Your own thank you to a mod. The message is optional. On its own, `!appreciatemod` thanks every mod who was here this stream. |
| `!setmodstreak @name 120` | Only you | Sets a mod's watch streak, if their number needs correcting. |
| `!testmodcard` | Mods | Sends a test card to the overlay. |

Set `OnlyModsCanCheck = false;` to let everyone use the first four.

### The boards

Use these names with `!modtop`.

| Name | Board | How it counts |
|---|---|---|
| `streak` | Watch Streak | Streams in a row with the mod there. |
| `sub` | Sub Streak | Months in a row subbed, when they share a resub. |
| `gifted` | Gifted Subs | Subs they've gifted. |
| `bits` | Bits | Bits they've cheered. |
| `thanks` | Most Thanked | Each `!thankmod` and `!appreciatemod`. |
| `guard` | Chat Guard | Timeouts and bans they've given. |
| `mvp` | Mod of the Stream | How many times they've won. |
| `streams` | Streams Modded | Streams they've been at in total. |

To rename a board, change its name or unit in its `Board` line. Change `true` to `false` to hide it.

---

## The switches

`true` = on, `false` = off.

| Switch | Starts as | What it does |
|---|---|---|
| `ChatMessages` | `true` | Sends everything in chat. |
| `Overlay` | `true` | Sends everything to the OBS overlay. |
| `OnlyModsCanCheck` | `true` | Only mods can use `!modchamps`, `!modtop`, `!modrank` and `!modrecap`. |
| `StartFromAutoVIP` | `true` | The first time a mod joins the list, copies their AutoVIP numbers across. It only reads them, and it's only done once. |
| `LurkingCounts` | `false` | Counts a mod as here if they're in chat without talking. Also switch on **Present Viewers** in Streamer.bot's Twitch settings. |
| `WelcomeMods` | `false` | Says hello in chat when a mod first talks each stream. |
| `ThankYouAtStreamEnd` | `true` | Thanks the mods and names the Mod of the Stream when you go offline. |
| `MilestoneMessages` | `true` | Celebrates when a mod hits a watch streak in the `Milestones` line. |

### The numbers

| Setting | Starts as | What it does |
|---|---|---|
| `StreamRestartMinutes` | 30 | If you come back within this many minutes, it counts as the same stream. |
| `TopCount` | 5 | How many mods show on `!modtop`. |
| `ThanksCooldownMinutes` | 30 | How long before the same viewer can thank the same mod again. |
| `MessagePoints`, `ModActionPoints`, `ThanksPoints` | 1, 5, 10 | How the Mod of the Stream is picked: points for each chat message, each timeout or ban, and each thank you that stream. |

### Who counts as a mod

This only decides who shows on the boards here. It never changes anything on Twitch.

Mods join the boards when they chat with the sword, or when they time out or ban someone. They leave the boards when they chat without it, or when you unmod them on Twitch. Their stats are kept, in case they come back.

- `AlwaysCount("name", "name2");` always counts someone, even without the sword.
- `NeverCount(...)` never counts them. Your bots go here. Add any bot that isn't listed.

You never count yourself. Timeouts and bans by a bot aren't counted once it's in `NeverCount`.

### Messages

Every chat message is a `Message` line, so you can reword any of them. Leave the text empty (`""`) to switch one off.

---

## When things update

- **Watch streaks** are worked out once your stream has properly ended: when you next go live, or when someone uses a command after `StreamRestartMinutes` has passed. So `!modchamps` right after you go offline can still show the old streak.
- **A mod is "here"** if they chat, or give a timeout or ban, or share their watch streak while you're live. Chatting while you're offline doesn't count.
- **Twitch watch streak shares** replace the mod's streak with Twitch's number.

**How it knows you're live:** Streamer.bot's Stream Online trigger, or OBS streaming if Streamer.bot is connected to OBS. If you open Streamer.bot after you've gone live and it isn't connected to OBS, the stream won't count until the next Stream Online.

---

## The overlay

You can skip this if you only want it in chat. Set `Overlay = false;` in that case.

1. In Streamer.bot, go to **Servers/Clients > WebSocket Server**, and make sure it's running.
2. Keep **`Mod_Appreciation-Overlay.html`** and **`Mod_Appreciation-Settings.html`** in the same folder.
3. Open **`Mod_Appreciation-Settings.html`** in your browser. Flip the switches and pick your colours, or click one of the six themes under **Colours**. The preview updates as you go, and the list next to **Play the animation** shows each card.
4. Click **Copy link for OBS**.
5. In OBS, add a **Browser** source, paste the link into **URL** (leave **Local file** unticked), and set the size to **1920 x 1080**.
6. Type `!testmodcard` in chat to check it's working.

If you change a setting later, copy the link again and paste it over the old one. If several cards come in at once, they show one after another.

You can run this next to AutoVIP's overlay. They're separate and each ignores the other's cards.

---

## Editing someone's stats

Stats are saved per user in Streamer.bot, under **Variables > Persisted User Globals**. They all start with `modApp.`, e.g. `modApp.watchStreak`, and you can change them there. AutoVIP's are separate, so changing one never touches the other.

## Troubleshooting

| Problem | Try this |
|---|---|
| A mod isn't on the boards | They need to chat first. A board only lists mods with more than 0. Anything with nothing to show says **No data yet**, in chat and on the overlay. |
| Someone who isn't a mod is on the boards | Add them to `NeverCount`, or have them chat so the sword check updates. |
| `!modchamps` does nothing | Only mods can use it unless `OnlyModsCanCheck = false;`. |
| Watch streaks aren't going up | The streak updates when the next stream starts. Check Stream Online and Offline are firing, and that the mod chatted while you were live. |
| Mods keep losing their streak | Streaks need every stream. Set `LurkingCounts = true;` if they often watch without chatting. |
| A mod's watch streak is wrong | Use `!setmodstreak @name 120`. Or have them share their streak on Twitch, which replaces it with Twitch's number. |
| Numbers look different from AutoVIP | They're only copied once. After that, each system keeps its own count. |
| The overlay shows nothing | Is `Overlay = true;`? Is the WebSocket Server running? Any problem with the connection shows in the bottom corner of the overlay. |
