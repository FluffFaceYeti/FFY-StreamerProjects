# FFY Easter

Easter commands for chat. Egg hunts, bunny names, an egg and spoon race and an Easter Bunny of the Day.

Heads up: it won't work without **FFY Commands**, so install that first.

## Installing

Download **`FFY-Easter`** from this page. Over in Streamer.bot, click **Import** at the top, drag it into the box and click **Import**.

Everything's switched on already. Give `!egghunt` a go in chat.

Don't want all of them? Open the **FFY Easter** folder in the **Commands** tab and untick **Enabled** on any you'd rather not have.

## What's in it (11 commands)

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

## Tweaking it

Everything's in the **FFY Easter** group in the **Actions** tab. To change something, open the action, double-click **Execute C# Code**, edit the lines between `EDIT BELOW` and `EDIT ABOVE` and hit **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Easter Numbers** | The number commands (min, max and the reply) |
| **FFY Easter Lists** | The pick-from-a-list commands |
| **FFY Easter Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Easter Duels** | The duels |
| **FFY Easter Of The Day** | The "of the Day" titles |
| **FFY Easter Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Easter Setup** | Runs once on import |

To add one of your own, use the FFY Commands guide (adding a number or list command) and keep it in **FFY My Number Commands** or **FFY My List Commands** so updates leave it alone.

Everything else from FFY Commands works with these too: special users, user variables, the switches, and `!top` for the interactions.

## Not working?

If nothing replies at all, check **FFY Commands** is installed and look in the **Logs** tab for `[FFY Easter]`. If it's just one command that's quiet, make sure it's switched on in the **FFY Easter** folder in the **Commands** tab.

For anything else, there's a troubleshooting section in the FFY Commands guide.
