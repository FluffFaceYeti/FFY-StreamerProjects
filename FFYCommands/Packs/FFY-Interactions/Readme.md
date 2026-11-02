# FFY Interactions

Hug, slap, boop and lots more, e.g. `!hug @someone`. It's got consent built in (`!accept` / `!deny`) and a `!top` leaderboard.

This is a pack for **FFY Commands**. Install that first if you haven't already.

## Installing

Download **`FFY-Interactions`** from this page. Over in Streamer.bot, click **Import** at the top, drag it into the box and click **Import**.

Everything's switched on already. Give `!bonk` a go in chat.

Don't want all of them? Open the **FFY Interactions** folder in the **Commands** tab and untick **Enabled** on any you'd rather not have.

## What's in it (14 commands)

| Command | What it is | Example reply |
|---|---|---|
| `!bonk @Sam` | @Bob Bonked @Sam with 73% power! | |
| `!boop @Sam` | @Bob Booped @Sam with 73% power! | |
| `!fliptable @Sam` | @Bob Flipped a table at @Sam with 73% power! | |
| `!highfive @Sam` | @Bob High-fived @Sam with 73% power! | |
| `!hug @Sam` | @Bob Hugged @Sam with 73% power! | |
| `!kiss @Sam` | @Bob Kissed @Sam with 73% power! | |
| `!love @Sam` | @Bob Sent love to @Sam with 73% power! | |
| `!pat @Sam` | @Bob Patted @Sam with 73% power! | |
| `!slap @Sam` | @Bob Slapped @Sam with 73% power! | |
| `!spank @Sam` | @Bob Spanked @Sam with 73% power! | |
| `!throwshoe @Sam` | @Bob Threw a shoe at @Sam with 73% power! | |
| `!accept` / `!deny` | Answer a consent request (when consent is switched on) | |
| `!top tickle` | Today's top ticklers and most tickled | |

## Tweaking it

Everything's in the **FFY Interactions** group in the **Actions** tab. To change something, open the action, double-click **Execute C# Code**, edit the lines between `EDIT BELOW` and `EDIT ABOVE` and hit **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Interactions** | Settings and replies for its commands |
| **FFY Action Words** | Settings and replies for its commands |
| **FFY Top Titles** | Settings and replies for its commands |
| **FFY Interactions Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Interactions Setup** | Runs once on import |

> Updating the pack replaces these actions, so if you want a change to stick, put it in the FFY My actions (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

## Not working?

If nothing replies at all, check **FFY Commands** is installed and look in the **Logs** tab for `[FFY Interactions]`. If it's just one command that's quiet, make sure it's switched on in the **FFY Interactions** folder in the **Commands** tab.

If it's something else, have a look at the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
