# FFY Summer

Summer commands for when it's too hot to think. Sunburn, ice cream, things you find on the beach, sandcastle contests and a Lobster of the Day.

You'll need **FFY Commands** installed before this one, as it runs on top of it.

## Installing

Download the **`FFY-Summer`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it, the commands are already switched on. Try `!sunburn` in chat.

If there are a few you don't want, go to the **Commands** tab, open the **FFY Summer** folder and untick **Enabled** on those.

## The commands (12)

| Command | What it is | Example reply |
|---|---|---|
| `!sunburn` | 0–100 % | @Bob, you're 50% sunburnt today! Ouch. |
| `!tan` | 0–100 % | @Bob, your tan is 50% golden today! |
| `!icecream` | 0–10 scoops | @Bob, you've had 5 scoops of ice cream today! |
| `!heatwave` | 18–40 °C | @Bob, it's 29°C where you are today. Melting! |
| `!beachready` | 0–100 % | @Bob, you're 50% beach ready today! |
| `!getaway` | 8 choices | @Bob, your summer getaway today is a beach in Spain! |
| `!icecreamflavour` | 8 choices | @Bob's ice cream today is mint choc chip! |
| `!beachfind` | 8 choices | @Bob found a perfect seashell on the beach! |
| `!splash @Sam` | Interaction | @Bob Splashed @Sam with 73% power! |
| `!waterballoon @Sam` | Interaction | @Bob Threw a water balloon at @Sam with 73% power! |
| `!sandcastle @Sam` | Duel | @Bob's sandcastle wins (87 vs 38)! @Sam's collapsed into a sad lump. |
| `!lobsterofday` | Lobster of the Day | Who won today. Win it by getting 100% on `!sunburn` |

## Changing things

Head to the **Actions** tab and open the **FFY Summer** group. Double-click **Execute C# Code** in the action you want, change the bits between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile** when you're done.

| Action | What's in it |
|---|---|
| **FFY Summer Numbers** | The number commands (min, max and the reply) |
| **FFY Summer Lists** | The pick-from-a-list commands |
| **FFY Summer Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Summer Duels** | The duels |
| **FFY Summer Of The Day** | The "of the Day" titles |
| **FFY Summer Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Summer Setup** | Runs once on import |

Want to add your own command? The FFY Commands guide shows how to add a number or list command. Put the lines in **FFY My Number Commands** or **FFY My List Commands** and updates will never touch them.

These work with all the usual FFY Commands stuff as well, like special users, user variables, the switches and `!top` for the interactions.

## Troubleshooting

- **Nothing replies:** is **FFY Commands** installed? Look for `[FFY Summer]` in the **Logs** tab.
- **Only one command is quiet:** check it's switched on in the **Commands** tab, in the **FFY Summer** folder.

For anything else, there's a troubleshooting section in the FFY Commands guide.
