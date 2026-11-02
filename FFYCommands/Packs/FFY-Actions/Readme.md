# FFY Actions

Punch, kickflip, uppercut, dodge and more.

It's a pack for **FFY Commands**, so install that first.

## Installing

Download the **`FFY-Actions`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it, the commands are already switched on. Try `!squeeze` in chat.

If there are a few you don't want, go to the **Commands** tab, open the **FFY Actions** folder and untick **Enabled** on those.

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

## Changing things

Head to the **Actions** tab and open the **FFY Actions** group. Double-click **Execute C# Code** in the action you want, change the bits between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile** when you're done.

| Action | What's in it |
|---|---|
| **FFY Actions** | Settings and replies for its commands |
| **FFY Actions Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Actions Setup** | Runs once on import |

> Updating the pack replaces these actions, so if you want a change to stick, put it in **FFY My Number Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

## Troubleshooting

- **Nothing replies:** is **FFY Commands** installed? Look for `[FFY Actions]` in the **Logs** tab.
- **Only one command is quiet:** check it's switched on in the **Commands** tab, in the **FFY Actions** folder.

If it's something else, have a look at the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
