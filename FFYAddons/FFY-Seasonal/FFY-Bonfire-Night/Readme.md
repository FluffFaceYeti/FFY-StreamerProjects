# FFY Bonfire Night

Bonfire Night commands: sparklers, fireworks, toffee apples, firework-offs and Guy of the Day. Remember, remember! An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Bonfire-Night`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!sparkler` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Bonfire Night** folder and untick **Enabled** on the ones you don't want.

---

## The commands (11)

| Command | What it is | Example reply |
|---|---|---|
| `!sparkler` | 0–100 % | @Bob, your sparkler skills are at 50% today! |
| `!fireworks` | 0–100 % | @Bob, your fireworks are 50% spectacular today! Oooooh! |
| `!toffeeapple` | 0–10 toffee apples | @Bob, you've eaten 5 toffee apples today! Mind your teeth. |
| `!guy` | 0–100 % | @Bob, you're 50% Guy Fawkes today. Remember, remember! |
| `!firework` | 8 choices | @Bob set off a Catherine wheel that won't spin! |
| `!sparklerword` | 8 choices | @Bob wrote your name (backwards) with their sparkler! |
| `!bonfirefood` | 8 choices | @Bob's Bonfire Night food today is a jacket potato wrapped in foil! |
| `!toffeeshare @Sam` | Interaction | @Bob Shared a toffee apple with @Sam with 73% power! |
| `!rocket @Sam` | Interaction | @Bob Set off a rocket for @Sam with 73% power! |
| `!fireworkoff @Sam` | Duel | @Bob wins the firework-off (87 vs 38)! @Sam's rocket fizzled out. |
| `!guyofday` | Guy of the Day | Who won today. Win it by getting 100% on `!guy` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Bonfire Night** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Bonfire Night Numbers** | The number commands (min, max and the reply) |
| **FFY Bonfire Night Lists** | The pick-from-a-list commands |
| **FFY Bonfire Night Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Bonfire Night Duels** | The duels |
| **FFY Bonfire Night Of The Day** | The "of the Day" titles |
| **FFY Bonfire Night Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Bonfire Night Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Bonfire Night]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Bonfire Night** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
