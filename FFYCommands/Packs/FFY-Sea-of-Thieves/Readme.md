# FFY Sea of Thieves

Sea of Thieves reputations and skills, plus the `!sotfest` countdown. A pack for **FFY Commands**.

> **You need FFY Commands installed first.** Install FFY Commands, then this pack.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Sea-of-Thieves`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!chainshot` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Sea of Thieves** folder and untick **Enabled** on the ones you don't want.

---

## The commands (12)

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

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Sea of Thieves** group. Open an action, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Sea of Thieves** | Settings and replies for its commands |
| **FFY Sea of Thieves Countdowns** | The countdowns |
| **FFY Sea of Thieves Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Sea of Thieves Setup** | Runs once on import |

> **Updating this pack replaces these actions.** To keep a change safe, put it in **FFY My Number Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Sea of Thieves]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Sea of Thieves** folder)?
- **Anything else:** see the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
