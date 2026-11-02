# FFY Halloween

Spooky (well, mostly silly) Halloween commands, and a bunch of **Nightmare Before Christmas** ones thrown in.

You'll need **FFY Commands** installed before this one, as it runs on top of it.

## Installing

Download the **`FFY-Halloween`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

That's it, the commands are already switched on. Try `!spooky` in chat.

If there are a few you don't want, go to the **Commands** tab, open the **FFY Halloween** folder and untick **Enabled** on those.

## The commands (17)

| Command | What it is | Example reply |
|---|---|---|
| `!spooky` | 0–100 % | @Bob, you're 50% spooky today! Boo! |
| `!witch` | 0–100 % | @Bob, you're 50% witch today! Mind the broomstick. |
| `!vampire` | 0–100 % | @Bob, you're 50% vampire today! Stay out of the sun. |
| `!zombie` | 0–100 % | @Bob, you're 50% zombie today... braaaains! |
| `!haunted` | 0–100 % | @Bob, your house is 50% haunted today! Did you hear that? |
| `!jack` | 0–100 % | @Bob, your Pumpkin King energy is at 50% today! What's this?! |
| `!zero` | 0–100 % | @Bob, Zero the ghost dog follows you 50% loyally today! |
| `!costume` | 12 choices | @Bob, your Halloween costume today is: Vampire! |
| `!pumpkin` | 10 choices | @Bob, you carved a Scary Face into your pumpkin today! |
| `!candy` | 10 choices | @Bob, you got A Full-Size Chocolate Bar in your trick-or-treat bag today! |
| `!trickortreat` | 7 choices | @Bob knocks on the door... TREAT! Here's a chocolate bar. |
| `!sally` | 26 choices | @Bob, Sally gave you a dress of stitched-together patches today! |
| `!oogieboogie` | 25 choices | Oogie Boogie rolled the dice against @Bob and got snake eyes. Oogie Boogie wins! |
| `!halloweentown` | 30 choices | @Bob, your job in Halloween Town today is: Pumpkin King! |
| `!whatsthis` | 33 choices | @Bob wanders into Christmas Town... What's this? It's snow! |
| `!spook @Sam` | Interaction | @Bob Spooked @Sam with 73% power! |
| `!pumpkinkingofday` | Pumpkin King of the Day | Who won today. Win it by getting 100% on `!jack` |

## Changing things

Head to the **Actions** tab and open the **FFY Halloween** group. Double-click **Execute C# Code** in the action you want, change the bits between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile** when you're done.

| Action | What's in it |
|---|---|
| **FFY Halloween Numbers** | The number commands (min, max and the reply) |
| **FFY Halloween Lists** | The pick-from-a-list commands |
| **FFY Halloween Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Halloween Of The Day** | The "of the Day" titles |
| **FFY Halloween Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Halloween Setup** | Runs once on import |

Want to add your own command? The FFY Commands guide shows how to add a number or list command. Put the lines in **FFY My Number Commands** or **FFY My List Commands** and updates will never touch them.

These work with all the usual FFY Commands stuff as well, like special users, user variables, the switches and `!top` for the interactions.

## Troubleshooting

- **Nothing replies:** is **FFY Commands** installed? Look for `[FFY Halloween]` in the **Logs** tab.
- **Only one command is quiet:** check it's switched on in the **Commands** tab, in the **FFY Halloween** folder.

For anything else, there's a troubleshooting section in the FFY Commands guide.
