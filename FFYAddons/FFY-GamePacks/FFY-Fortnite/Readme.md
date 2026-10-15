# FFY Fortnite

Fortnite commands for your stream: drop spots, emotes, skins, loot, box fights and Victory Royale of the Day. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Fortnite`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!victoryroyale` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Fortnite** folder and untick **Enabled** on the ones you don't want.

---

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

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Fortnite** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Fortnite Numbers** | The number commands (min, max and the reply) |
| **FFY Fortnite Lists** | The pick-from-a-list commands |
| **FFY Fortnite Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Fortnite Duels** | The duels |
| **FFY Fortnite Of The Day** | The "of the Day" titles |
| **FFY Fortnite Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Fortnite Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Fortnite]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Fortnite** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
