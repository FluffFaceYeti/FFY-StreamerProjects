# FFY Mining

Chat goes mining for ores and gems. They sell what they dig up for coins and save up for a better pickaxe, which finds more stuff and rarer gems. Once in a blue moon somebody hits a legendary 1-1 gem.

```
Bob: !mine
Chat: @Bob swung their Iron Pickaxe (1/1) and found: Diamond, Silver, 2 Iron, Coal. Worth $702.15! Type "!sellores" to sell or "!mineinv" to see your haul.
Chat: BIG FIND!!! @Bob just struck Diamond worth $668.80! WHAT A SWING!
Bob: !sellores
Chat: @Bob sold their ores for $702.15! Wallet: $1,014.30. Type "!upgrade" to get a better pickaxe.
Bob: !upgrade
Chat: @Bob upgraded to the Gold Pickaxe! More finds and rarer gems await. Wallet: $14.30.
```

There are 12 ores and gems, 6 pickaxes and 8 legendary 1-1 gems. You pick how many times a day people can mine and how often everything resets.

You don't need FFY Commands for it, and it works on Twitch, Kick and YouTube.

## Installing

Download the **`FFY-Mining`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

The commands are already switched on. Type `!mine` in chat to give it a go.

## Commands

| Command | What it does |
|---|---|
| `!mine` | Goes mining. The message says which mine of the day it is, e.g. **1/1**. |
| `!mineinv` | Shows your ores waiting to be sold, your 1-1 gems, your pickaxe, and what it's all worth. `!mineinv @Sam` shows someone else's. |
| `!sellores` | Sells all your ores for coins. Your 1-1 gems are kept. |
| `!pickaxe` | Shows your pickaxe, the next one, and how much it costs. |
| `!upgrade` | Buys the next pickaxe, if you have enough coins. |
| `!bestgems` | The most valuable gems in the whole channel, and who owns them. |
| `!minewallet` | Shows how many coins you have. `!minewallet @Sam` shows someone else's. |
| `!minetop` | The top 5 miners, by coins plus haul. |
| `!mineseason` | Shows how many days are left until the season resets. |

## Ores and gems

| Ore | How common | Value |
|---|---|---|
| Stone | Very common | $0.05 – $0.20 |
| Coal | Very common | $0.50 – $2 |
| Copper | Common | $1 – $4 |
| Iron | Common | $2 – $8 |
| Silver | Uncommon | $5 – $15 |
| Gold | Uncommon | $10 – $30 |
| Amethyst | Rare | $20 – $60 |
| Emerald | Rare | $40 – $120 |
| Ruby | Rare | $60 – $180 |
| Sapphire | Rare | $70 – $200 |
| Diamond | Very rare (**BIG FIND**) | $200 – $800 |
| Mythril | Super rare (**BIG FIND**) | $800 – $3,000 |

Diamond and Mythril each get a **BIG FIND!!!** shout in chat.

### Pickaxes

A better pickaxe finds more ores each time you mine, and makes rare gems more likely:

| Pickaxe | Price | Finds per mine | Rare gem chance |
|---|---|---|---|
| Wooden Pickaxe | Free (everyone starts here) | 4 | Normal |
| Stone Pickaxe | $100 | 4 | ×1.25 |
| Iron Pickaxe | $400 | 5 | ×1.5 |
| Gold Pickaxe | $1,500 | 5 | ×2 |
| Diamond Pickaxe | $5,000 | 6 | ×3 |
| Mythril Pickaxe | $20,000 | 7 | ×4 |

### 1-1 gems

Heart of the Mountain, Star Sapphire, Dragon's Eye Ruby, The Endless Diamond, Moonstone Crown Jewel, Phoenix Fire Opal, Ancient Dwarven Emerald and The Void Pearl.

You'll find one roughly once every 2,000 finds, and they're worth between $5,000 and $25,000. When someone strikes one, nobody else can get it for the rest of the season, and chat gets something like *"WOW!!! @Bob unearthed Star Sapphire, a 1-1 gem worth $18,824.42!"*

`!sellores` won't ever sell them, so they're safe until the season ends.

## Settings

In the **Actions** tab, open the **FFY Mining** group, then the **FFY Mining** action, and double-click **Execute C# Code**. Everything you can change is between `EDIT BELOW` and `EDIT ABOVE`:

| Setting | What it does |
|---|---|
| `ResetDays = 30;` | **The season.** Every pickaxe, haul and wallet is reset after this many days. `0` = never reset. |
| `MinesPerDay = 1;` | How many times each viewer can mine per day. |
| `FindsPerMine = 4;` | How many ores each mine gives with the Wooden Pickaxe. Better pickaxes add more. |
| `Money = "$";` | The money symbol, e.g. `"£"` or `"€"`. |
| `Ore(...)` lines | The ores: `Ore("name", chance, lowest value, highest value)`. Ores with a chance under 5 count as rare, so pickaxes boost them. |
| `Pickaxe(...)` lines | The pickaxes, in order: `Pickaxe("name", price, extra finds, rare boost)`. |
| `LegendaryChance = 0.05;` | The chance of a 1-1 gem per find, out of 100. |
| `Legendary(...)` | The 1-1 gems: `Legendary(lowest value, highest value, names...)`. |
| `BigFind(...)` | Which ores get a **BIG FIND!!!** message. |
| `BestCount = 5;` | How many gems `!bestgems` shows. |
| The `...Message` lines | Every message chat sees. Change the wording, but keep the `{...}` placeholders. |

Click **Save and Compile** when you're done.

## Worth knowing

It's all saved in the **Global Variables** tab as `ffy.mining`. Delete that if you want a fresh season right now.

Days go by your PC's clock and reset at midnight.

Long messages are split up so chat doesn't cut the end off.

`!mineinv`, `!pickaxe` and `!minetop` can get spammy, so you might want to give them a cooldown in the **Commands** tab.

## If something's not working

If there's no reply, make sure the commands are switched on in the **FFY Mining** folder in the **Commands** tab.

A **Save and Compile** error almost always means there's a missing `"`, `,` or `;` on the line it mentions.
