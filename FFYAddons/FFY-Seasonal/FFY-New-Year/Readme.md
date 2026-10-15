# FFY New Year

New Year commands: resolutions, predictions, party hats, countdown clashes and Party Animal of the Day. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-New-Year`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!resolution` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY New Year** folder and untick **Enabled** on the ones you don't want.

---

## The commands (11)

| Command | What it is | Example reply |
|---|---|---|
| `!resolution` | 0–100 % | @Bob, there's a 50% chance you keep your New Year's resolution! |
| `!partyanimal` | 0–100 % | @Bob, you're 50% party animal tonight! |
| `!hangover` | 0–100 % | @Bob, your New Year's hangover is at 50%. Drink water! |
| `!newyou` | 0–100 % | @Bob, you're 50% new you this year! |
| `!newyearresolution` | 8 choices | @Bob's New Year's resolution: go to the gym (twice)! |
| `!prediction` | 8 choices | @Bob's prediction for the new year: you'll win something big! |
| `!partyhat` | 7 choices | @Bob is wearing a glittery top hat to the New Year party! |
| `!cheers @Sam` | Interaction | @Bob Raised a glass with @Sam with 73% power! |
| `!auldlangsyne @Sam` | Interaction | @Bob Sang Auld Lang Syne with @Sam with 73% power! |
| `!countdownclash @Sam` | Duel | @Bob shouted HAPPY NEW YEAR first (87 vs 38)! @Sam was still on "three". |
| `!partyanimalofday` | Party Animal of the Day | Who won today. Win it by getting 100% on `!partyanimal` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY New Year** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY New Year Numbers** | The number commands (min, max and the reply) |
| **FFY New Year Lists** | The pick-from-a-list commands |
| **FFY New Year Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY New Year Duels** | The duels |
| **FFY New Year Of The Day** | The "of the Day" titles |
| **FFY New Year Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY New Year Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY New Year]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY New Year** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
