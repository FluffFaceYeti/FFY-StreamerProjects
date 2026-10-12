# FFY Dino

Your chat goes **digging for dinosaur fossils**. Every dig turns up bones, junk, amber, or very rarely a legendary **1-1** fossil. Find every bone of a dinosaur to **complete its skeleton** and put it on display in your **museum**.

```
Bob: !dig
Chat: @Bob went digging (1/1) and found: T-Rex Skull (new!), Velociraptor Claws (spare), a plastic toy dinosaur, Triceratops Horns (new!), Amber with a Mosquito. Closest skeleton: T-Rex 5/6. Type "!bones" to see your progress.
Chat: Shiny! @Bob found Amber with a Mosquito worth $212.40!
...
Chat: SKELETON COMPLETE!!! @Bob JUST FINISHED A T-REX SKELETON!!! The museum crowd goes wild! Worth $1,000.00!
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- 11 dinosaurs to complete, from the Velociraptor to the Giganotosaurus.
- You choose how many digs a day, and how often everything **resets**.

---

## Installing

1. Download the **`FFY-Dino`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!dig` in chat to test.

---

## The commands

| Command | What it does |
|---|---|
| `!dig` | Goes digging. Each dig finds 5 things. The message says which dig of the day it is, e.g. **1/1**. |
| `!bones` | Shows the skeletons you're closest to finishing, which bones are missing, and how many spare bones you have. |
| `!sellbones` | Sells your spare (duplicate) bones for coins. |
| `!museum` | Shows your completed skeletons, your best treasures, and what it's all worth. `!museum @Sam` shows someone else's. |
| `!bestfossils` | The most valuable treasures in the whole channel, and who owns them. |
| `!dinowallet` | Shows how much money you have from selling bones. `!dinowallet @Sam` shows someone else's. |
| `!dinotop` | The top 5 museums, by value. |
| `!dinoseason` | Shows how many days are left until the season resets. |

---

## How digging works

Each find is one of these:

| Find | Chance | What happens |
|---|---|---|
| A bone | 85% | A bone from a random dinosaur. **New** bones count towards its skeleton, and repeats become **spares** you can sell. |
| Junk | 10% | An old boot, a rusty spoon, a plastic toy dinosaur... worth nothing, but funny. |
| Amber | 4.95% | A treasure for your museum, worth $50 to $400. |
| 1-1 fossil | 0.05% | A legendary treasure worth $5,000 to $25,000. **Only one person can own each one.** |

To stop the last bone taking forever, half of all bones are ones you still need (you can change this).

### The dinosaurs

| Dinosaur | Bones | Skeleton value | How common |
|---|---|---|---|
| Velociraptor | 5 | $50 | Very common |
| Triceratops | 6 | $80 | Very common |
| Parasaurolophus | 5 | $110 | Common |
| Stegosaurus | 5 | $120 | Common |
| Ankylosaurus | 5 | $150 | Common |
| Pteranodon | 5 | $180 | Common |
| Brachiosaurus | 7 | $450 | Rare |
| Mosasaurus | 5 | $600 | Rare |
| Spinosaurus | 6 | $700 | Rare |
| T-Rex | 6 | $1,000 | Very rare |
| Giganotosaurus | 7 | $1,500 | Very rare |

When you complete a skeleton, chat gets a **SKELETON COMPLETE!** message. Dinosaurs worth $500 or more get extra hype. You can complete the same dinosaur more than once.

### 1-1 fossils

Golden T-Rex Skull, Crystal Raptor Claw, Dragon Bone, Perfect Dino Egg, Fossilised Heart, Sue's Lost Tooth, The Rainbow Trilobite and Meteorite Fragment.

- Once someone digs one up, nobody else can get it that season.
- Chat gets its own *"WOW!!! @Bob dug up Dragon Bone, a 1-1 fossil worth $18,250.00!"* message.

---

## Settings

**Actions tab** → **FFY Dino** group → **FFY Dino** → double-click **Execute C# Code**. Everything is between `EDIT BELOW` and `EDIT ABOVE`:

| Setting | What it does |
|---|---|
| `ResetDays = 30;` | **The season.** Every museum and wallet is wiped after this many days. `0` = never reset. |
| `DigsPerDay = 1;` | How many digs each viewer gets per day. |
| `FindsPerDig = 5;` | How many things each dig turns up. |
| `NewBoneChance = 50;` | Out of 100, how often a bone is one you still need. Higher = skeletons complete faster. |
| `Money = "$";` | The money symbol, e.g. `"£"` or `"€"`. |
| `FossilChance`, `JunkChance`, `AmberChance`, `LegendaryChance` | The chance of each kind of find, out of 100. |
| `Dino(...)` lines | The dinosaurs: `Dino("name", chance, skeleton value, bones...)`. Add your own, e.g. `Dino("Dilophosaurus", 12, 200, "Skull", "Crests", "Ribs", "Legs", "Tail");` |
| `Junk(...)` | The junk you can find. |
| `Amber(...)` | Amber treasures: `Amber(lowest value, highest value, names...)`. |
| `Legendary(...)` | The 1-1 fossils: `Legendary(lowest value, highest value, names...)`. |
| `SpareBonePercent = 10;` | A spare bone sells for this share of its skeleton's value, out of 100. |
| `BigSkeletonValue = 500;` | Skeletons worth this much or more get the extra-hype message. |
| `BestCount = 5;` | How many treasures `!bestfossils` shows. |
| The `...Message` lines | Every message chat sees. Change the wording, but keep the `{...}` placeholders. |

Click **Save and Compile** after changing anything.

---

## Good to know

- **Everything is saved** in the **Global Variables** tab as `ffy.dino`. Deleting it starts a new season straight away.
- **A "day"** follows your PC's clock and resets at midnight.
- **Long messages are split** so chat doesn't cut them off.
- **Stop spam:** give `!museum`, `!bones` and `!dinotop` a cooldown in the **Commands** tab.

---

## Troubleshooting

- **No reply:** check the commands are switched on in the **Commands** tab, in the **FFY Dino** folder.
- **"Save and Compile" error:** look for a missing `"`, `,` or `;` on the line it mentions.
