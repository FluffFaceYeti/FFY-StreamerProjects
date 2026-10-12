# FFY Pokemon

Your chat opens **Pokémon booster packs**: 10 cards plus an Energy, just like a real pack. Every card has a **PSA grade** and a **value**. Viewers can **keep** a pack in their binder, or **sell** it to the trader for coins.

```
Bob: !pokemon
Chat: @Bob opened pack 1/1: Metal Energy, Zubat, Pichu, Bronzor, Trubbish, Dusclops, Boldore, Whirlipede, Kirlia (Reverse), Vileplume (Rare Reverse), Mewtwo (Ultra Rare). Best pull: Mewtwo (Ultra Rare, PSA 8, $588.01). Pack worth $779.17. Type "!keep" to keep it, "!sell all" to sell it all, or "!sell bulk" to keep only the hits.
Bob: !sell bulk
Chat: @Bob sold 9 bulk cards for $132.03 and kept 2 hits! Wallet: $132.03.
Bob: !binder
Chat: @Bob's binder: 2 cards worth $647.14 | Top 3: Mewtwo (Ultra Rare, PSA 8, $588.01), Vileplume (Rare Reverse, PSA 6, $59.13)
Bob: !pokemonwallet
Chat: @Bob's wallet: $132.03
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- All **1,025 Pokémon**, plus rare **god packs** and ten **1-1** Pikachus.
- You choose how many packs a day, and how often everything **resets**.

---

## Installing

1. Download the **`FFY-Pokemon`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!pokemon` in chat to test.

---

## The commands

| Command | What it does |
|---|---|
| `!pokemon` | Opens a pack. The message says which pack of the day it is, e.g. **pack 2/3**. |
| `!keep` | Puts the whole pack in your binder. |
| `!sell all` (or `!sellall`) | Sells the whole pack to the trader. The money goes in your wallet. |
| `!sell bulk` (or `!sellbulk`) | Sells the bulk (Energy, Commons and Uncommons) and keeps the hits. |
| `!sell` | Asks whether you mean `!sell all` or `!sell bulk`, so nobody sells a pack by accident. |
| `!binder` | Shows how many cards you have, their total value, and your top 3 cards. |
| `!binder @Sam` | Shows someone else's binder. |
| `!pokemonwallet` | Shows how much money you have from selling. `!pokemonwallet @Sam` shows someone else's. |
| `!pokemonseason` | Shows how many days are left until the season resets. |
| `!bestcards` | The most valuable cards in the whole channel, and who owns them, e.g. *1. Pikachu Galar (1-1, PSA 10, $99,203.63) owned by @Zed*. You choose how many (top 3, 5, 9...). |
| `!pokemontop` | The top 5 collectors, by binder value. |

> If someone doesn't `!keep` or sell a pack, it goes into their binder automatically when they open their next one.
>
> Once they've opened all their packs, `!pokemon` says *"that's all your packs for today (3/3)! Come back tomorrow!"*

---

## What's in a pack

Packs follow a real Scarlet & Violet booster:

| Slot | Cards | What can be in it |
|---|---|---|
| Energy | 1 | A basic Energy |
| Common | 4 | Commons |
| Uncommon | 3 | Uncommons |
| Reverse Holo | 1 | A reverse holo Common, Uncommon or Rare |
| Reverse Holo or better | 1 | Usually a reverse holo, sometimes a Holo, Ultra or Secret Rare |
| Rare or better | 1 | At least a Rare, with a chance of Holo, Ultra, Secret Rare or a **1-1** |

Reverse holo cards show **(Reverse)** and are worth **double**.

### God packs

About **1 in 2,000** packs is a **god pack**: every card is a Holo, Ultra or Secret Rare. Chat gets a big announcement before the pack:

```
GOD PACK ALERT!!! @Bob JUST RIPPED OPEN A GOD PACK!!! EVERY. SINGLE. CARD. IS. A. HIT! The best pull is Gold Rayquaza (S-Rare, PSA 8, $7,966.37) and the whole pack is worth $12,222.68! CHAT, GO WILD!!!
```

### Big hits

Pulling an **Ultra Rare** or **Secret Rare** in a normal pack gets its own message after the pack:

```
BIG HIT!!! @Bob just pulled Latias (Ultra Rare, PSA 9, $1,204.50)! WHAT A PULL!
```

### 1-1s

Ten special Pikachus can come out of the Rare slot, about **1 in 1,000** packs:

Pikachu Kanto, Johto, Hoenn, Sinnoh, Hisui, Unova, Kalos, Alola, Galar and Paldea.

- **Only one person can own each one.** Once someone pulls Pikachu Kanto, nobody else can get it.
- They're **always PSA 10**, worth $20,000 to $100,000. Chat gets its own *"WOW!!! @Bob pulled Pikachu Kalos, PSA 10, a 1-1 card worth $60,858.54!"* message.
- If the owner **sells** it, it goes back into the packs for someone else to pull.
- When the season resets, they're all back up for grabs.
- Once all ten are owned, that slot gives a Secret Rare instead.

---

## How cards are valued

**Rarity** sets the card's base value:

