# FFY Minecraft

Minecraft commands for chat. Diamonds, biomes, mobs, crafting, how likely a Creeper is to get you, PvP and a Diamond Miner of the Day.

Heads up: it won't work without **FFY Commands**, so install that first.

## Installing

Download **`FFY-Minecraft`** from this page. Over in Streamer.bot, click **Import** at the top, drag it into the box and click **Import**.

Everything's switched on already. Give `!diamonds` a go in chat.

Don't want all of them? Open the **FFY Minecraft** folder in the **Commands** tab and untick **Enabled** on any you'd rather not have.

## What's in it (13 commands)

| Command | What it is | Example reply |
|---|---|---|
| `!diamonds` | 0–64 diamonds | @Bob, you mined 32 diamonds today! |
| `!mcbuilder` | 0–100 % | @Bob, your Minecraft building is at 50% today! |
| `!redstone` | 0–100 % | @Bob, your redstone skills are at 50% today! |
| `!swordskill` | 0–100 % | @Bob, your sword skills are at 50% today! |
| `!creeperluck` | 0–100 % | @Bob, there's a 50% chance a creeper sneaks up on you today. Aw man. |
| `!biome` | 10 choices | @Bob, you spawned in a Plains today! |
| `!mob` | 10 choices | @Bob, you'd be a Creeper in Minecraft today! |
| `!craft` | 10 choices | @Bob crafted a diamond pickaxe today! |
| `!mcdeath` | 10 choices | @Bob fell from a high place. Respawn? |
| `!tnt @Sam` | Interaction | @Bob Blew up the house of @Sam with 73% power! |
| `!emerald @Sam` | Interaction | @Bob Traded an emerald with @Sam with 73% power! |
| `!pvp @Sam` | Duel | @Bob won the PvP (87 vs 38)! @Sam drops all their items. |
| `!diamondminerofday` | Diamond Miner of the Day | Who won today. Win it by getting 64% on `!diamonds` |

## Tweaking it

Everything's in the **FFY Minecraft** group in the **Actions** tab. To change something, open the action, double-click **Execute C# Code**, edit the lines between `EDIT BELOW` and `EDIT ABOVE` and hit **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Minecraft Numbers** | The number commands (min, max and the reply) |
| **FFY Minecraft Lists** | The pick-from-a-list commands |
| **FFY Minecraft Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Minecraft Duels** | The duels |
| **FFY Minecraft Of The Day** | The "of the Day" titles |
| **FFY Minecraft Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Minecraft Setup** | Runs once on import |

To add one of your own, use the FFY Commands guide (adding a number or list command) and keep it in **FFY My Number Commands** or **FFY My List Commands** so updates leave it alone.

Everything else from FFY Commands works with these too: special users, user variables, the switches, and `!top` for the interactions.

## Not working?

If nothing replies at all, check **FFY Commands** is installed and look in the **Logs** tab for `[FFY Minecraft]`. If it's just one command that's quiet, make sure it's switched on in the **FFY Minecraft** folder in the **Commands** tab.

For anything else, there's a troubleshooting section in the FFY Commands guide.
