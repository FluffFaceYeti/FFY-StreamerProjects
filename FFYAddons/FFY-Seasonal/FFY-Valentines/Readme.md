# FFY Valentines

Soppy, cheesy Valentine's commands for chat. Pickup lines, dream dates, Cupid's arrow duels and a Valentine of the Day.

Heads up: it won't work without **FFY Commands**, so install that first.

## Installing

Download **`FFY-Valentines`** from this page. Over in Streamer.bot, click **Import** at the top, drag it into the box and click **Import**.

Everything's switched on already. Give `!lovestruck` a go in chat.

Don't want all of them? Open the **FFY Valentines** folder in the **Commands** tab and untick **Enabled** on any you'd rather not have.

## What's in it (14 commands)

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

## Tweaking it

Everything's in the **FFY Valentines** group in the **Actions** tab. To change something, open the action, double-click **Execute C# Code**, edit the lines between `EDIT BELOW` and `EDIT ABOVE` and hit **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Valentines Numbers** | The number commands (min, max and the reply) |
| **FFY Valentines Lists** | The pick-from-a-list commands |
| **FFY Valentines Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Valentines Duels** | The duels |
| **FFY Valentines Of The Day** | The "of the Day" titles |
| **FFY Valentines Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Valentines Setup** | Runs once on import |

To add one of your own, use the FFY Commands guide (adding a number or list command) and keep it in **FFY My Number Commands** or **FFY My List Commands** so updates leave it alone.

Everything else from FFY Commands works with these too: special users, user variables, the switches, and `!top` for the interactions.

## Not working?

If nothing replies at all, check **FFY Commands** is installed and look in the **Logs** tab for `[FFY Valentines]`. If it's just one command that's quiet, make sure it's switched on in the **FFY Valentines** folder in the **Commands** tab.

For anything else, there's a troubleshooting section in the FFY Commands guide.
