# FFY Bonfire Night

Remember, remember! Bonfire Night commands with sparklers, fireworks, toffee apples, firework-offs and a Guy of the Day.

You'll need **FFY Commands** installed before this one, as it runs on top of it.

## Installing

Download the **`FFY-Bonfire-Night`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it, the commands are already switched on. Try `!sparkler` in chat.

If there are a few you don't want, go to the **Commands** tab, open the **FFY Bonfire Night** folder and untick **Enabled** on those.

## The commands (11)

| Command | What it is | Example reply |
|---|---|---|
| `!sparkler` | 0–100 % | @Bob, your sparkler skills are at 50% today! |
| `!fireworks` | 0–100 % | @Bob, your fireworks are 50% spectacular today! Oooooh! |
| `!toffeeapple` | 0–10 toffee apples | @Bob, you've eaten 5 toffee apples today! Mind your teeth. |
| `!guy` | 0–100 % | @Bob, you're 50% Guy Fawkes today. Remember, remember! |
| `!firework` | 8 choices | @Bob set off a Catherine wheel that won't spin! |
| `!sparklerword` | 8 choices | @Bob wrote your name (backwards) with their sparkler! |
| `!bonfirefood` | 8 choices | @Bob's Bonfire Night food today is a jacket potato wrapped in foil! |
| `!toffeeshare @Sam` | Interaction | @Bob Shared a toffee apple with @Sam with 73% power! |
| `!rocket @Sam` | Interaction | @Bob Set off a rocket for @Sam with 73% power! |
| `!fireworkoff @Sam` | Duel | @Bob wins the firework-off (87 vs 38)! @Sam's rocket fizzled out. |
| `!guyofday` | Guy of the Day | Who won today. Win it by getting 100% on `!guy` |

## Changing things

Head to the **Actions** tab and open the **FFY Bonfire Night** group. Double-click **Execute C# Code** in the action you want, change the bits between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile** when you're done.

| Action | What's in it |
|---|---|
| **FFY Bonfire Night Numbers** | The number commands (min, max and the reply) |
| **FFY Bonfire Night Lists** | The pick-from-a-list commands |
| **FFY Bonfire Night Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Bonfire Night Duels** | The duels |
| **FFY Bonfire Night Of The Day** | The "of the Day" titles |
| **FFY Bonfire Night Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Bonfire Night Setup** | Runs once on import |

Want to add your own command? The FFY Commands guide shows how to add a number or list command. Put the lines in **FFY My Number Commands** or **FFY My List Commands** and updates will never touch them.

These work with all the usual FFY Commands stuff as well, like special users, user variables, the switches and `!top` for the interactions.

## Troubleshooting

- **Nothing replies:** is **FFY Commands** installed? Look for `[FFY Bonfire Night]` in the **Logs** tab.
- **Only one command is quiet:** check it's switched on in the **Commands** tab, in the **FFY Bonfire Night** folder.

For anything else, there's a troubleshooting section in the FFY Commands guide.
