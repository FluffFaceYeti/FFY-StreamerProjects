# FFY Overlays

OBS overlays for your stream. Each one is just a single HTML file, so there's no Streamer.bot, no login and nothing to install.

## FFY Raid Battle

**[`FFY-RaidBattle.html`](FFY-RaidBattle.html)** turns raids into a battle. You and the raider pop up on screen, your chat spams your emotes, the raiders spam theirs, and every emote makes that side's character bigger. Biggest one when the timer ends gets the crown.

It works out whose emotes are whose by itself, and that includes 7TV and BTTV ones.

### Themes

There are 20 to pick from, or you can have a random one for each raid. Each has its own colours and a few settings of its own.

| Theme | What grows | Where the picture goes |
|---|---|---|
| Beard | The beard | The face |
| Ghost | The whole ghost | In its see-through tummy |
| T-Rex | The whole dino | On its belly |
| Sausage Dog | The body gets longer | On its side |
| Chonky Cat | The belly | On its belly |
| Hot Air Balloon | The balloon | On the balloon |
| Snowman | More snowballs | On the bottom snowball |
| Pumpkin | The whole pumpkin | Like a carved face |
| Cake | More tiers | The cake topper |
| Slime | The blob | Floating inside it |
| Cobra | The body | On its hood |
| Rocket | The hull and the flame | The porthole |
| Robot | The whole robot | The head screen |
| Mohawk | The hair | The face |
| Frog | The whole frog | On its belly |
| Burger | More layers | On a cocktail stick |
| Tree | The whole tree | In the leaves |
| Octopus | The tentacles | On its head |
| Wizard Hat | The hat | The face |
| Dragon | The fire | On its belly |

### Other settings

- **Timer:** in the middle, at the top or bottom, or off. Ring or plain numbers.
- **Health bar:** one tug of war bar, or two health bars that drain as the other side spams. With two bars you can have an empty bar end the battle early.
- **Battle:** how long it lasts, how long the winner shows, the smallest raid worth battling and how quickly things grow.
- **On screen:** names, emote counts, which emotes to spam, the winner's name, flying emotes, character size, darkening the screen behind, picture shape and an outline for the picture if you want one.

### Setting it up

Download `FFY-RaidBattle.html` and open it in your browser. Type in your Twitch channel, pick a theme and change whatever you like. The preview on the right updates as you go.

When you're happy, click **Get OBS link** to copy the link. In OBS, add a **Browser** source at **1920 × 1080**, leave **Local file** unticked and paste the link into the URL box. You won't see anything until someone raids.

The source has to be in the scene you're on when the raid lands, so add it to every scene you might be live on. Use **Add Existing** after the first one so it's the same source each time.

### Commands

You and your mods can use these:

| Command | What it does |
|---|---|
| `!raidtest` | Runs a test battle with pretend emotes |
| `!raidbattle @someone` | Starts a battle against that channel, without a raid |
| `!raidstop` | Ends a battle early |
| `!raidtheme ghost` | Sets the theme until the overlay reloads. Use one word: `beard`, `ghost`, `dino`, `dog`, `cat`, `balloon`, `snowman`, `pumpkin`, `cake`, `slime`, `snake` (the cobra), `rocket`, `robot`, `mohawk`, `frog`, `burger`, `tree`, `octopus`, `wizard` or `dragon` |

The old `!beardtest`, `!beardbattle` and `!beardstop` still work too.

## Supporting me

These are free. If you'd like to leave a tip, my Ko-fi is **[ko-fi.com/flufffaceyeti](https://ko-fi.com/flufffaceyeti)**.
