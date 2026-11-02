# FFY Fortnite

Fortnite commands for when you're dropping in. Where to land, emotes, skins, loot, box fights and a Victory Royale of the Day.

You'll need **FFY Commands** installed before this one, as it runs on top of it.

## Installing

Download the **`FFY-Fortnite`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it, the commands are already switched on. Try `!victoryroyale` in chat.

If there are a few you don't want, go to the **Commands** tab, open the **FFY Fortnite** folder and untick **Enabled** on those.

## The commands (14)

| Command | What it is | Example reply |
|---|---|---|
| `!victoryroyale` | 0–100 % | @Bob, you're 50% Victory Royale today! |
| `!builder` | 0–100 % | @Bob, your building skills are at 50% today! 90s for days. |
| `!sweat` | 0–100 % | @Bob, you're 50% sweaty today. Calm down! |
| `!vbucks` | 0–13500 V-Bucks | @Bob, you've got 6750 V-Bucks today! |
| `!elims` | 0–30 elims | @Bob, you got 15 eliminations today! |
| `!noskin` | 0–100 % | @Bob, you're 50% default skin today! |
| `!drop` | 10 choices | @Bob, you're dropping at Tilted Towers today! |
| `!emote` | 10 choices | @Bob hit the Floss on the battle bus! |
| `!fortniteskin` | 10 choices | @Bob, you're rocking the Peely skin today! |
| `!loot` | 10 choices | @Bob opened a chest and got a gold Pump Shotgun! |
| `!emoteon @Sam` | Interaction | @Bob Emoted on @Sam with 73% power! |
| `!crank @Sam` | Interaction | @Bob Cranked 90s on @Sam with 73% power! |
| `!boxfight @Sam` | Duel | @Bob won the box fight (87 vs 38)! @Sam gets sent back to the lobby. |
| `!victoryroyaleofday` | Victory Royale of the Day | Who won today. Win it by getting 100% on `!victoryroyale` |

## Changing things

Head to the **Actions** tab and open the **FFY Fortnite** group. Double-click **Execute C# Code** in the action you want, change the bits between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile** when you're done.

| Action | What's in it |
|---|---|
| **FFY Fortnite Numbers** | The number commands (min, max and the reply) |
| **FFY Fortnite Lists** | The pick-from-a-list commands |
| **FFY Fortnite Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Fortnite Duels** | The duels |
| **FFY Fortnite Of The Day** | The "of the Day" titles |
| **FFY Fortnite Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Fortnite Setup** | Runs once on import |

Want to add your own command? The FFY Commands guide shows how to add a number or list command. Put the lines in **FFY My Number Commands** or **FFY My List Commands** and updates will never touch them.

These work with all the usual FFY Commands stuff as well, like special users, user variables, the switches and `!top` for the interactions.

## Troubleshooting

- **Nothing replies:** is **FFY Commands** installed? Look for `[FFY Fortnite]` in the **Logs** tab.
- **Only one command is quiet:** check it's switched on in the **Commands** tab, in the **FFY Fortnite** folder.

For anything else, there's a troubleshooting section in the FFY Commands guide.
