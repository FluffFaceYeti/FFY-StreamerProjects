# FFY Tamagotchi

Remember Tamagotchis? This puts one in your chat. Every viewer can hatch their own, or the whole chat can share one. Feed it, play with it, clean up after it and let it nap, and it grows up a little bit every time you go live. Neglect it and it might head back to the Tamagotchi Planet...

```
Bob: !tama Pickle
Chat: @Bob got a Tamagotchi! An egg wobbled, cracked, and out popped Pickle! Type !tamafeed, !tamaplay, !tamaclean and !tamasleep to look after it.
Chat: @Bob's Pink Pickle (Baby, brand new) | Hunger 80 | Happiness 80 | Rest 80 | Clean 80 | Health 100 | Mood: Over the moon *does a happy little dance*
Bob: !tamafeed
Chat: @Bob fed Pickle a dumpling! *munch munch* Hunger 100/100.
Bob: !tamacolour glitter
Chat: @Bob's Pickle is now Glitter! It's admiring itself in the mirror.
```

Just like the real thing, it lets chat know when it's Hungry, Sleepy, Messy, Bored or Poorly. Its age goes up with your streams, and it grows from a Baby all the way to a Senior.

There's an animated OBS overlay too. It shows the chat's Tamagotchi on screen and reacts as soon as someone looks after it.

You don't need FFY Commands, and it works on Twitch, Kick and YouTube.

## Installing

Download the **`FFY-Tamagotchi`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

The commands are switched on already, and so are the Stream Online triggers for Twitch, Kick and YouTube. Someone needs to hatch a Tamagotchi with `!tama` first. Until they do, the other commands just explain how.

## Two ways to play

### Everyone has their own (`SharedTamagotchi = false;`)

Each viewer hatches their own with `!tama` and looks after it themselves. They can drop in on each other's with `!tamavisit @Sam`.

### One for the whole chat (`SharedTamagotchi = true;`)

Chat shares a single Tamagotchi and looks after it together:

```
Mia: !tama Pickle
Chat: @Mia found an egg for the whole chat! It wobbled, cracked, and out popped Pickle! Everyone can !tamafeed, !tamaplay, !tamaclean and !tamasleep to look after it.
Sam: !tamafeed
Chat: @Sam fed Pickle a dumpling! *munch munch* Hunger 100/100.
```

The waits on feeding, playing and cleaning are shared as well. Once someone's fed it, nobody else can until the wait's up.

Only you and your mods can name it or change its colour and shell, unless you set `OnlyModsNameChatTamagotchi = false;`, which lets anyone do it.

In this mode `!tamatop` just shows the chat's Tamagotchi, and `!tamavisit` isn't used. Its stats show up under **your** username in Persisted User Globals.

You can switch between the two modes whenever you like without losing anything. Viewers' own Tamagotchis and the chat's one are saved separately.

## Commands

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

There's a 10 minute wait on feeding, playing and cleaning, so chat can't just spam them.

## How it works

### Needs

It has four needs: Hunger, Happiness, Rest and Cleanliness. Each goes from 0 to 100 and drops a little every hour you're **live**. When you go offline it freezes, and picks up where it left off next time you stream. If you'd rather they drop all the time, set `OnlyWhileLive = false;`.

| Need | Drops by | Goes up with |
|---|---|---|
| Hunger | 6 an hour | `!tamafeed` (+35) |
| Happiness | 4 an hour | `!tamaplay` (+30), feeding and cleaning (+5), visits (+15) |
| Rest | 3 an hour | `!tamasleep` (+60) |
| Cleanliness | 3 an hour | `!tamaclean` (back to 100) |

### Health

If it's starving (Hunger at 0) or filthy (Cleanliness at 0), it loses 3 health an hour. The rest of the time it slowly gets better. If its health hits 0, it goes back to the Tamagotchi Planet and the next `!tama` hatches a fresh egg. Left completely on its own, one lasts about 40 hours of streaming.

### Mood

Like a real one, it tells you what it needs. Chat sees its two most urgent moods, worst first, and what it's up to, e.g. *Mood: Exhausted and Hungry \*can barely keep its eyes open\**.

| Mood | When |
|---|---|
| Poorly *\*sniffle sniffle\** | Health below 50 |
| Starving / Hungry | Hunger below 10 / below 30 |
| Exhausted / Sleepy | Rest below 10 / below 30 |
| Stinky / Messy | Cleanliness below 10 / below 30 |
| Lonely / Bored | Happiness below 10 / below 30 |
| Over the moon, Happy, Grumpy or Miserable | Nothing urgent. It depends on how well looked after it is overall |

### Growing up

Its age is counted in streams. Every time you go live on Twitch, Kick or YouTube, every Tamagotchi gets 1 stream older, e.g. *"Pickle (Child, 3 streams old)"*. A newly hatched one is *brand new*.

It goes from Baby to Child at 1 stream, Teen at 3, Adult at 6 and Senior at 14. The next time someone checks on it after it grows, chat gets a message.

Going live on a few platforms at once only counts as 1 stream, because go-lives less than an hour apart are ignored. If you'd prefer it to age in real days, set `StreamAge = false;` and the `Stage(...)` numbers will mean days instead.

### Colours

A new Tamagotchi hatches in a random colour: Pink, Blue, Yellow, Green, Purple, Orange, Red, White, Black, Teal, Lilac, Rainbow, Glitter or See-through.

## The OBS overlay

This puts the chat's Tamagotchi on your stream. It's a Tamagotchi with a little pixel screen, in its own colour, with health hearts along the top and a small box underneath showing its name, age and mood.

