# FFY Magic

Auras, elemental items, wizard items, patronus and more. A pack for **FFY Commands**.

> **You need FFY Commands installed first.** Install FFY Commands, then this pack.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Magic`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!auravibes` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Magic** folder and untick **Enabled** on the ones you don't want.

---

## The commands (6)

| Command | What it is | Example reply |
|---|---|---|
| `!auravibes` | 10 | @Bob, your aura vibe today is Radiant! |
| `!auraitems` | 6 | @Bob, your aura accessory today is Crystal Necklace! |
| `!elementalitems` | 7 | @Bob, your elemental item today is Fire Amulet! |
| `!wizarditems` | 7 | @Bob, your wizard item today is Wand! |
| `!wizardvibes` | 7 | @Bob, your wizard vibe today is Apprentice! |
| `!patronus` | 106 | @Bob, your Patronus takes the form of a Stag! |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Magic** group. Open an action, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Aura** | Settings and replies for its commands |
| **FFY Aura Items** | Settings and replies for its commands |
| **FFY Elemental Items** | Settings and replies for its commands |
| **FFY Wizard Items** | Settings and replies for its commands |
| **FFY Wizard Vibes** | Settings and replies for its commands |
| **FFY Patronus** | Settings and replies for its commands |
| **FFY Magic Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Magic Setup** | Runs once on import |

> **Updating this pack replaces these actions.** To keep a change safe, put it in **FFY My List Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Magic]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Magic** folder)?
- **Anything else:** see the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
