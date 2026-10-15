# FFY Halloween

Spooky, silly Halloween commands, including some **Nightmare Before Christmas** ones. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Halloween`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!spooky` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Halloween** folder and untick **Enabled** on the ones you don't want.

---

## The commands (17)

| Command | What it is | Example reply |
|---|---|---|
| `!spooky` | 0–100 % | @Bob, you're 50% spooky today! Boo! |
| `!witch` | 0–100 % | @Bob, you're 50% witch today! Mind the broomstick. |
| `!vampire` | 0–100 % | @Bob, you're 50% vampire today! Stay out of the sun. |
| `!zombie` | 0–100 % | @Bob, you're 50% zombie today... braaaains! |
| `!haunted` | 0–100 % | @Bob, your house is 50% haunted today! Did you hear that? |
| `!jack` | 0–100 % | @Bob, your Pumpkin King energy is at 50% today! What's this?! |
| `!zero` | 0–100 % | @Bob, Zero the ghost dog follows you 50% loyally today! |
| `!costume` | 12 choices | @Bob, your Halloween costume today is: Vampire! |
| `!pumpkin` | 10 choices | @Bob, you carved a Scary Face into your pumpkin today! |
| `!candy` | 10 choices | @Bob, you got A Full-Size Chocolate Bar in your trick-or-treat bag today! |
| `!trickortreat` | 7 choices | @Bob knocks on the door... TREAT! Here's a chocolate bar. |
| `!sally` | 26 choices | @Bob, Sally gave you a dress of stitched-together patches today! |
| `!oogieboogie` | 25 choices | Oogie Boogie rolled the dice against @Bob and got snake eyes. Oogie Boogie wins! |
| `!halloweentown` | 30 choices | @Bob, your job in Halloween Town today is: Pumpkin King! |
| `!whatsthis` | 33 choices | @Bob wanders into Christmas Town... What's this? It's snow! |
| `!spook @Sam` | Interaction | @Bob Spooked @Sam with 73% power! |
| `!pumpkinkingofday` | Pumpkin King of the Day | Who won today. Win it by getting 100% on `!jack` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Halloween** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Halloween Numbers** | The number commands (min, max and the reply) |
| **FFY Halloween Lists** | The pick-from-a-list commands |
| **FFY Halloween Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Halloween Of The Day** | The "of the Day" titles |
| **FFY Halloween Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Halloween Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Halloween]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Halloween** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