It wanders around, hops when it's happy and gets a new look at every stage (Baby, Child, Teen, Adult, Senior). It shows what it needs the same way a real one does: a rice ball when it's hungry, Zzz when it's sleepy, a mess when it needs cleaning, a "!" when it's bored, and a skull when it's poorly.

There are 10 shells to choose from: Classic (with a keyring), Dinosaur (spikes and a tail), Yeti (fluffy fur and horns), Crochet (knitted, with a flower and a ball of yarn), Cat (ears and whiskers), Bunny, Bear, Frog, Alien and Crown. A new one hatches in a random shell, and `!tamashell` changes it.

`!tamastats` slides the screen over to its needs, 4 hearts each like a real Tamagotchi. It shows Hunger and Happy first, then Rest and Clean, then goes back to the Tamagotchi.

Whenever chat looks after it, it reacts straight away, with a speech bubble saying who did it, like *"@Sam fed Pickle!"*. Food drops in, it plays catch, it gets cleaned up, the lights go off for a nap. You'll also see eggs hatching, it growing up, or it floating off to the Tamagotchi Planet.

The overlay only shows the **chat's** Tamagotchi, so you need `SharedTamagotchi = true;`. There's only ever one on screen.

### Setting up the overlay

1. Download **`FFY-Tamagotchi-Overlay.html`** from this page and put it somewhere you won't lose it.
2. Turn on Streamer.bot's WebSocket Server. Go to the **Servers/Clients** tab, then **WebSocket Server**, tick **Auto Start** and click **Start Server**. By default it's address `127.0.0.1` and port `8080`. Don't use `4455`, because that's OBS's own WebSocket, which Streamer.bot uses to control OBS.
3. In OBS, add a **Browser** source, tick **Local file** and choose `FFY-Tamagotchi-Overlay.html`. Set the width to **360** and the height to **590**.

That's it. The chat's Tamagotchi shows up straight away and updates whenever someone uses a command.

If your WebSocket settings are different, open `FFY-Tamagotchi-Overlay.html` in Notepad. The settings are at the top, between `SETTINGS` and `END OF SETTINGS`:

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

You can also stick them on the end of the file's address instead, like `FFY-Tamagotchi-Overlay.html?port=8081&scale=1.5`.

Want a look before setting it up? Open the file in your browser with `?demo=1` on the end of the address and it'll play through everything it can do, no Streamer.bot needed. `?demo=shells` shows all the shells.

## Switches

These are at the top of the settings. Set each to `true` (on) or `false` (off):

| Switch | What it does |
|---|---|
| `SharedTamagotchi = false;` | `false` = every viewer hatches their own Tamagotchi. `true` = the whole chat shares one. |
| `OnlyModsNameChatTamagotchi = true;` | When it's shared: only mods (and you) can name it or change its colour. `false` = anyone can. |
| `StreamAge = true;` | `true` = age counts streams (1 more each time you go live). `false` = age counts real hours and days. |
| `Overlay = true;` | Sends the chat's Tamagotchi to the OBS overlay. `false` turns this off. |
| `OnlyWhileLive = true;` | `true` = needs and health only change while you're live, so it can't starve between streams. `false` = they change all the time, like a real Tamagotchi. |
| `AdoptFirst = true;` | A Tamagotchi must be hatched with `!tama` before the other commands work. `false` = any command hatches one. |
| `UserVariables = true;` | Shows the stats in Persisted User Globals. `false` turns this off. |

## Stats in Persisted User Globals

You can see everyone's Tamagotchi in Streamer.bot. Go to the **Global Variables** tab, then **Persisted User Globals**, then the platform (**Twitch**, **Kick** or **YouTube**), then their username.

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

If you change a value, the Tamagotchi picks it up next time that viewer uses a command. Setting **Tamagotchi Health** to 100 is a handy way to nurse a poorly one back to health.

## Changing other things

In the **Actions** tab, open the **FFY Tamagotchi** group, then the **FFY Tamagotchi** action, and double-click **Execute C# Code**. Everything's between `EDIT BELOW` and `EDIT ABOVE`. Click **Save and Compile** when you've finished.

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

## Worth knowing

Everything's saved in the **Global Variables** tab as `ffy.tamagotchi`. Delete that and every Tamagotchi goes with it.

When you import again to update, all the Tamagotchis are kept but the settings go back to default, so you'll need to set your switches again.

If `!tama` or `!tamatop` get spammed, give them a cooldown in the **Commands** tab.

## If something's not working

**No reply:** check the commands are switched on in the **FFY Tamagotchi** folder in the **Commands** tab.

**The overlay says it can't reach Streamer.bot:** make sure the WebSocket Server is started (**Servers/Clients** tab → **WebSocket Server**) and the port matches the overlay's settings.

**The overlay says "Not shared":** set `SharedTamagotchi = true;`. The overlay only shows the chat's Tamagotchi.

**The overlay doesn't change when chat uses a command:** check `Overlay = true;`, then right-click the Browser source in OBS and click **Refresh**.

**It's not getting older, or its needs never go down:** check the **FFY Tamagotchi** action in the **Actions** tab has its **Stream Online** and **Stream Offline** triggers (Twitch, Kick and YouTube).

**Streamer.bot was closed when you ended a stream:** don't worry. A stream never counts for more than 12 hours, so it won't starve over the next few days.

**Save and Compile error:** look for a missing `"`, `,` or `;` on the line it mentions.
