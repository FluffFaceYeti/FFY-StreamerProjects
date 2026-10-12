# FFY Gym

Lift, deadlift, bench press, sprint and more. A pack for **FFY Commands**.

> **You need FFY Commands installed first.** Install FFY Commands, then this pack.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Gym`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!lift` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Gym** folder and untick **Enabled** on the ones you don't want.

---

## The commands (8)

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

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Gym** group. Open an action, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Gym** | Settings and replies for its commands |
| **FFY Gym Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Gym Setup** | Runs once on import |

> **Updating this pack replaces these actions.** To keep a change safe, put it in **FFY My Number Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Gym]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Gym** folder)?
- **Anything else:** see the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
