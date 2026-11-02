# FFY Sea of Thieves

Sea of Thieves reputations and skills, and a `!sotfest` countdown.

You need **FFY Commands** installed before adding this pack.

## Installing

Grab the **`FFY-Sea-of-Thieves`** file from this page, then in Streamer.bot hit **Import** at the top, drop the file in and click **Import**.

The commands switch on by themselves, so you can type `!chainshot` straight away to check it's working.

You can turn off any you don't like. Find them in the **FFY Sea of Thieves** folder in the **Commands** tab and untick **Enabled**.

## Commands (12)

| Command | What it is | Example reply |
|---|---|---|
| `!chainshot` | 0–100 % | @Bob, Your chainshot accuracy is 50% today! |
| `!sniper` | 0–100 % | @Bob, Your Eye of Reach accuracy is 50% today! |
| `!swordlord` | 0–100 % | @Bob, You're 50% sword lord today! |
| `!lunge` | 0–100 % | @Bob, Your sword lunge skills are 50% today! |
| `!tuck` | 0–100 % | @Bob, Your tucking skills are 50% today! |
| `!gh` | 1–75 Lvls | @Bob, Your Gold Hoarders reputation is level 38 today! |
| `!oos` | 1–75 Lvls | @Bob, Your Order of Souls reputation is level 38 today! |
| `!ma` | 1–75 Lvls | @Bob, Your Merchant Alliance reputation is level 38 today! |
| `!athena` | 1–75 Lvls | @Bob, Your Athena's Fortune reputation is level 38 today! |
| `!reaper` | 1–75 Lvls | @Bob, Your Reaper's Bones reputation is level 38 today! |
| `!hunter` | 1–75 Pts | @Bob, Your Hunter's Call reputation is 38 points today! |
| `!sotfest` | Countdown to SoT Fest (10 July) | |

## Making changes

It all lives in the **Actions** tab under the **FFY Sea of Thieves** group. Open an action, double-click **Execute C# Code**, change whatever's between `EDIT BELOW` and `EDIT ABOVE`, then click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Sea of Thieves** | Settings and replies for its commands |
| **FFY Sea of Thieves Countdowns** | The countdowns |
| **FFY Sea of Thieves Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Sea of Thieves Setup** | Runs once on import |

> Updating the pack replaces these actions, so if you want a change to stick, put it in **FFY My Number Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

## If something's not working

No replies at all usually means **FFY Commands** isn't installed. The **Logs** tab will show `[FFY Sea of Thieves]` lines if the pack is running. If just one command isn't replying, check it's ticked in the **FFY Sea of Thieves** folder in the **Commands** tab.

If it's something else, have a look at the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
