# FFY StPatricks

A handful of St Patrick's Day commands. How Irish you are today, pots of gold, jig-offs and a Leprechaun of the Day.

Heads up: it won't work without **FFY Commands**, so install that first.

## Installing

Download **`FFY-StPatricks`** from this page. Over in Streamer.bot, click **Import** at the top, drag it into the box and click **Import**.

Everything's switched on already. Give `!irish` a go in chat.

Don't want all of them? Open the **FFY StPatricks** folder in the **Commands** tab and untick **Enabled** on any you'd rather not have.

## What's in it (10 commands)

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

## Tweaking it

Everything's in the **FFY StPatricks** group in the **Actions** tab. To change something, open the action, double-click **Execute C# Code**, edit the lines between `EDIT BELOW` and `EDIT ABOVE` and hit **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY StPatricks Numbers** | The number commands (min, max and the reply) |
| **FFY StPatricks Lists** | The pick-from-a-list commands |
| **FFY StPatricks Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY StPatricks Duels** | The duels |
| **FFY StPatricks Of The Day** | The "of the Day" titles |
| **FFY StPatricks Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY StPatricks Setup** | Runs once on import |

To add one of your own, use the FFY Commands guide (adding a number or list command) and keep it in **FFY My Number Commands** or **FFY My List Commands** so updates leave it alone.

Everything else from FFY Commands works with these too: special users, user variables, the switches, and `!top` for the interactions.

## Not working?

If nothing replies at all, check **FFY Commands** is installed and look in the **Logs** tab for `[FFY StPatricks]`. If it's just one command that's quiet, make sure it's switched on in the **FFY StPatricks** folder in the **Commands** tab.

For anything else, there's a troubleshooting section in the FFY Commands guide.
