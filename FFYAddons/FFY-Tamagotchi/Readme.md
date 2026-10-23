# FFY Tamagotchi

A Tamagotchi for your chat. Either every viewer hatches their own, or the whole chat looks after one together. Feed it, play with it, keep it clean and let it nap, and it grows up a little every time you go live. Forget about it, and it might fly back to the Tamagotchi Planet.

```
Bob: !tama Pickle
Chat: @Bob got a Tamagotchi! An egg wobbled, cracked, and out popped Pickle! Type !tamafeed, !tamaplay, !tamaclean and !tamasleep to look after it.
Chat: @Bob's Pink Pickle (Baby, brand new) | Hunger 80 | Happiness 80 | Rest 80 | Clean 80 | Health 100 | Mood: Over the moon *does a happy little dance*
Bob: !tamafeed
Chat: @Bob fed Pickle a dumpling! *munch munch* Hunger 100/100.
Bob: !tamacolour glitter
Chat: @Bob's Pickle is now Glitter! It's admiring itself in the mirror.
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- Moods like a real Tamagotchi: it tells chat when it's Hungry, Sleepy, Messy, Bored or Poorly.
- Its age counts your streams, and it grows from Baby to Senior.
- An **OBS overlay** shows the chat's Tamagotchi on stream, animated, reacting live when chat looks after it.

---

## Installing

1. Download the **`FFY-Tamagotchi`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you, and Stream Online triggers for Twitch, Kick and YouTube are already set up. A Tamagotchi is hatched with `!tama`. Until then, the other commands tell chat how.

---

## Two ways to play

### Everyone has their own (`SharedTamagotchi = false;`)

Every viewer hatches their own Tamagotchi with `!tama` and looks after it themselves. They can visit each other's with `!tamavisit @Sam`.

### The chat's Tamagotchi (`SharedTamagotchi = true;`)

The whole chat shares one Tamagotchi and looks after it together:

```
Mia: !tama Pickle
Chat: @Mia found an egg for the whole chat! It wobbled, cracked, and out popped Pickle! Everyone can !tamafeed, !tamaplay, !tamaclean and !tamasleep to look after it.
Sam: !tamafeed
Chat: @Sam fed Pickle a dumpling! *munch munch* Hunger 100/100.
```

- The feed, play and clean waits are shared too, so once someone has fed it, nobody can feed it again until the wait is over.
- Only mods (and you) can name it or change its colour and shell. Set `OnlyModsNameChatTamagotchi = false;` to let anyone.
- `!tamatop` shows the chat's Tamagotchi, and `!tamavisit` isn't used.
- Its stats are shown under **your** username in Persisted User Globals.

Switching between the two keeps both. Viewers' own Tamagotchis and the chat's one are saved separately.

---

## The commands

| Command | What it does |
|---|---|
| `!tama` | Hatches a Tamagotchi, then shows how it's doing: colour, name, stage, age, needs, health and mood. Add a name to hatch it with that name, e.g. `!tama Sir Wobbles`. |
| `!tamafeed` | Feeds it. It won't eat if it's already full. |
| `!tamaplay` | Plays a game with it. Makes it happy, but tires it out and makes it a bit hungry. It won't play if it's too sleepy. |
| `!tamaclean` | Tidies up after it. |
| `!tamasleep` | Puts it down for a nap. It can only nap every 2 hours. |
| `!tamaname` *name* | Renames it, e.g. `!tamaname Sir Wobbles`. |
| `!tamacolour` *colour* | Changes its colour, e.g. `!tamacolour pink`. `!tamacolor` works too. Type it on its own to see the colours. |
| `!tamashell` *shell* | Changes the shape of its shell on the OBS overlay, e.g. `!tamashell cat`. Type it on its own to see the shells. |
| `!tamastats` | Shows its needs on the OBS overlay's screen: Hunger and Happy, then Rest and Clean. Without the overlay, it shows the same as `!tama`. |
| `!tamavisit @Sam` | Visits someone else's Tamagotchi and plays with it, making it happier. 3 visits a day. |
| `!tamatop` | The 5 oldest Tamagotchis in chat. |
| `!tamahelp` | Lists the commands in chat. |

Feeding, playing and cleaning each have a 10 minute wait, so chat can't spam them.

---

## How it works

**Needs:** Hunger, Happiness, Rest and Cleanliness go from 0 to 100, and slowly drop for every hour you're **live**. When you go offline, the Tamagotchi freezes and carries on from where it was when you next go live (set `OnlyWhileLive = false;` to have them drop all the time):

| Need | Drops by | Goes up with |
|---|---|---|
| Hunger | 6 an hour | `!tamafeed` (+35) |
| Happiness | 4 an hour | `!tamaplay` (+30), feeding and cleaning (+5), visits (+15) |
| Rest | 3 an hour | `!tamasleep` (+60) |
| Cleanliness | 3 an hour | `!tamaclean` (back to 100) |

**Health:** while it's starving (Hunger 0) or filthy (Cleanliness 0), its health drops by 3 an hour. Otherwise it slowly recovers. If health reaches 0, it goes back to the Tamagotchi Planet, and the next `!tama` hatches a new egg. A Tamagotchi left alone completely lasts about 40 hours of streaming.

**Mood:** like a real Tamagotchi, it tells you what it needs. Chat sees its two most urgent moods, worst first, plus what it's doing, e.g. *Mood: Exhausted and Hungry \*can barely keep its eyes open\**.

| Mood | When |
|---|---|
| Poorly *\*sniffle sniffle\** | Health below 50 |
| Starving / Hungry | Hunger below 10 / below 30 |
| Exhausted / Sleepy | Rest below 10 / below 30 |
| Stinky / Messy | Cleanliness below 10 / below 30 |
| Lonely / Bored | Happiness below 10 / below 30 |
| Over the moon, Happy, Grumpy or Miserable | Nothing urgent. It depends on how well looked after it is overall |

**Age and growing up:** its age counts your streams. Each time you go live on Twitch, Kick or YouTube, every Tamagotchi gets 1 stream older, e.g. *"Pickle (Child, 3 streams old)"*. A newly hatched one is *brand new*. It grows from Baby to Child at 1 stream, Teen at 3, Adult at 6 and Senior at 14. Chat sees a message when it grows, the next time someone checks on it.

- Going live on more than one platform at once only counts as 1 stream (go-lives less than an hour apart are ignored).
- To count real days instead, set `StreamAge = false;`. The `Stage(...)` numbers then mean days.

**Colour:** a new Tamagotchi hatches in a random colour: Pink, Blue, Yellow, Green, Purple, Orange, Red, White, Black, Teal, Lilac, Rainbow, Glitter or See-through.

---

## The OBS overlay

Put the chat's Tamagotchi on your stream: a Tamagotchi with a pixel screen, in its own colour, with its health hearts across the top of the screen, and a small box underneath with its name, age and mood.

- It walks about, hops when it's happy, and grows a new look at each stage (Baby, Child, Teen, Adult, Senior).
- It shows what it needs, like a real one: a rice ball when it's hungry, Zzz when it's sleepy, a mess when it needs cleaning, a "!" when it's bored, and a skull when it's poorly.
- **Shells:** 10 shell shapes: Classic (with a keyring), Dinosaur (spikes and a tail), Yeti (fluffy fur and horns), Crochet (knitted, with a flower and a ball of yarn), Cat (ears and whiskers), Bunny, Bear, Frog, Alien and Crown. A new Tamagotchi hatches in a random one, and `!tamashell` changes it.
- `!tamastats` slides the screen to its needs, 4 hearts each, like a real Tamagotchi: Hunger and Happy, then Rest and Clean, then back to the Tamagotchi.
- When chat looks after it, it reacts straight away, with a speech bubble saying who did it, e.g. *"@Sam fed Pickle!"*: food drops in, it plays catch, it gets cleaned up, the lights go off for a nap, an egg hatches, it grows up, or it floats off to the Tamagotchi Planet.

The overlay is for the **chat's Tamagotchi**, so it needs `SharedTamagotchi = true;`. Only one is ever on screen.

**Setting it up:**

1. Download **`FFY-Tamagotchi-Overlay.html`** from this page and keep it somewhere safe.
2. **Switch on Streamer.bot's WebSocket Server:** **Servers/Clients** tab → **WebSocket Server**. Tick **Auto Start**, then click **Start Server**. The default is address `127.0.0.1`, port `8080`. Don't use `4455`: that's OBS's own WebSocket, which Streamer.bot uses to control OBS.
3. **In OBS:** add a **Browser** source, tick **Local file**, and pick `FFY-Tamagotchi-Overlay.html`. Set the width to **360** and the height to **590**.

That's it. It shows the chat's Tamagotchi straight away, and updates whenever chat uses a command.

**Different WebSocket settings?** Open `FFY-Tamagotchi-Overlay.html` in Notepad. The settings are at the top, between `SETTINGS` and `END OF SETTINGS`:

| Setting | What it does |
|---|---|
| `host: "127.0.0.1"` | The WebSocket Server's address in Streamer.bot. |
| `port: 8080` | The WebSocket Server's port in Streamer.bot. |
| `endpoint: "/"` | The WebSocket Server's endpoint in Streamer.bot. |
| `password: ""` | Only if you switched on **Authentication** for the WebSocket Server. Put the password between the quotes. |
| `showCard: true` | `false` hides the box with its name, age and mood, so only the Tamagotchi shows. |
| `showBubble: true` | `false` hides the speech bubble. |
| `bubbleSeconds: 6` | How long the speech bubble stays. |
| `scale: 1` | The size of the whole overlay, e.g. `1.5` for bigger. Change the Browser source's size to match. |
| `shell: "auto"` | `"auto"` = the shell chat picks with `!tamashell`. Or always use one, e.g. `shell: "Cat"`. |
| `refreshMinutes: 2` | How often it re-checks its needs while nobody uses a command. |

You can also add them to the end of the file's address instead, e.g. `FFY-Tamagotchi-Overlay.html?port=8081&scale=1.5`.

**Want to see it first?** Open the file in your web browser with `?demo=1` added to the end of the address. It plays through everything it can do without Streamer.bot. `?demo=shells` shows every shell.

---

## Switches

At the top of the settings. Set each one to `true` (on) or `false` (off):

| Switch | What it does |
|---|---|
| `SharedTamagotchi = false;` | `false` = every viewer hatches their own Tamagotchi. `true` = the whole chat shares one. |
| `OnlyModsNameChatTamagotchi = true;` | When it's shared: only mods (and you) can name it or change its colour. `false` = anyone can. |
| `StreamAge = true;` | `true` = age counts streams (1 more each time you go live). `false` = age counts real hours and days. |
| `Overlay = true;` | Sends the chat's Tamagotchi to the OBS overlay. `false` turns this off. |
| `OnlyWhileLive = true;` | `true` = needs and health only change while you're live, so it can't starve between streams. `false` = they change all the time, like a real Tamagotchi. |
| `AdoptFirst = true;` | A Tamagotchi must be hatched with `!tama` before the other commands work. `false` = any command hatches one. |
| `UserVariables = true;` | Shows the stats in Persisted User Globals. `false` turns this off. |

---

## Stats in Persisted User Globals

Every viewer's Tamagotchi is shown in Streamer.bot: **Global Variables** tab → **Persisted User Globals** → the platform (**Twitch**, **Kick** or **YouTube**) → their username.

| Variable | Can you change it? |
|---|---|
| **Tamagotchi Name** | Yes |
| **Tamagotchi Colour** | Yes, any colour you like |
| **Tamagotchi Shell** | Yes, one of the shells |
| **Tamagotchi Hunger**, **Happiness**, **Rest**, **Cleanliness** | Yes (0 to 100) |
| **Tamagotchi Health** | Yes (0 to 100) |
| **Tamagotchi Care Points** | Yes |
| **Tamagotchi Stage**, **Age**, **Mood** | No, these are just shown for you |
| **Tamagotchi Pet ID** | No, leave this alone. It tells the game which Tamagotchi the stats belong to |

Change a value and the Tamagotchi picks it up the next time that viewer uses a command, e.g. set **Tamagotchi Health** to 100 to nurse a poorly Tamagotchi back to health.

---

## Changing it

**Actions tab** → **FFY Tamagotchi** group → **FFY Tamagotchi** → double-click **Execute C# Code**. Everything is between `EDIT BELOW` and `EDIT ABOVE`. Click **Save and Compile** after changing anything.

| Setting | What it does |
|---|---|
| `HungerPerHour`, `HappinessPerHour`, `RestPerHour`, `CleanlinessPerHour` | How fast each need drops, per hour. Lower them for a more relaxed Tamagotchi. |
| `HealthLossPerHour = 3;` | How fast health drops while it's starving or filthy. |
| `HealthGainPerHour = 2;` | How fast health recovers when it's looked after. |
| `FeedAmount`, `PlayAmount`, `SleepAmount`, `VisitAmount` | How much each command helps. |
| `CareCooldownMinutes = 10;` | The wait between feeds, plays and cleans. |
| `SleepCooldownMinutes = 120;` | The wait between naps. |
| `VisitsPerDay = 3;` | How many Tamagotchis each viewer can visit a day. |
| `Stage("name", number)` lines | The growth stages, and how many streams old (or days, with `StreamAge = false;`) it must be for each. |
| `PetNames(...)` | The names a new Tamagotchi can hatch with. |
| `Foods(...)` | What it can be fed. |
| `Games(...)` | The games you can play with it. |
| `Colours(...)` | The colours it can be. |
| `Shells(...)` | The shells it can have on the overlay. Remove any you don't want. |
| `NeedMood("need", below, "name", "action")` lines | The moods for each need, e.g. `NeedMood("hunger", 30, "Hungry", "*stares at the fridge*")` = Hungry when Hunger drops below 30. |
| `Mood(above, "name", "action")` lines | The moods when nothing is urgent, and how high its needs must be on average for each. |
| `SickMood("name", "action")` | The mood when its health is below 50. |
| `MoodsShown = 2;` | How many moods chat sees at once. |
| The `Message("...", "...")` lines | Every message chat sees. Change the wording, but keep the `{...}` words. |

---

## Good to know

- Everything is saved in the **Global Variables** tab as `ffy.tamagotchi`. Deleting it removes every Tamagotchi.
- **Importing again** (to update) keeps every Tamagotchi, but the settings go back to the defaults, so set your switches again.
- **Stop spam:** give `!tama` and `!tamatop` a cooldown in the **Commands** tab.

---

## Troubleshooting

- **No reply:** check the commands are switched on in the **Commands** tab, in the **FFY Tamagotchi** folder.
- **The overlay says it can't reach Streamer.bot:** check the WebSocket Server is started (**Servers/Clients** tab → **WebSocket Server**), and that the port matches the overlay's settings.
- **The overlay says "Not shared":** set `SharedTamagotchi = true;`. The overlay only shows the chat's Tamagotchi.
- **The overlay doesn't change when chat uses a command:** check `Overlay = true;`, then right-click the Browser source in OBS and click **Refresh**.
- **It isn't getting older, or its needs never drop:** check the **FFY Tamagotchi** action has its **Stream Online** and **Stream Offline** triggers (Twitch, Kick and YouTube) in the **Actions** tab.
- **If Streamer.bot was closed when you ended a stream:** a stream counts for at most 12 hours, so the Tamagotchi won't starve over the following days.
- **"Save and Compile" error:** look for a missing `"`, `,` or `;` on the line it mentions.
