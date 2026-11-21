# FFY_Points

Your own channel points, with your own name for them. Viewers earn them just by hanging out: watching (lurkers count too), following, raiding and more. Then every so often you run a point event, and everyone scrambles to type `!join` for a chance to win a pile of them.

```
Mia: !points
Chat: @Mia has 1,240 Fluff.
Mod: !pointevent hunt
Chat: Point Hunt has started! Type !join in the next 60 seconds for a chance to win 500 Fluff! 3 lucky winners.
Sam: !join
Bob: !join
Mia: !join
Chat: Point Hunt is over! @Mia, @Sam, @Bob won 500 Fluff!
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- **Call your points whatever you like**: Fluff, Cookies, Bananas...
- **Point events** can pop up on stream with your own pictures, GIFs, videos and sounds.
- Viewers can spend their points on tickets with **FFY Web Giveaway**.
- **No code to edit.** A builder page makes the import for you.

---

## Installing

1. Download this whole folder.
2. Open **`FFY_Points Builder.html`** in your browser.
3. Name your points, set how people earn them, and make your point events. The **Points** page shows exactly what everyone gets as you go.
4. Press **Make my import**, then **Copy**.
5. In Streamer.bot, click **Import** in the bar at the top, paste it in and click **Import**.
6. For points from watching, go to **Platforms > Twitch > Settings** in Streamer.bot and make sure **Present Viewers** is on.

Just want to try it first? Import the **`FFY_Points`** file instead. It has the default settings, and you can make your own import later.

**Changing something later?** Open the builder, change it, make a new import and import it over the old one. Nobody loses their points. The builder remembers your settings in that browser. On another PC, press **Load settings**, paste in your last import and press **Load**.

---

## How people earn

It works a lot like StreamElements loyalty points. Here's what everyone gets to start with. You can change all of it in the builder.

| What | Starts at | |
| --- | --- | --- |
| Watching | 10 every 10 minutes | Lurkers count too. You pick how often, from every minute to every 30 minutes. |
| Following | 50 | Twitch and Kick follows, and YouTube subscribers. |
| Subscribing | 250 | Twitch and Kick. |
| Gifting subs | 250 for every sub gifted | Twitch and Kick, to the person gifting. |
| Cheering | 100 for every 100 bits | Twitch. |
| Raiding | 100 | Twitch, to the raider. |
| Tipping | 10 for every 1 tipped | StreamElements, Streamlabs, Ko-fi, TipeeeStream and Fourthwall. |
| Chatting | Off | Turn it on to give points per message, once a minute at most, so spamming doesn't pay. |

A few things worth knowing:

- **Everyone earns the same** for watching and chatting. Subscribers don't get extra, so it stays fair when points are spent on giveaway tickets.
- Watching and chatting only earn while you're live, unless you switch off **Only while I'm live**. The bonuses always count.
- Tips go to the Twitch account with the tipper's name. Anonymous tips are skipped.
- Bots in **Ignored users** never earn. Nightbot, StreamElements and the usual ones are already on the list.
- Need a break from points? Switch off **Points enabled**. Nobody earns anything, but the commands and point events still work.

---

## Commands

| Command | Who | What it does |
| --- | --- | --- |
| `!points` | Everyone | Shows your points. `!points @Sam` shows Sam's. |
| `!pointstop` | Everyone | The leaderboard. |
| `!givepoints @Sam 50` | Everyone | Gives Sam 50 of your points. You can switch this off. |
| `!join` | Everyone | Joins the point event that's running. |
| `!addpoints @Sam 100` | You and mods | Gives Sam 100 points. |
| `!removepoints @Sam 100` | You and mods | Takes 100 points from Sam. |
| `!bonus 5000` | You and mods | Gives 5,000 points to everyone who's watched or chatted in the last 10 minutes. Great for celebrating a raid or a big moment. |
| `!bonus 5000 @Sam` | You and mods | Gives just Sam 5,000 points. |
| `!pointevent hunt` | You and mods | Starts the event called hunt. `!pointevent` on its own picks a random one. |

Don't like a command's name? Rename any of them in the builder.

---

## Point events

You start with three, and you can change them, remove them or add your own:

- **Point Hunt**: 3 winners get 500 each.
- **Point Drop**: 1 lucky winner gets 1,000.
- **Point Rain**: 10 winners get 100 each.

For each one you pick a short name (the bit after `!pointevent`), a title, the prize, how many win and how long people have to join. You can also give it a picture, GIF or video, a sound and its own start message.

Winners are picked at random from everyone who joined. Want them to happen by themselves? Set a random event to start every so many minutes while you're live.

### The overlay

When an event starts, it can pop up on stream with your picture and sound, count people joining, then show off the winners and hide again.

1. In Streamer.bot, go to **Servers/Clients > WebSocket Server** and make sure it's running (port 8080 normally).
2. In OBS, add a **Browser Source**.
3. Tick **Local file** and pick **`FFY_Points Overlay.html`**.
4. Set the size to your canvas, e.g. 1920 × 1080.

It stays invisible until an event starts.

**Streamer.bot on another PC?** Untick **Local file** and use this as the URL instead, with your Streamer.bot PC's address:

```
file:///C:/path/to/FFY_Points Overlay.html?host=192.168.1.20&port=8080
```

If your WebSocket Server has a password, add `&password=yourpassword` to the end.

**Using your own pictures and sounds:** they can be links, or files on your PC. For a file, hold **Shift**, right-click it in File Explorer, pick **Copy as path** and paste it into the builder. A preview shows underneath so you know it's worked. Files on your PC only show when the overlay is added with **Local file** ticked, and they have to be on the PC that runs OBS.

---

## Using your points in giveaways

Want viewers to spend their points on giveaway tickets? Set up your own **[FFY Web Giveaway](../FFY-WebGiveaway/Readme.md)** site, then make your import with the **Points Builder** on your giveaway site instead of this one. It's the same thing, with an extra box that links your points to the site. Everyone keeps the points they've already got.

---

## Troubleshooting

| Problem | Try this |
| --- | --- |
| Nobody earns from watching | Is **Present Viewers** on in Streamer.bot's Twitch settings? Are you live? Points only come every few minutes, so give it a bit. |
| Someone isn't earning | Check they're not in **Ignored users**. You don't earn in your own chat unless you turn that on. |
| The overlay shows nothing | Is the WebSocket Server running? Start an event with `!pointevent` to test it. |
| A picture or sound doesn't show | If it's a file, is it on the PC that runs OBS, and is **Local file** ticked? Check the preview in the builder. |
| I changed something and nothing happened | Make a new import in the builder and import it again. Points are kept. |

---

## For other apps

This is the techy bit. You only need it if you're making your own app that uses FFY_Points.

Anything connected to Streamer.bot's WebSocket can run the **FFY_Points** action with these arguments. The answer comes back as a `General.Custom` event with `source` set to `FFY_Points` and the same `requestId`.

| `ffyPoints` | Other arguments | Does |
| --- | --- | --- |
| `balance` | `user`, `platform` | Returns their points. |
| `spend` | `user`, `amount`, `platform` | Takes the points if they have enough. `ok` is false if they don't. |
| `add` | `user`, `amount`, `platform` | Gives points, e.g. a refund. |
| `startEvent` | `eventName` | Starts an event. Leave the name empty for a random one. |
| `info` | | Returns the points name and the events. |

`platform` is `twitch` if you leave it out.
