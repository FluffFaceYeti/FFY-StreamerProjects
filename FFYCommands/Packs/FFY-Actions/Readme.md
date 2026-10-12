# FFY Actions

Punch, kickflip, uppercut, dodge and more. A pack for **FFY Commands**.

> **You need FFY Commands installed first.** Install FFY Commands, then this pack.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Actions`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!squeeze` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Actions** folder and untick **Enabled** on the ones you don't want.

---

## The commands (17)

| Command | What it is | Example reply |
|---|---|---|
| `!squeeze` | 0–100 % | @Bob, Your squeeze strength is 50% today! |
| `!push` | 0–100 kg | @Bob, Your push power is 50kg today! |
| `!jump` | 0–100 cm | @Bob, Your jump height is 50cm today! |
| `!press` | 0–100 kg | @Bob, Your press strength is 50kg today! |
| `!kick` | 0–100 % | @Bob, Your kick power is 50% today! |
| `!dodge` | 0–100 % | @Bob, Your dodge agility is 50% today! |
| `!roll` | 0–100 m | @Bob, You can roll 50m today! |
| `!slide` | 0–100 m/s | @Bob, Your slide speed is 50m/s today! |
| `!climb` | 0–100 m/s | @Bob, Your climbing speed is 50m/s today! |
| `!punch` | 0–100 kg | @Bob, Your punch power is 50kg today! |
| `!block` | 0–100 % | @Bob, Your blocking strength is 50% today! |
| `!tackle` | 0–100 kg | @Bob, Your tackle force is 50kg today! |
| `!throw` | 0–100 % | @Bob, Your throwing accuracy is 50% today! |
| `!kickflip` | 0–100 % | @Bob, Your kickflip ability is 50% today! |
| `!spin` | 0–100 rpm | @Bob, You're spinning at 50rpm today! |
| `!uppercut` | 0–100 kg | @Bob, Your uppercut power is 50kg today! |
| `!grapple` | 0–100 % | @Bob, Your grapple strength is 50% today! |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Actions** group. Open an action, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Actions** | Settings and replies for its commands |
| **FFY Actions Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Actions Setup** | Runs once on import |

> **Updating this pack replaces these actions.** To keep a change safe, put it in **FFY My Number Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Actions]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Actions** folder)?
- **Anything else:** see the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
