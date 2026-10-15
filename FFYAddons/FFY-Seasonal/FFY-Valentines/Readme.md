# FFY Valentines

Lovestruck, cheesy Valentine's Day commands: pickup lines, dream dates, Cupid's arrow duels and Valentine of the Day. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Valentines`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!lovestruck` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Valentines** folder and untick **Enabled** on the ones you don't want.

---

## The commands (14)

| Command | What it is | Example reply |
|---|---|---|
| `!lovestruck` | 0–100 % | @Bob, you're 50% lovestruck today! Somebody fetch a bucket. |
| `!romantic` | 0–100 % | @Bob, you're 50% romantic today! Candles at the ready. |
| `!cheesy` | 0–100 % | @Bob, your chat-up lines are 50% cheesy today. Brie-lliant. |
| `!single` | 0–100 % | @Bob, you're 50% ready to mingle today! |
| `!cupid` | 0–100 % | @Bob, Cupid's aim on you is 50% accurate today! |
| `!heartbreak` | 0–100 % | @Bob, your heart is 50% broken today. Have a chocolate. |
| `!valentine` | 12 choices | @Bob, your Valentine today is a very confused pigeon! |
| `!pickupline` | 8 choices | @Bob's pickup line of the day: "Are you a parking ticket? Because you've got fine written all over you." |
| `!date` | 8 choices | @Bob, your dream date today is a candlelit dinner at a kebab shop! |
| `!chocolates` | 8 choices | @Bob opened the box of chocolates and got the strawberry cream nobody wants! |
| `!serenade @Sam` | Interaction | @Bob Serenaded @Sam with 73% power! |
| `!rose @Sam` | Interaction | @Bob Gave a red rose to @Sam with 73% power! |
| `!cupidarrow @Sam` | Duel | @Bob's arrow struck true (87 vs 38)! @Sam is now hopelessly in love with a lamppost. |
| `!valentineofday` | Valentine of the Day | Who won today. Win it by getting 100% on `!lovestruck` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Valentines** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Valentines Numbers** | The number commands (min, max and the reply) |
| **FFY Valentines Lists** | The pick-from-a-list commands |
| **FFY Valentines Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Valentines Duels** | The duels |
| **FFY Valentines Of The Day** | The "of the Day" titles |
| **FFY Valentines Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Valentines Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Valentines]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Valentines** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
