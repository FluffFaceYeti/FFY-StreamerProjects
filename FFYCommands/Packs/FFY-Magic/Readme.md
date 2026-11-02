# FFY Magic

Auras, elemental items, wizard items, your patronus and more.

It's a pack for **FFY Commands**, so install that first.

## Installing

Download the **`FFY-Magic`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it, the commands are already switched on. Try `!auravibes` in chat.

If there are a few you don't want, go to the **Commands** tab, open the **FFY Magic** folder and untick **Enabled** on those.

## The commands (6)

| Command | What it is | Example reply |
|---|---|---|
| `!auravibes` | 10 | @Bob, your aura vibe today is Radiant! |
| `!auraitems` | 6 | @Bob, your aura accessory today is Crystal Necklace! |
| `!elementalitems` | 7 | @Bob, your elemental item today is Fire Amulet! |
| `!wizarditems` | 7 | @Bob, your wizard item today is Wand! |
| `!wizardvibes` | 7 | @Bob, your wizard vibe today is Apprentice! |
| `!patronus` | 106 | @Bob, your Patronus takes the form of a Stag! |

## Changing things

Head to the **Actions** tab and open the **FFY Magic** group. Double-click **Execute C# Code** in the action you want, change the bits between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile** when you're done.

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

> Updating the pack replaces these actions, so if you want a change to stick, put it in **FFY My List Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

## Troubleshooting

- **Nothing replies:** is **FFY Commands** installed? Look for `[FFY Magic]` in the **Logs** tab.
- **Only one command is quiet:** check it's switched on in the **Commands** tab, in the **FFY Magic** folder.

If it's something else, have a look at the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
