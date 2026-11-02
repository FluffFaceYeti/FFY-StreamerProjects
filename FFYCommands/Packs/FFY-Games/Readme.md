# FFY Games

Little games for chat to play against each other. Duels, dice, rock-paper-scissors, tug of war and more.

It's a pack for **FFY Commands**, so install that first.

## Installing

Download the **`FFY-Games`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it, the commands are already switched on. Try `!bootybattle` in chat.

If there are a few you don't want, go to the **Commands** tab, open the **FFY Games** folder and untick **Enabled** on those.

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

## Changing things

Head to the **Actions** tab and open the **FFY Games** group. Double-click **Execute C# Code** in the action you want, change the bits between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile** when you're done.

| Action | What's in it |
|---|---|
| **FFY Duels** | Settings and replies for its commands |
| **FFY Dice** | Settings and replies for its commands |
| **FFY Games Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Games Setup** | Runs once on import |

> Updating the pack replaces these actions, so if you want a change to stick, put it in the FFY My actions (in FFY Commands) instead. See [Keeping your changes safe from updates](../../QuickGuide.md#21-keeping-your-changes-safe-from-updates).

## Troubleshooting

- **Nothing replies:** is **FFY Commands** installed? Look for `[FFY Games]` in the **Logs** tab.
- **Only one command is quiet:** check it's switched on in the **Commands** tab, in the **FFY Games** folder.

If it's something else, have a look at the [troubleshooting section](../../QuickGuide.md#28-troubleshooting) in the FFY Commands guide.
