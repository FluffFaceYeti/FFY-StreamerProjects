# FFY Pokemon

Chat gets to open Pokémon booster packs. Each one has 10 cards plus an Energy, like a real pack, and every card comes with a PSA grade and a price. Once it's open, viewers can keep the pack in their binder or sell it to the trader for coins.

```
Bob: !pokemon
Chat: @Bob opened pack 1/1: Metal Energy, Zubat, Pichu, Bronzor, Trubbish, Dusclops, Boldore, Whirlipede, Kirlia (Reverse Holo), Vileplume (Reverse Holo), Mewtwo. Best: Mewtwo (PSA 8, $588.01). Worth $779.17. !keep, !sell all or !sell bulk
Bob: !sell bulk
Chat: @Bob sold 9 bulk cards for $132.03 and kept 2 hits! Wallet: $132.03.
Bob: !binder
Chat: @Bob's binder: 2 cards worth $647.14 | Top 3: Mewtwo (PSA 8, $588.01), Vileplume (Reverse Holo, PSA 6, $59.13)
Bob: !pokemonwallet
Chat: @Bob's wallet: $132.03
```

All 1,025 Pokémon are in there, plus the odd god pack and ten 1-1 Pikachus. You decide how many packs people get a day and how often everything resets.

It doesn't need FFY Commands and it works on Twitch, Kick and YouTube.

## Installing

Download the **`FFY-Pokemon`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's all. The commands are already on, so type `!pokemon` in chat and rip your first pack.

## Commands

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
| `!bestcards` | The most valuable cards in the whole channel, and who owns them, e.g. *1. Pikachu Galar (PSA 10, $99,203.63) owned by @Zed*. You choose how many (top 3, 5, 9...). |
| `!pokemontop` | The top 5 collectors, by binder value. |

If someone forgets to `!keep` or sell a pack, it goes into their binder by itself when they open the next one. And when they've used up their packs for the day, `!pokemon` tells them *"that's all your packs for today (3/3)! Come back tomorrow!"*

## What's in a pack

The packs are based on a real Scarlet & Violet booster:

| Slot | Cards | What can be in it |
|---|---|---|
| Energy | 1 | A basic Energy |
| Common | 4 | Commons |
| Uncommon | 3 | Uncommons |
| Reverse Holo | 1 | A reverse holo Common, Uncommon or Rare |
| Reverse Holo or better | 1 | Usually a reverse holo, sometimes a Holo, Ultra or Secret Rare |
| Rare or better | 1 | At least a Rare, with a chance of Holo, Ultra, Secret Rare or a **1-1** |

Reverse holos have **(Reverse Holo)** after the name and they're worth double.

### God packs

Roughly 1 in every 2,000 packs is a god pack, where every single card is a Holo, Ultra or Secret Rare. Chat gets one big announcement and the whole thing goes straight into the binder, so there's nothing to keep or sell:

```
GOD PACK ALERT!!! @Bob JUST RIPPED OPEN A GOD PACK!!! EVERY. SINGLE. CARD. IS. A. HIT! The best pull is Gold Rayquaza (PSA 8, $7,966.37) and the whole pack is worth $12,222.68! It's gone straight into their binder. CHAT, GO WILD!!!
```

### Big hits

If you pull an Ultra Rare or Secret Rare in a normal pack, it gets its own message after the pack:

```
BIG HIT!!! @Bob just pulled Latias (PSA 9, $1,204.50)! WHAT A PULL!
```

### 1-1s

There are ten special Pikachus that can turn up in the Rare slot, in about 1 in 1,000 packs: Pikachu Kanto, Johto, Hoenn, Sinnoh, Hisui, Unova, Kalos, Alola, Galar and Paldea.

Each one can only belong to one person. So once someone's pulled Pikachu Kanto, that's it, nobody else can get it. They're always PSA 10 and worth anywhere from $20,000 to $100,000, and chat gets a message like *"WOW!!! @Bob pulled Pikachu Kalos, PSA 10, a 1-1 card worth $60,858.54!"*

