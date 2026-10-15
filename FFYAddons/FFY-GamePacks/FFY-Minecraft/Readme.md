# FFY Minecraft

Minecraft commands for your stream: diamonds, biomes, mobs, crafting, Creeper chances, PvP and Diamond Miner of the Day. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Minecraft`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!diamonds` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Minecraft** folder and untick **Enabled** on the ones you don't want.

---

## The commands (13)

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

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Minecraft** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Minecraft Numbers** | The number commands (min, max and the reply) |
| **FFY Minecraft Lists** | The pick-from-a-list commands |
| **FFY Minecraft Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Minecraft Duels** | The duels |
| **FFY Minecraft Of The Day** | The "of the Day" titles |
| **FFY Minecraft Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Minecraft Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Minecraft]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Minecraft** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