| Rarity | Value range | Cards | Which Pokémon |
|---|---|---|---|
| Energy | $0.05 – $0.25 | 8 | Basic Energy |
| Common | $0.25 – $3 | 308 | First forms that evolve: Pidgey, Caterpie, Magikarp, Zubat |
| Uncommon | $1 – $8 | 142 | Starters and middle evolutions: Charmander, Ivysaur, Pidgeotto |
| Rare | $5 – $40 | 419 | Fully evolved, and Pokémon that don't evolve: Butterfree, Raichu, Tauros |
| Holo Rare | $20 – $150 | 62 | Final starters, pseudo-legendaries and fan favourites: Charizard, Dragonite, Gengar, Pikachu, Eevee |
| Ultra Rare | $100 – $800 | 102 | Every legendary and mythical, plus ex/VMAX cards: Mewtwo, Lugia, Charizard ex |
| Secret Rare (shown as **S-Rare**) | $500 – $5,000, always PSA 7 or better | 14 | Gold, Shiny and Illustrator cards: Gold Charizard, Shiny Umbreon |
| 1-1 | $2,000 – $10,000 (always PSA 10) | 10 | The regional Pikachus |

**The PSA grade** then multiplies the value:

| PSA | Chance | Value |
|---|---|---|
| 10 | 3% | ×10 |
| 9 | 12% | ×3 |
| 8 | 20% | ×1.6 |
| 7 | 20% | ×1.2 |
| 6 | 15% | ×1 |
| 5 and below | 30% | ×0.8 down to ×0.25 |

---

## Settings

**Actions tab** → **FFY Pokemon** group → **FFY Pokemon** → double-click **Execute C# Code**. Everything is between `EDIT BELOW` and `EDIT ABOVE`:

| Setting | What it does |
|---|---|
| `ResetDays = 30;` | **The season.** Every binder and wallet is wiped after this many days. `0` = never reset. |
| `PacksPerDay = 1;` | How many packs each viewer can open per day. |
| `BestCardsCount = 5;` | How many cards `!bestcards` shows, e.g. `3` or `9`. |
| `Money = "$";` | The money symbol, e.g. `"£"` or `"€"`. |
| `Slot(...)` lines | **What's in a pack.** `Slot("name", how many cards, rarity, chance, rarity, chance...)`. Add `Reverse` after a rarity for a reverse holo, e.g. `"Rare Reverse"`. |
| `ReverseMultiplier = 2;` | How much more a reverse holo is worth. |
| `GodPackChance = 0.05;` | The chance of a god pack, out of 100. `0.05` = 1 in 2,000. `0` = never. |
| `GodPack(...)` | Which rarities a god pack's cards come from, and their chances. |
| `BigHit(...)` | Which rarities get a **BIG HIT!!!** message, e.g. `BigHit("Ultra Rare", "Secret Rare");`. Add `"Holo Rare"` for more hype, or remove one for less. |
| `Bulk(...)` | Which rarities count as bulk. `!sell bulk` sells these and keeps the rest. |
| `Tier(...)` lines | The rarities: `Tier("name", lowest value, highest value, cards...)`. |
| `OneOfOne(...)` | Which rarities are 1-1s (always PSA 10, one owner each). |
| `Grade(...)` lines | The PSA grades: `Grade(grade, chance, value multiplier)`. |
| `MinGrade(...)` | The lowest PSA a rarity can get, e.g. `MinGrade("Secret Rare", 7);` means Secret Rares are always PSA 7 to 10. Add a line for any rarity, e.g. `MinGrade("Ultra Rare", 5);`. |
| `Short(...)` | A shorter name shown in chat, e.g. `Short("Secret Rare", "S-Rare");`. Add more to keep messages short, e.g. `Short("Ultra Rare", "U-Rare");`. |
| The `...Message` lines | Every message chat sees. Change the wording, but keep the `{...}` placeholders. `{opened}/{limit}` is the "pack 2/3" counter. Change `GodPackMessage`, `BigHitMessage` or `OneOfOneMessage` to make the hype your own. |

Click **Save and Compile** after changing anything.

**Adding a card:** add its name to the end of a `Tier(...)` list, in quotes, with a comma before it. For example, to add a Gold Mew to Secret Rare:

```csharp
            "Shiny Gyarados", "Rainbow Umbreon", "Gold Lugia", "Illustrator Charizard", "Gold Mew");
```

**Adding a 1-1:** add its name to the `Tier("1-1", ...)` list the same way.

**Bigger packs:** change the number in a `Slot(...)` line, e.g. `Slot("Common", 6, "Common", 100);` for 6 commons.

---

## Good to know

- **Everyone's cards** are saved in the **Global Variables** tab as `ffy.pokemon`. Deleting it starts a new season straight away.
- **Bulk is saved as a total.** Hits are saved card by card, but Energy, Commons and Uncommons are only kept as a count and a value, so the save stays small.
- **When a season ends,** the next command shows *"A new Pokémon season has started!"*, and everyone starts again with an empty binder and wallet.
- **A "day"** follows your PC's clock and resets at midnight.
- **Long messages are split.** A pack message that's too long for chat is sent in two parts.
- **Stop spam:** give `!pokemontop`, `!bestcards`, `!binder` and `!pokemonwallet` a cooldown in the **Commands** tab.

---

## Troubleshooting

- **No reply:** check the commands are switched on in the **Commands** tab, in the **FFY Pokemon** folder.
- **The Logs tab says "No Tier(...) line called ...":** a `Slot(...)` or `GodPack(...)` line names a rarity that has no `Tier(...)` line. Check the spelling.
- **"Save and Compile" error:** look for a missing `"`, `,` or `;` on the line it mentions.
