# FFY Summer

Sunny summer commands: sunburn, ice cream, beach finds, sandcastle contests and Lobster of the Day. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Summer`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!sunburn` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Summer** folder and untick **Enabled** on the ones you don't want.

---

## The commands (12)

| Command | What it is | Example reply |
|---|---|---|
| `!sunburn` | 0–100 % | @Bob, you're 50% sunburnt today! Ouch. |
| `!tan` | 0–100 % | @Bob, your tan is 50% golden today! |
| `!icecream` | 0–10 scoops | @Bob, you've had 5 scoops of ice cream today! |
| `!heatwave` | 18–40 °C | @Bob, it's 29°C where you are today. Melting! |
| `!beachready` | 0–100 % | @Bob, you're 50% beach ready today! |
| `!getaway` | 8 choices | @Bob, your summer getaway today is a beach in Spain! |
| `!icecreamflavour` | 8 choices | @Bob's ice cream today is mint choc chip! |
| `!beachfind` | 8 choices | @Bob found a perfect seashell on the beach! |
| `!splash @Sam` | Interaction | @Bob Splashed @Sam with 73% power! |
| `!waterballoon @Sam` | Interaction | @Bob Threw a water balloon at @Sam with 73% power! |
| `!sandcastle @Sam` | Duel | @Bob's sandcastle wins (87 vs 38)! @Sam's collapsed into a sad lump. |
| `!lobsterofday` | Lobster of the Day | Who won today. Win it by getting 100% on `!sunburn` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Summer** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Summer Numbers** | The number commands (min, max and the reply) |
| **FFY Summer Lists** | The pick-from-a-list commands |
| **FFY Summer Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Summer Duels** | The duels |
| **FFY Summer Of The Day** | The "of the Day" titles |
| **FFY Summer Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Summer Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Summer]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Summer** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
