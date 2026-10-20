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
- Only mods (and you) can name it or change its colour. Set `OnlyModsNameChatTamagotchi = false;` to let anyone.
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
| `!tamavisit @Sam` | Visits someone else's Tamagotchi and plays with it, making it happier. 3 visits a day. |
| `!tamatop` | The 5 oldest Tamagotchis in chat. |
| `!tamahelp` | Lists the commands in chat. |

Feeding, playing and cleaning each have a 10 minute wait, so chat can't spam them.

---

## How it works

**Needs:** Hunger, Happiness, Rest and Cleanliness go from 0 to 100, and slowly drop every hour, even when you're offline:

| Need | Drops by | Goes up with |
|---|---|---|
| Hunger | 6 an hour | `!tamafeed` (+35) |
| Happiness | 4 an hour | `!tamaplay` (+30), feeding and cleaning (+5), visits (+15) |
| Rest | 3 an hour | `!tamasleep` (+60) |
| Cleanliness | 3 an hour | `!tamaclean` (back to 100) |

**Health:** while it's starving (Hunger 0) or filthy (Cleanliness 0), its health drops by 3 an hour. Otherwise it slowly recovers. If health reaches 0, it goes back to the Tamagotchi Planet, and the next `!tama` hatches a new egg. A Tamagotchi left alone completely lasts about 3 to 4 days.

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

## Switches

At the top of the settings. Set each one to `true` (on) or `false` (off):

| Switch | What it does |
|---|---|
| `SharedTamagotchi = false;` | `false` = every viewer hatches their own Tamagotchi. `true` = the whole chat shares one. |
| `OnlyModsNameChatTamagotchi = true;` | When it's shared: only mods (and you) can name it or change its colour. `false` = anyone can. |
| `StreamAge = true;` | `true` = age counts streams (1 more each time you go live). `false` = age counts real hours and days. |
| `AdoptFirst = true;` | A Tamagotchi must be hatched with `!tama` before the other commands work. `false` = any command hatches one. |
| `UserVariables = true;` | Shows the stats in Persisted User Globals. `false` turns this off. |

---

## Stats in Persisted User Globals

Every viewer's Tamagotchi is shown in Streamer.bot: **Global Variables** tab → **Persisted User Globals** → the platform (**Twitch**, **Kick** or **YouTube**) → their username.

| Variable | Can you change it? |
|---|---|
| **Tamagotchi Name** | Yes |
| **Tamagotchi Colour** | Yes, any colour you like |
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
- **It isn't getting older:** check the **FFY Tamagotchi** action has its **Stream Online** triggers (Twitch, Kick and YouTube) in the **Actions** tab.
- **"Save and Compile" error:** look for a missing `"`, `,` or `;` on the line it mentions.
