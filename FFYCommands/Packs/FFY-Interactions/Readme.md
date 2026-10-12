# FFY Interactions

Hug, slap, boop and more with `!hug @someone`. Includes consent (`!accept` / `!deny`) and `!top`. A pack for **FFY Commands**.

> **You need FFY Commands installed first.** Install FFY Commands, then this pack.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Interactions`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!bonk` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Interactions** folder and untick **Enabled** on the ones you don't want.

---

## The commands (14)

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

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Interactions** group. Open an action, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Interactions** | Settings and replies for its commands |
| **FFY Action Words** | Settings and replies for its commands |
| **FFY Top Titles** | Settings and replies for its commands |
| **FFY Interactions Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Interactions Setup** | Runs once on import |

> **Updating this pack replaces these actions.** To keep a change safe, put it in the FFY My actions (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Interactions]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Interactions** folder)?
- **Anything else:** see the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
