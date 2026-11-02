# FFY ThanksGiving

Daft Thanksgiving commands, with lots of turkey.

This plugs into **FFY Commands**, so get that installed first.

## Installing

Grab the **`FFY-ThanksGiving`** file from this page, then in Streamer.bot hit **Import** at the top, drop the file in and click **Import**.

The commands switch on by themselves, so you can type `!turkey` straight away to check it's working.

You can turn off any you don't like. Find them in the **FFY ThanksGiving** folder in the **Commands** tab and untick **Enabled**.

## Commands (12)

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

## Making changes

It all lives in the **Actions** tab under the **FFY ThanksGiving** group. Open an action, double-click **Execute C# Code**, change whatever's between `EDIT BELOW` and `EDIT ABOVE`, then click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY ThanksGiving Numbers** | The number commands (min, max and the reply) |
| **FFY ThanksGiving Lists** | The pick-from-a-list commands |
| **FFY ThanksGiving Duels** | The duels |
| **FFY ThanksGiving Of The Day** | The "of the Day" titles |
| **FFY ThanksGiving Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY ThanksGiving Setup** | Runs once on import |

If you want to add your own, follow the bit in the FFY Commands guide about adding a number or list command, and put it in **FFY My Number Commands** or **FFY My List Commands**. That way an update won't wipe it.

Special users, user variables, the switches and `!top` for the interactions from FFY Commands all work with these too.

## If something's not working

No replies at all usually means **FFY Commands** isn't installed. The **Logs** tab will show `[FFY ThanksGiving]` lines if the pack is running. If just one command isn't replying, check it's ticked in the **FFY ThanksGiving** folder in the **Commands** tab.

For anything else, there's a troubleshooting section in the FFY Commands guide.
