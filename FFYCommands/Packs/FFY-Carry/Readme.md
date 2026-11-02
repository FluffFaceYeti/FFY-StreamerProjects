# FFY Carry

Just three: how much weight, how many items and how much gold you can carry.

You need **FFY Commands** installed before adding this pack.

## Installing

Grab the **`FFY-Carry`** file from this page, then in Streamer.bot hit **Import** at the top, drop the file in and click **Import**.

The commands switch on by themselves, so you can type `!weight` straight away to check it's working.

You can turn off any you don't like. Find them in the **FFY Carry** folder in the **Commands** tab and untick **Enabled**.

## Commands (3)

| Command | What it is | Example reply |
|---|---|---|
| `!weight` | 0–200 kg | @Bob, Your carry weight is 100kg today! |
| `!items` | 0–100 items | @Bob, You're carrying 50 items today! |
| `!gold` | 0–100 coins | @Bob, You're carrying 50 coins today! |

## Making changes

It all lives in the **Actions** tab under the **FFY Carry** group. Open an action, double-click **Execute C# Code**, change whatever's between `EDIT BELOW` and `EDIT ABOVE`, then click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Carry** | Settings and replies for its commands |
| **FFY Hold** | Settings and replies for its commands |
| **FFY Carry Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Carry Setup** | Runs once on import |

> Updating the pack replaces these actions, so if you want a change to stick, put it in **FFY My Number Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

## If something's not working

No replies at all usually means **FFY Commands** isn't installed. The **Logs** tab will show `[FFY Carry]` lines if the pack is running. If just one command isn't replying, check it's ticked in the **FFY Carry** folder in the **Commands** tab.

If it's something else, have a look at the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
