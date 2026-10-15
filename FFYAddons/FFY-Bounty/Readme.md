# FFY Bounty

Put a price on someone's head! Mods and viewers post bounties, bounty hunters try to track them down and claim the reward, and the wanted can lie low in a hideout.

```
Bob: !bounty @Sam 50 stole my sandwich
Chat: WANTED: @Sam! @Bob added 50 coins to the bounty for "stole my sandwich". Total bounty: 50 coins.
Ann: !bountyhunt @Sam
Chat: @Sam slipped away from @Ann! The 20 coin hunting fee was added to the bounty, which is now 70 coins. (1/3)
Kim: !bountyhunt @Sam
Chat: BOUNTY CLAIMED! @Kim tracked down @Sam and collected 70 coins! (1/3)
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.

---

## Installing

1. Download the **`FFY-Bounty`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!bountyhelp` in chat to see them.

---

## How it works

- **Coins:** everyone starts with 100 coins and gets 25 more each day they use a bounty command. They earn far more by claiming bounties.
- **Posting a bounty:** `!bounty @someone 50 reason` takes 50 of your coins and adds them to that person's bounty. Several people can add to the same bounty, and it keeps growing. **Mods and you** can post bounties for free, with no limit.
- **Hunting:** `!bountyhunt @someone` tries to catch them. There's a 40% chance to start with.
  - **Catch them:** you claim the whole bounty, and it's gone.
  - **They slip away:** you pay a 20 coin fee, which is added to their bounty. Missed hunts make the bounty bigger!
- **Hideouts:** if you're wanted, `!hideout` lets you lie low for 30 minutes, which makes you much harder to catch. Once a day.

---

## The commands

| Command | What it does |
|---|---|
| `!bounty @Sam 50 reason` | Adds 50 coins to the bounty on Sam. The reason is optional. |
| `!bountyhunt @Sam` | Hunts Sam. Catch them to claim the bounty. 3 hunts a day. |
| `!bounties` | The most wanted list, biggest bounties first. |
| `!wanted @Sam` | Sam's wanted poster: the bounty, why, who posted it, and whether they're lying low. |
| `!hideout` | Lie low for 30 minutes if you're wanted. Once a day. |
| `!bountycoins` | How many coins you have. `!bountycoins @Sam` shows Sam's. |
| `!bountytop` | The top bounty hunters, by coins earned. |
| `!bountyclear @Sam` | **Mods and you only.** Removes the bounty on Sam. |
| `!bountyhelp` | Lists the commands in chat. |

---

## Settings

**Actions tab** → **FFY Bounty** group → **FFY Bounty** → double-click **Execute C# Code**. Everything is between `EDIT BELOW` and `EDIT ABOVE`. Click **Save and Compile** after changing anything.

| Setting | What it does |
|---|---|
| `AllowViewerBounties = true;` | `false` = only mods and you can post bounties. |
| `AllowHideouts = true;` | `false` switches `!hideout` off. |
| `ProtectMods = false;` | `true` = nobody can put a bounty on a mod. |
| `StartingCoins = 100;` | Coins each viewer starts with. |
| `DailyCoins = 25;` | Coins each viewer gets each day they use a bounty command. |
| `MinBounty = 10;` / `MaxBounty = 5000;` | The smallest and biggest bounty a viewer can post. Mods have no limit. |
| `HuntsPerDay = 3;` | How many hunts each viewer gets a day. |
| `CatchChance = 40;` | The chance of catching someone, out of 100. |
| `MissFee = 20;` | What a missed hunt costs. It's added to the bounty. |
| `HideoutProtection = 25;` | How much harder it is to catch someone lying low, e.g. 25 turns a 40% chance into 15%. |
| `HideoutMinutes = 30;` | How long a hideout lasts. |
| `BoardSize = 5;` | How many bounties `!bounties` shows. |
| The `Message("...", "...")` lines | Every message chat sees. Change the wording, but keep the `{...}` words. |

---

## Good to know

- Everything is saved in the **Global Variables** tab as `ffy.bounty`. Deleting it clears every bounty and everyone's coins.
- **`ProtectMods`** knows who the mods are once they've used a bounty command.
- **Stop spam:** give `!bounties`, `!wanted` and `!bountytop` a cooldown in the **Commands** tab.

---

## Troubleshooting

- **No reply:** check the commands are switched on in the **Commands** tab, in the **FFY Bounty** folder.
- **"Save and Compile" error:** look for a missing `"`, `,` or `;` on the line it mentions.
