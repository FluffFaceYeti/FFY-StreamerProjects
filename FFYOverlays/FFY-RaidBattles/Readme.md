# FFY Raid Battles

This one turns raids into a battle. You and the raider pop up on screen, your chat spams your emotes, the raiders spam theirs, and every emote makes that side's character bigger. Whoever's biggest when the timer ends gets the crown.

It works out whose emotes are whose by itself, and that includes 7TV and BTTV ones.

There are 20 themes, or you can have a random one for each raid: Beard, Ghost, T-Rex, Sausage Dog, Chonky Cat, Hot Air Balloon, Snowman, Pumpkin, Cake, Slime, Cobra, Rocket, Robot, Mohawk, Frog, Burger, Tree, Octopus, Wizard Hat and Dragon.

You can also change the timer, the health bars, how long a battle lasts, the smallest raid worth battling and what shows on screen.

## Setting it up

1. Download **[`FFYRaidBattle.html`](FFYRaidBattle.html)** and open it in your browser.
2. Type in your Twitch channel, pick a theme and change whatever you like. The preview updates as you go.
3. Click **Get OBS link**.
4. In OBS, add a **Browser** source, paste the link into **URL** and set the size to **1920 x 1080**. Leave **Local file** unticked.

You won't see anything until someone raids. The source has to be in the scene you're on when the raid lands, so add it to every scene you might be live on. Use **Add Existing** after the first one so it's the same source each time.

## Commands

You and your mods can use these:

| Command | What it does |
|---|---|
| `!raidtest` | Runs a test battle with pretend emotes |
| `!raidbattle @someone` | Starts a battle against that channel, without a raid |
| `!raidstop` | Ends a battle early |
| `!raidtheme ghost` | Sets the theme until the overlay reloads |

For `!raidtheme`, use one word: `beard`, `ghost`, `dino`, `dog`, `cat`, `balloon`, `snowman`, `pumpkin`, `cake`, `slime`, `snake` (the cobra), `rocket`, `robot`, `mohawk`, `frog`, `burger`, `tree`, `octopus`, `wizard` or `dragon`.

The old `!beardtest`, `!beardbattle` and `!beardstop` still work too.
