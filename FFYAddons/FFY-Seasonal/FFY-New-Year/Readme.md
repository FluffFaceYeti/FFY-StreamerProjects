# FFY New Year

New Year commands. Resolutions, predictions for the year, party hats, countdown clashes and a Party Animal of the Day.

This plugs into **FFY Commands**, so get that installed first.

## Installing

Grab the **`FFY-New-Year`** file from this page, then in Streamer.bot hit **Import** at the top, drop the file in and click **Import**.

The commands switch on by themselves, so you can type `!resolution` straight away to check it's working.

You can turn off any you don't like. Find them in the **FFY New Year** folder in the **Commands** tab and untick **Enabled**.

## Commands (11)

| Command | What it is | Example reply |
|---|---|---|
| `!resolution` | 0–100 % | @Bob, there's a 50% chance you keep your New Year's resolution! |
| `!partyanimal` | 0–100 % | @Bob, you're 50% party animal tonight! |
| `!hangover` | 0–100 % | @Bob, your New Year's hangover is at 50%. Drink water! |
| `!newyou` | 0–100 % | @Bob, you're 50% new you this year! |
| `!newyearresolution` | 8 choices | @Bob's New Year's resolution: go to the gym (twice)! |
| `!prediction` | 8 choices | @Bob's prediction for the new year: you'll win something big! |
| `!partyhat` | 7 choices | @Bob is wearing a glittery top hat to the New Year party! |
| `!cheers @Sam` | Interaction | @Bob Raised a glass with @Sam with 73% power! |
| `!auldlangsyne @Sam` | Interaction | @Bob Sang Auld Lang Syne with @Sam with 73% power! |
| `!countdownclash @Sam` | Duel | @Bob shouted HAPPY NEW YEAR first (87 vs 38)! @Sam was still on "three". |
| `!partyanimalofday` | Party Animal of the Day | Who won today. Win it by getting 100% on `!partyanimal` |

## Making changes

It all lives in the **Actions** tab under the **FFY New Year** group. Open an action, double-click **Execute C# Code**, change whatever's between `EDIT BELOW` and `EDIT ABOVE`, then click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY New Year Numbers** | The number commands (min, max and the reply) |
| **FFY New Year Lists** | The pick-from-a-list commands |
| **FFY New Year Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY New Year Duels** | The duels |
| **FFY New Year Of The Day** | The "of the Day" titles |
| **FFY New Year Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY New Year Setup** | Runs once on import |

If you want to add your own, follow the bit in the FFY Commands guide about adding a number or list command, and put it in **FFY My Number Commands** or **FFY My List Commands**. That way an update won't wipe it.

Special users, user variables, the switches and `!top` for the interactions from FFY Commands all work with these too.

## If something's not working

No replies at all usually means **FFY Commands** isn't installed. The **Logs** tab will show `[FFY New Year]` lines if the pack is running. If just one command isn't replying, check it's ticked in the **FFY New Year** folder in the **Commands** tab.

For anything else, there's a troubleshooting section in the FFY Commands guide.
