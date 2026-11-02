# FFY Dino

Send chat off digging for dinosaur fossils. Most digs turn up bones, some junk, the odd bit of amber, and every now and then a legendary 1-1 fossil. Find every bone of a dinosaur and you've got a full skeleton for your museum.

```
Bob: !dig
Chat: @Bob went digging (1/1) and found: T-Rex Skull (new!), Velociraptor Claws (spare), a plastic toy dinosaur, Triceratops Horns (new!), Amber with a Mosquito. Closest skeleton: T-Rex 5/6. Type "!bones" to see your progress.
Chat: Shiny! @Bob found Amber with a Mosquito worth $212.40!
...
Chat: SKELETON COMPLETE!!! @Bob JUST FINISHED A T-REX SKELETON!!! The museum crowd goes wild! Worth $1,000.00!
```

There are 11 dinosaurs to collect, from the little Velociraptor up to the Giganotosaurus. You decide how many digs people get a day and how often it all resets.

It works without FFY Commands, on Twitch, Kick and YouTube.

## Installing

Download the **`FFY-Dino`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it. The commands are on already, so try `!dig` in chat.

## Commands

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

## How digging works

Every find is one of these:

| Find | Chance | What happens |
|---|---|---|
| A bone | 85% | A bone from a random dinosaur. **New** bones count towards its skeleton, and repeats become **spares** you can sell. |
| Junk | 10% | An old boot, a rusty spoon, a plastic toy dinosaur... worth nothing, but funny. |
| Amber | 4.95% | A treasure for your museum, worth $50 to $400. |
| 1-1 fossil | 0.05% | A legendary treasure worth $5,000 to $25,000. **Only one person can own each one.** |

Half of all bones you dig up will be ones you still need, so you're not stuck forever hunting that one last bone. You can change that in the settings.

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

Finishing a skeleton gets a **SKELETON COMPLETE!** message in chat, and the ones worth $500 or more get a bit of extra hype. You can complete the same dinosaur more than once.

### 1-1 fossils

There are eight: Golden T-Rex Skull, Crystal Raptor Claw, Dragon Bone, Perfect Dino Egg, Fossilised Heart, Sue's Lost Tooth, The Rainbow Trilobite and Meteorite Fragment.

Once someone digs one up, it's theirs and nobody else can find it that season. Chat gets a message like *"WOW!!! @Bob dug up Dragon Bone, a 1-1 fossil worth $18,250.00!"*

## Settings

In the **Actions** tab, open the **FFY Dino** group, then the **FFY Dino** action, and double-click **Execute C# Code**. The settings are between `EDIT BELOW` and `EDIT ABOVE`:

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

Don't forget to click **Save and Compile** afterwards.

## Worth knowing

Everything's saved in the **Global Variables** tab as `ffy.dino`. Delete that and a new season starts straight away.

A "day" goes by your PC's clock and resets at midnight.

Long messages get split up so chat doesn't cut them off.

If people spam `!museum`, `!bones` or `!dinotop`, stick a cooldown on them in the **Commands** tab.

## If something's not working

No reply? Check the commands are switched on in the **FFY Dino** folder in the **Commands** tab.

If **Save and Compile** gives you an error, look for a missing `"`, `,` or `;` on the line it mentions.
