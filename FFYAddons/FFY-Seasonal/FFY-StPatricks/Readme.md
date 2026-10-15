# FFY StPatricks

St Patrick's Day commands: the luck of the Irish, pots of gold, jig-offs and Leprechaun of the Day. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-StPatricks`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!irish` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY StPatricks** folder and untick **Enabled** on the ones you don't want.

---

## The commands (10)

| Command | What it is | Example reply |
|---|---|---|
| `!irish` | 0–100 % | @Bob, you're 50% Irish today! Sláinte! |
| `!leprechaun` | 0–100 % | @Bob, you're 50% leprechaun today! Hide your gold. |
| `!lucky` | 0–100 % | @Bob, the luck of the Irish is 50% with you today! |
| `!green` | 0–100 % | @Bob, you're wearing 50% green today! |
| `!potofgold` | 8 choices | @Bob reached the end of the rainbow and found a pot of gold coins! |
| `!irishblessing` | 6 choices | An Irish blessing for @Bob: May the road rise up to meet you. |
| `!jig` | 6 choices | @Bob danced a perfect Irish jig! |
| `!pinch @Sam` | Interaction | @Bob Pinched @Sam with 73% power! |
| `!jigoff @Sam` | Duel | @Bob won the jig-off (87 vs 38)! @Sam tripped over a shamrock. |
| `!leprechaunofday` | Leprechaun of the Day | Who won today. Win it by getting 100% on `!leprechaun` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY StPatricks** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY StPatricks Numbers** | The number commands (min, max and the reply) |
| **FFY StPatricks Lists** | The pick-from-a-list commands |
| **FFY StPatricks Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY StPatricks Duels** | The duels |
| **FFY StPatricks Of The Day** | The "of the Day" titles |
| **FFY StPatricks Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY StPatricks Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY StPatricks]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY StPatricks** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
