# FFY Gym

Gym commands. How much everyone's lifting, deadlifting and bench pressing today, how fast they sprint, and so on.

You need **FFY Commands** installed before adding this pack.

## Installing

Grab the **`FFY-Gym`** file from this page, then in Streamer.bot hit **Import** at the top, drop the file in and click **Import**.

The commands switch on by themselves, so you can type `!lift` straight away to check it's working.

You can turn off any you don't like. Find them in the **FFY Gym** folder in the **Commands** tab and untick **Enabled**.

## Commands (8)

| Command | What it is | Example reply |
|---|---|---|
| `!lift` | 0–500 kg | @Bob, You're lifting 250kg today! |
| `!run` | 0–42 km | @Bob, You've got 21km in your legs today! |
| `!sprint` | 0–100 m/s | @Bob, Your sprint speed is 50m/s today! |
| `!deadlift` | 0–500 kg | @Bob, Your deadlifting 250kg today! |
| `!curl` | 0–200 kg | @Bob, You're curling 100kg today! |
| `!row` | 0–1000 m | @Bob, You rowed 500m today! |
| `!stretch` | 0–100 % | @Bob, Your flexibility is 50% today! |
| `!benchpress` | 20–200 kg | @Bob, you're bench pressing 110kg today! |

## Making changes

It all lives in the **Actions** tab under the **FFY Gym** group. Open an action, double-click **Execute C# Code**, change whatever's between `EDIT BELOW` and `EDIT ABOVE`, then click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Gym** | Settings and replies for its commands |
| **FFY Gym Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Gym Setup** | Runs once on import |

> Updating the pack replaces these actions, so if you want a change to stick, put it in **FFY My Number Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

## If something's not working

No replies at all usually means **FFY Commands** isn't installed. The **Logs** tab will show `[FFY Gym]` lines if the pack is running. If just one command isn't replying, check it's ticked in the **FFY Gym** folder in the **Commands** tab.

If it's something else, have a look at the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
