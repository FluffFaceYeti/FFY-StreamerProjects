# FFY Pirate

For the pirates in chat. Pirate skills, outfits, sails and kegs, with a Pirate and a Captain of the Day.

It's a pack for **FFY Commands**, so install that first.

## Installing

Download the **`FFY-Pirate`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it, the commands are already switched on. Try `!pirate` in chat.

If there are a few you don't want, go to the **Commands** tab, open the **FFY Pirate** folder and untick **Enabled** on those.

## The commands (18)

| Command | What it is | Example reply |
|---|---|---|
| `!pirate` | 0–100 % | @Bob, You're 50% pirate today! |
| `!captain` | 0–100 % | @Bob, Your captain energy is 50% today! |
| `!treasure_hunting` | 0–100 % | @Bob, Your treasure hunting instincts are 50% today! |
| `!sea_navigation` | 0–100 % | @Bob, Your navigation skills are 50% today! |
| `!ship_maintenance` | 0–100 % | @Bob, Your ship maintenance skills are 50% today! |
| `!swordsmanship` | 0–100 % | @Bob, Your swordsmanship is 50% today! |
| `!swashbuckling` | 0–100 % | @Bob, You're 50% swashbuckler today! |
| `!plunder` | 0–100 % | @Bob, Your plundering efficiency is 50% today! |
| `!cannon_use` | 0–100 % | @Bob, Your cannon skills are 50% today! |
| `!crew_morale` | 0–100 % | @Bob, Your crew morale is 50% today! |
| `!intimidation` | 0–100 % | @Bob, Your intimidation factor is 50% today! |
| `!parley` | 0–100 % | @Bob, Your parley skills are 50% today! |
| `!piratevibes` | 7 | @Bob, your pirate vibe today is Swashbuckler! |
| `!pirateoutfits` | 7 | @Bob, your pirate accessory today is Tricorn Hat! |
| `!sails` | 131 | @Bob, today your ship is repping the Affiliate Alliance Sails! |
| `!keg` | 4 | @Bob, you light a Gunpowder Barrel and board the enemy ship! |
| `!pirateofday` | Pirate of the Day | Who won today. Win it with 100% on `!pirate` |
| `!captainofday` | Captain of the Day | Who won today. Win it with 100% on `!captain` |

## Changing things

Head to the **Actions** tab and open the **FFY Pirate** group. Double-click **Execute C# Code** in the action you want, change the bits between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile** when you're done.

| Action | What's in it |
|---|---|
| **FFY Piracy** | Settings and replies for its commands |
| **FFY Pirate** | Settings and replies for its commands |
| **FFY Pirate Outfits** | Settings and replies for its commands |
| **FFY Sails** | Settings and replies for its commands |
| **FFY Keg** | Settings and replies for its commands |
| **FFY Pirate Of The Day** | The "of the Day" titles |
| **FFY Pirate Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Pirate Setup** | Runs once on import |

> Updating the pack replaces these actions, so if you want a change to stick, put it in **FFY My Number Commands** or **FFY My List Commands** (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

## Troubleshooting

- **Nothing replies:** is **FFY Commands** installed? Look for `[FFY Pirate]` in the **Logs** tab.
- **Only one command is quiet:** check it's switched on in the **Commands** tab, in the **FFY Pirate** folder.

If it's something else, have a look at the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