If the owner sells theirs, it goes back into the packs for someone else to find. They all go back up for grabs when the season resets too. If all ten are owned, that slot gives a Secret Rare instead.

## How cards are valued

The rarity sets the starting value:

| Rarity | Value range | Cards | Which Pokémon |
|---|---|---|---|
| Energy | $0.05 – $0.25 | 8 | Basic Energy |
| Common | $0.25 – $3 | 308 | First forms that evolve: Pidgey, Caterpie, Magikarp, Zubat |
| Uncommon | $1 – $8 | 142 | Starters and middle evolutions: Charmander, Ivysaur, Pidgeotto |
| Rare | $5 – $40 | 419 | Fully evolved, and Pokémon that don't evolve: Butterfree, Raichu, Tauros |
| Holo Rare | $20 – $150 | 62 | Final starters, pseudo-legendaries and fan favourites: Charizard, Dragonite, Gengar, Pikachu, Eevee |
| Ultra Rare | $100 – $800 | 102 | Every legendary and mythical, plus ex/VMAX cards: Mewtwo, Lugia, Charizard ex |
| Secret Rare | $500 – $5,000, always PSA 7 or better | 14 | Gold, Shiny and Illustrator cards: Gold Charizard, Shiny Umbreon |
| 1-1 | $2,000 – $10,000 (always PSA 10) | 10 | The regional Pikachus |

Then the PSA grade multiplies it:

| PSA | Chance | Value |
|---|---|---|
| 10 | 3% | ×10 |
| 9 | 12% | ×3 |
| 8 | 20% | ×1.6 |
| 7 | 20% | ×1.2 |
| 6 | 15% | ×1 |
| 5 and below | 30% | ×0.8 down to ×0.25 |

## Settings

Go to the **Actions** tab, open the **FFY Pokemon** group and the **FFY Pokemon** action, and double-click **Execute C# Code**. The settings are all between `EDIT BELOW` and `EDIT ABOVE`:

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
| The `...Message` lines | Every message chat sees. Change the wording, but keep the `{...}` placeholders. `{opened}/{limit}` is the "pack 2/3" counter. Change `GodPackMessage`, `BigHitMessage` or `OneOfOneMessage` to make the hype your own. |

Click **Save and Compile** once you've made your changes.

To add a card, put its name on the end of one of the `Tier(...)` lists, in quotes with a comma before it. Say you wanted a Gold Mew in Secret Rare:

```csharp
            "Shiny Gyarados", "Rainbow Umbreon", "Gold Lugia", "Illustrator Charizard", "Gold Mew");
```

Adding a 1-1 works the same way, just in the `Tier("1-1", ...)` list.

Want bigger packs? Change the number in a `Slot(...)` line. `Slot("Common", 6, "Common", 100);` would give you 6 commons, for example.

## Worth knowing

Everyone's cards are saved in the **Global Variables** tab as `ffy.pokemon`. Delete that and a new season starts right away.

To keep the save small, hits are stored card by card but bulk isn't. Energy, Commons and Uncommons are just saved as a count and a total value.

When a season ends, the next command anyone uses says *"A new Pokémon season has started!"*, and everybody starts over with an empty binder and wallet.

A "day" goes by your PC's clock and resets at midnight.

If a pack message is too long for chat, it gets sent in two parts.

`!pokemontop`, `!bestcards`, `!binder` and `!pokemonwallet` are the ones people tend to spam, so a cooldown in the **Commands** tab is a good idea.

## If something's not working

**No reply:** make sure the commands are switched on in the **FFY Pokemon** folder in the **Commands** tab.

**The Logs tab says "No Tier(...) line called ...":** one of your `Slot(...)` or `GodPack(...)` lines mentions a rarity that doesn't have a `Tier(...)` line. Usually it's a typo.

**Save and Compile error:** look for a missing `"`, `,` or `;` on the line it points to.
