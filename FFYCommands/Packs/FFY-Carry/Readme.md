# FFY Carry

Carry weight, items and gold. A pack for **FFY Commands**.

> **You need FFY Commands installed first.** Install FFY Commands, then this pack.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Carry`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!weight` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Carry** folder and untick **Enabled** on the ones you don't want.

---

## The commands (3)

| Command | What it is | Example reply |
|---|---|---|
| `!weight` | 0–200 kg | @Bob, Your carry weight is 100kg today! |
| `!items` | 0–100 items | @Bob, You're carrying 50 items today! |
| `!gold` | 0–100 coins | @Bob, You're carrying 50 coins today! |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Carry** group. Open an action, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Carry** | Settings and replies for its commands |
| **FFY Hold** | Settings and replies for its commands |
| **FFY Carry Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Carry Setup** | Runs once on import |

> **Updating this pack replaces these actions.** To keep a change safe, put it in **FFY My Number Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Carry]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Carry** folder)?
- **Anything else:** see the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
