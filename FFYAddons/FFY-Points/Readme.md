# FFY_Points

Your own channel points, with your own name for them. Viewers earn them by chatting and watching (lurkers too), and you can run point events where everyone types `!join` for a chance to win more.

```
Mia: !points
Chat: @Mia has 1,240 Fluff.
Mod: !pointevent hunt
Chat: Point Hunt has started! Type !join in the next 60 seconds for a chance to win 500 Fluff! 3 lucky winners.
...
Chat: Point Hunt is over! @Mia, @Sam, @Bob won 500 Fluff!
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- **You name your points** and choose how many people earn for everything.
- **Point events** with your own pictures, GIFs, videos and sounds on an OBS overlay.
- Viewers can spend their points on entries in the **FFY Giveaway Tool**.

---

## Installing

You don't need to edit any code. The builder page makes the import for you.

1. Download this whole folder.
2. Open **`FFY_Points Builder.html`** in your browser.
3. Fill in the boxes, then press **Make my import** and **Copy**.
4. In Streamer.bot, click **Import** in the bar at the top, paste it in and click **Import**.
5. For points from watching, go to **Platforms > Twitch > Settings** in Streamer.bot and make sure **Present Viewers** is on.

Just want to try it first? Import the **`FFY_Points`** file instead. It has the default settings.

**Changing something later:** open the builder again, change it, make a new import and import it over the old one. Everyone keeps their points. The builder remembers your boxes in that browser. On another PC, paste your last import into **Your saved settings** and press **Load**.

---

## Earning

It works like StreamElements loyalty points. The **Points** page of the builder shows exactly what everyone gets as you change it.

| What | Default | |
| --- | --- | --- |
| Watching | 10 every 10 minutes | Lurkers count too. Uses Streamer.bot's Present Viewers. Pick 1 to 30 minutes. |
| Follower bonus | 50 | Twitch, Kick, and YouTube subscribers |
| Subscriber bonus | 250 | Twitch and Kick |
| Gifted sub bonus | 250 for every sub gifted | Twitch and Kick, to the gifter |
| Cheer bonus | 100 for every 100 bits | Twitch |
| Raid bonus | 100 | Twitch, to the raider |
| Tip bonus | 10 for every 1 tipped | StreamElements, Streamlabs, Ko-fi, TipeeeStream and Fourthwall |
| Chat bonus | Off | Points per chat message, once a minute at most. |

- Watching and chat points are only earned while you're live, unless you switch off **Only while I'm live**. Bonuses always count.
- **Points enabled** switches off all earning. Commands and point events still work.
- Tips go to the Twitch account with the tipper's name, and anonymous tips are skipped.
- Bots in **Ignored users** never earn.
- Everyone earns the same for watching and chatting. Subscribers don't get extra, so points stay fair when they're spent on giveaway tickets.

---

## Commands

| Command | Who | What it does |
| --- | --- | --- |
| `!points` | Everyone | Shows your points. `!points @Sam` shows Sam's. |
| `!pointstop` | Everyone | The leaderboard. |
| `!givepoints @Sam 50` | Everyone | Gives 50 of your points to Sam. You can switch this off. |
| `!join` | Everyone | Joins the point event that's running. |
| `!addpoints @Sam 100` | You and mods | Gives Sam 100 points. |
| `!removepoints @Sam 100` | You and mods | Takes 100 points from Sam. |
| `!bonus 5000` | You and mods | Gives 5,000 points to everyone watching or chatting in the last 10 minutes. `!bonus 5000 all` does the same. |
| `!bonus 5000 @Sam` | You and mods | Gives Sam 5,000 points. |
| `!pointevent hunt` | You and mods | Starts the event called hunt. `!pointevent` on its own starts a random one. |

You can rename every command in the builder.

---

## Point events

The builder comes with three: **Point Hunt** (3 winners of 500), **Point Drop** (1 winner of 1000) and **Point Rain** (10 winners of 100). Change them, remove them or add your own. Each one has:

- a short name, used after the start command
- a title, the prize each winner gets, how many win, and how long people have to join
- a picture, GIF or video and a sound for the overlay, both optional
- its own start message, if you want one

Winners are picked at random from everyone who joined. You can also have a random event start by itself every so many minutes while you're live.

### The overlay

1. In OBS, add a **Browser Source**.
2. Tick **Local file** and pick **`FFY_Points Overlay.html`**.
3. Set the size to your canvas, e.g. 1920 × 1080.

It only shows up while an event is running, then shows the winners and hides again. It connects to Streamer.bot's WebSocket server, so make sure that's on (**Servers/Clients > WebSocket Server**, port 8080).

Streamer.bot on another PC? Untick **Local file** and use this as the URL instead, with your Streamer.bot PC's address:

```
file:///C:/path/to/FFY_Points Overlay.html?host=192.168.1.20&port=8080
```

Or open the overlay file in Notepad and change `127.0.0.1` and `8080` under `// SETTINGS`.

If your WebSocket server has a password, add `&password=yourpassword` to the end.

Pictures, GIFs, videos and sounds can be links or files saved on your PC. In the builder, hold **Shift**, right-click the file in File Explorer, pick **Copy as path** and paste it in. A preview shows underneath so you know it works. Local files only show when the overlay is added with **Local file** ticked (or a `file:///` URL), and the file has to be on the PC that runs OBS.

---

## For the Giveaway Tool and other apps

Anything connected to Streamer.bot's WebSocket can run the **FFY_Points** action with these arguments. The answer comes back as a `General.Custom` event with `source` set to `FFY_Points` and the same `requestId`.

| `ffyPoints` | Other arguments | Does |
| --- | --- | --- |
| `balance` | `user`, `platform` | Returns their points. |
| `spend` | `user`, `amount`, `platform` | Takes the points if they have enough. `ok` is false if they don't. |
| `add` | `user`, `amount`, `platform` | Gives points, e.g. a refund. |
| `startEvent` | `eventName` | Starts an event. Leave the name empty for a random one. |
| `info` | | Returns the points name and the events. |

`platform` is `twitch` if you leave it out.
