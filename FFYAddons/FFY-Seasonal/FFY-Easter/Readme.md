# FFY Easter

Egg-cellent Easter commands: egg hunts, Easter bunny names, egg and spoon races and Easter Bunny of the Day. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Easter`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!egghunt` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Easter** folder and untick **Enabled** on the ones you don't want.

---

## The commands (11)

| Command | What it is | Example reply |
|---|---|---|
| `!egghunt` | 0–50 eggs | @Bob, you found 25 Easter eggs today! Check behind the sofa for more. |
| `!bunny` | 0–100 % | @Bob, you're 50% Easter Bunny today! Hop to it. |
| `!sugarrush` | 0–100 % | @Bob, your chocolate sugar rush is at 50% today! |
| `!eggcellent` | 0–100 % | @Bob, you're 50% eggcellent today! |
| `!hotcrossbun` | 0–12 buns | @Bob, you've eaten 6 hot cross buns today! |
| `!easteregg` | 10 choices | @Bob cracked open their Easter egg and found a tiny chick! |
| `!bunnyname` | 8 choices | @Bob, your Easter Bunny name today is Sir Hops-a-Lot! |
| `!bonnet` | 8 choices | @Bob, your Easter bonnet today is covered in daffodils! |
| `!eggtoss @Sam` | Interaction | @Bob Threw an Easter egg at @Sam with 73% power! |
| `!eggrace @Sam` | Duel | @Bob won the egg and spoon race (87 vs 38)! @Sam's egg is on the floor. |
| `!bunnyofday` | Easter Bunny of the Day | Who won today. Win it by getting 100% on `!bunny` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Easter** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Easter Numbers** | The number commands (min, max and the reply) |
| **FFY Easter Lists** | The pick-from-a-list commands |
| **FFY Easter Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Easter Duels** | The duels |
| **FFY Easter Of The Day** | The "of the Day" titles |
| **FFY Easter Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Easter Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Easter]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Easter** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
