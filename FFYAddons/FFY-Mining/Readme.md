# FFY Mining

Your chat goes **mining for ores and gems**. Sell what you find for coins, then **upgrade your pickaxe** to find more, and rarer, gems. Very rarely, someone strikes a legendary **1-1** gem.

```
Bob: !mine
Chat: @Bob swung their Iron Pickaxe (1/1) and found: Diamond, Silver, 2 Iron, Coal. Worth $702.15! Type "!sellores" to sell or "!mineinv" to see your haul.
Chat: BIG FIND!!! @Bob just struck Diamond worth $668.80! WHAT A SWING!
Bob: !sellores
Chat: @Bob sold their ores for $702.15! Wallet: $1,014.30. Type "!upgrade" to get a better pickaxe.
Bob: !upgrade
Chat: @Bob upgraded to the Gold Pickaxe! More finds and rarer gems await. Wallet: $14.30.
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- 12 ores and gems, 6 pickaxes, and 8 legendary 1-1 gems.
- You choose how many mines a day, and how often everything **resets**.

---

## Installing

1. Download the **`FFY-Mining`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!mine` in chat to test.

---

## The commands

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

---

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

Diamond and Mythril get their own **BIG FIND!!!** message.

### Pickaxes

Better pickaxes find **more ores per mine** and make **rare gems more likely**:

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

- About **1 in 2,000** finds. They're worth $5,000 to $25,000.
- Once someone strikes one, nobody else can get it that season.
- Chat gets its own *"WOW!!! @Bob unearthed Star Sapphire, a 1-1 gem worth $18,824.42!"* message.
- `!sellores` never sells them. They're yours for the season.

---

## Settings

**Actions tab** → **FFY Mining** group → **FFY Mining** → double-click **Execute C# Code**. Everything is between `EDIT BELOW` and `EDIT ABOVE`:

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

Click **Save and Compile** after changing anything.

---

## Good to know

- **Everything is saved** in the **Global Variables** tab as `ffy.mining`. Deleting it starts a new season straight away.
- **A "day"** follows your PC's clock and resets at midnight.
- **Long messages are split** so chat doesn't cut them off.
- **Stop spam:** give `!mineinv`, `!pickaxe` and `!minetop` a cooldown in the **Commands** tab.

---

## Troubleshooting

- **No reply:** check the commands are switched on in the **Commands** tab, in the **FFY Mining** folder.
- **"Save and Compile" error:** look for a missing `"`, `,` or `;` on the line it mentions.
