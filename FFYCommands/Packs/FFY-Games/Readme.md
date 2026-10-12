# FFY Games

Duels, dice, rock-paper-scissors, tug of war and more. A pack for **FFY Commands**.

> **You need FFY Commands installed first.** Install FFY Commands, then this pack.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Games`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!bootybattle` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Games** folder and untick **Enabled** on the ones you don't want.

---

## The commands (16)

| Command | What it is | Example reply |
|---|---|---|
| `!bootybattle @Sam` | Duel on booty | The crowd goes wild as @Bob's 100% booty steals the show! |
| `!plunderraid @Sam` | Duel on plundering | @Bob pillaged with unmatched fury, looting 28% of the treasure! @Sam was left with scraps (20%). |
| `!pistolfight @Sam` | Duel on intimidation | @Sam shot true - @Bob drops their pistol in surrender! (99% vs 43%) |
| `!shipbattle @Sam` | Duel on cannon skills | @Sam broadside-shattered @Bob's hull! (45% vs 36%) - glorious victory! |
| `!swordfight @Sam` | Duel on swordsmanship | @Sam wins the duel! @Bob shall be swabbing decks tonight (15% vs 13%). |
| `!ppduel @Sam` | Duel on PP size | @Bob and @Sam clashed in an epic PP duel. It's a draw at 7 inches each! |
| `!d20` | Roll a D20 | @Bob, you rolled a d20 and got **17**! |
| `!d12` | Roll a D12 | @Bob, you rolled a d12 and got **5**! |
| `!randomcoinflip` | Heads or tails | @Bob, you flipped a coin and got **Heads**! |
| `!rps @Sam` | Rock, paper, scissors | @Bob wins! rock beats scissors. |
| `!rpsls @Sam` | Rock, paper, scissors, lizard, Spock | @Sam wins! spock beats rock. |
| `!tugofwar @Sam` | Tug of war | @Sam wins! Pulled with 90 vs @Bob's 36. |
| `!diceroll @Sam` | Highest dice roll wins | @Sam wins! 4 vs @Bob's 2 |
| `!coinflip` | Flip a coin | @Bob flips a coin... Tails! |
| `!highorlow @Sam` | Guess higher or lower | @Bob guessed higher — correct! The number was 74. |
| `!compat @Sam` | Compatibility test | Sparks fly! @Bob & @Sam are 67% in sync. |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Games** group. Open an action, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Duels** | Settings and replies for its commands |
| **FFY Dice** | Settings and replies for its commands |
| **FFY Games Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Games Setup** | Runs once on import |

> **Updating this pack replaces these actions.** To keep a change safe, put it in the FFY My actions (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Games]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Games** folder)?
- **Anything else:** see the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
