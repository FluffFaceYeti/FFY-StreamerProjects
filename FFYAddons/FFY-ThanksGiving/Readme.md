#  FFY ThanksGiving

Silly, turkey-filled Thanksgiving commands. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-ThanksGiving`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!turkey` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY ThanksGiving** folder and untick **Enabled** on the ones you don't want.

---

## The commands (12)

| Command | What it is | Example reply |
|---|---|---|
| `!turkey` | 0–100 % | @Bob, you're 50% turkey today! Gobble gobble! |
| `!gobble` | 0–120 dB | @Bob, your gobble is 60 decibels today! |
| `!foodcoma` | 0–100 % | @Bob, you're 50% into a food coma today. Undo that top button. |
| `!gravy` | 0–5 litres | @Bob, you've had 3 litres of gravy today! That's a lot of gravy. |
| `!pilgrim` | 0–100 % | @Bob, you're 50% pilgrim today! |
| `!stuffing` | 8 choices | @Bob, your stuffing today is Sage and Onion! |
| `!pie` | 8 choices | @Bob, your Thanksgiving pie today is Pumpkin Pie! |
| `!thankful` | 11 choices | @Bob is thankful for pizza today! |
| `!leftovers` | 7 choices | @Bob's leftovers today: a turkey sandwich! |
| `!carve` | 6 choices | @Bob carved the turkey and made perfect, even slices! |
| `!wishbone @Sam` | Duel | @Bob got the big half of the wishbone (87 vs 38)! Make a wish, @Bob! |
| `!turkeyofday` | Turkey of the Day | Who won today. Win it by getting 100% on `!turkey` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY ThanksGiving** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY ThanksGiving Numbers** | The number commands (min, max and the reply) |
| **FFY ThanksGiving Lists** | The pick-from-a-list commands |
| **FFY ThanksGiving Duels** | The duels |
| **FFY ThanksGiving Of The Day** | The "of the Day" titles |
| **FFY ThanksGiving Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY ThanksGiving Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY ThanksGiving]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY ThanksGiving** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
