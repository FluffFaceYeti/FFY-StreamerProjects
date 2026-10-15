# FFY Pets

Pets for your chat: dogs, cats, chickens, goats, llamas and more. Either the whole chat looks after the chat's pet together, or every viewer adopts their own. Feed them, walk them, play with them, teach them tricks, and watch the bond grow.

```
Bob: !feedpet
Chat: Woof! @Bob fed Biscuit a sausage! Biscuit gobbled it all up.
Sam: !feedpet
Chat: Biscuit has already been fed today! (by @Bob) Come back tomorrow!
Sam: !trainpet
Chat: Woof! Biscuit learned a new trick: roll over! Thanks to @Sam's training.
Ann: !pettrick
Chat: @Ann asked Biscuit to roll over... and it did! Woof!
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- 27 kinds of pet, from dogs and cats to Highland Cows, Mooshrooms and a Baby Dragon, each with its own sound, food, tricks, walks and play.

---

## Installing

1. Download the **`FFY-Pets`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Before anything else, a pet has to be adopted with `!registerpet`, e.g. `!registerpet Biscuit dog`. Until then, the other commands tell chat how.

---

## Two ways to play

### The chat's pet (`SharedPet = true;`)

The whole chat looks after the chat's pets together. **A mod or you adopts the chat's pet first**, e.g. `!registerpet Biscuit dog`. Then each pet can be fed, walked, played with and trained once a day, by anyone. Whoever gets there first does it, and everyone else sees *"Biscuit has already been fed today! (by @Bob)"*.

With more than one chat pet (see `PetAmount`), `!feedpet` feeds whichever pet is still hungry. When they're all done, chat sees *"All the pets have been fed!"*.

**Changing the chat's pet:** a mod types `!releasepet Biscuit`, then adopts the new one, e.g. `!registerpet Clucky chicken`.

### Everyone has their own (`SharedPet = false;`)

Every viewer adopts their own pet with `!registerpet`, then looks after it themselves:

```
!registerpet Biscuit dog
!registerpet Lady Clucksworth chicken
```

Leave the kind off and they get a surprise one. `PetAmount` sets how many pets each viewer can have. To swap a pet, they `!releasepet` it first, then adopt a new one.

---

## The commands

| Command | What it does |
|---|---|
| `!pet` | Shows the pet's name, kind, bond, tricks and what it's had today. In own-pet mode, `!pet @Sam` shows Sam's pets. |
| `!feedpet` | Feeds the pet. Once a day. |
| `!walkpet` | Takes the pet for a walk. Once a day. |
| `!playpet` | Plays with the pet. Once a day. |
| `!trainpet` | Trains the pet. Every few sessions it learns a new trick. Once a day. |
| `!pettrick` | Asks the pet to show off one of its tricks. |
| `!cuddlepet` | Gives the pet a cuddle, any time (with a short wait between cuddles). |
| `!registerpet` *name kind* | Adopts a pet, e.g. `!registerpet Biscuit dog`. **Needed before anything else.** For the chat's pets, only mods can do this. |
| `!renamepet` *name* | Renames the pet. For the chat's pets, only mods can do this. |
| `!releasepet` *name* | Finds a pet a lovely new home, to make room for a different one. For the chat's pets, only mods can do this. |
| `!pettop` | Chat's pets: who's looked after them the most. Own pets: the most bonded pets in chat. |
| `!pethelp` | Lists the commands in chat. |

**More than one pet?** Add the pet's name to pick which one, e.g. `!feedpet Nugget`, `!pettrick Biscuit` or `!renamepet Biscuit Sir Biscuit`.

---

## The pets

| Kind | Sound | Example trick |
|---|---|---|
| Dog | Woof! | roll over |
| Cat | Meow! | ignore you on purpose |
| Chicken | Bawk bawk! | cross the road |
| Hamster | Squeak! | stuff its cheeks |
| Goat | Meeeh! | eat a whole bush |
| Duck | Quack! | waddle in a line |
| Parrot | SQUAWK! Pretty bird! | copy the doorbell |
| Pig | Oink oink! | find truffles |
| Snake | Hissss! | hide in a boot |
| Llama | Mmmmm! | spit on command (gross) |
| Fox | Ring-ding-ding! | do the fox scream |
| Owl | Hoo hoo! | turn its head all the way round |
| Penguin | Honk honk! | slide on its belly |
| Cow | Moooo! | ring its cow bell |
| Highland Cow | Mooooo! (but fluffier) | flick its fringe |
| Mini Cow | Moo! (a tiny one) | fit in a basket |
| Mooshroom | Moo! *mushrooms wobble* | fill a bowl with stew |
| Minecraft Cow | *blocky moo* | walk into a fence |
| Pygmy Goat | Meh! (a small one) | climb on your back |
| Capybara | *calm squeak* | let a bird ride on its head |
| Red Panda | *happy squeak* | stand up tall to look scary |
| Axolotl | *blub blub* | regrow a leg |
| Hedgehog | *snuffle snuffle* | roll into a ball |
| Bunny | *nose wiggle* | do a binky jump |
| Sloth | *slow yawn* | move one inch |
| Frog | Ribbit! | catch a fly with its tongue |
| Baby Dragon | *tiny roar* | roast a marshmallow |

Each kind has its own walk and play too. A cat refuses its lead, a goat climbs on top of a car, and a sloth takes three hours to reach the gate.

**Two-word kinds** work too: `!registerpet Bessie highland cow`, `!registerpet Steve minecraft cow` or `!registerpet Toast baby dragon`.

**Bond:** every bit of care earns the pet XP, and every 1,000 XP its bond grows: Stranger, Acquaintance, Buddy, Good Friend, Best Friend, Inseparable and finally Soulmate. Chat sees a message each time.

---

## Switches

At the top of the settings. Set each one to `true` (on) or `false` (off), or a number where shown:

| Switch | What it does |
|---|---|
| `SharedPet = true;` | `true` = the chat shares its pets. `false` = every viewer adopts their own with `!registerpet`. |
| `PetAmount = 1;` | Shared: how many pets the chat has. Own: how many pets each viewer can adopt. |
| `AllowFeeding = true;` | Switches `!feedpet` on or off. |
| `AllowWalks = true;` | Switches `!walkpet` on or off. |
| `AllowPlaying = true;` | Switches `!playpet` on or off. |
| `AllowTraining = true;` | Switches `!trainpet` and `!pettrick` on or off. |
| `AllowCuddles = true;` | Switches `!cuddlepet` on or off. |
| `OncePerDay = true;` | `true` = feeding, walks, play and training reset at midnight. `false` = they use `CareCooldownMinutes` instead. |
| `CareCooldownMinutes = 120;` | The wait between feeds (and so on) when `OncePerDay = false`. |
| `ShowWhoDidIt = true;` | Adds *"(by @Bob)"* when a pet has already been looked after. |
| `AnnounceBondLevels = true;` | Chat sees a message when a pet's bond grows. |
| `AllowRelease = true;` | Pets can be given up with `!releasepet`, to make room for a different one. |
| `OnlyModsManageChatPets = true;` | Only mods can adopt, rename or release the chat's pets. `false` = anyone can. |

---

## Changing it

**Actions tab** → **FFY Pets** group → **FFY Pets** → double-click **Execute C# Code**. Everything is between `EDIT BELOW` and `EDIT ABOVE`. Click **Save and Compile** after changing anything.

| Setting | What it does |
|---|---|
| `CuddleCooldownSeconds = 60;` | The wait between cuddles, for each viewer. |
| `TrainingsPerTrick = 3;` | Training sessions needed to learn each new trick. |
| `FeedXp`, `WalkXp`, `PlayXp`, `TrainXp`, `CuddleXp`, `XpPerLevel` | How much bond each kind of care gives, and how much XP each bond level needs. |
| `Bonds(...)` | The bond level names, in order. |
| `Kind(...)` lines | The pets: `Kind("name", "sound", "foods", "tricks", "walk", "play")`. Split lists with `\|`. In the walk and play lines, `{pet}` is the pet's name. |
| The `Message("...", "...")` lines | Every message chat sees. Change the wording, but keep the `{...}` words. |

**Adding a new kind of pet:**

```csharp
Kind("Penguin", "Honk!", "a fish|a bucket of sardines|a squid",
    "slide on its belly|waddle|flap its wings|dive for fish",
    "{pet} slid all the way to the shops on its belly!",
    "{pet} played in the snow and threw snowballs with its flippers!");
```

---

## Good to know

- Everything is saved in the **Global Variables** tab as `ffy.pets`. Deleting it starts everyone's pets from scratch.
- **Changing modes** keeps both sets of pets. The chat's pets and viewers' own pets are saved separately.
- **Updating from the first version?** It gave the chat Biscuit the Dog automatically. To swap Biscuit for a different pet, a mod types `!releasepet Biscuit`, then `!registerpet` with the new name and kind.
- **"Today"** follows your PC's clock and resets at midnight.
- **Stop spam:** give `!pet` and `!pettop` a cooldown in the **Commands** tab.

---

## Troubleshooting

- **No reply:** check the commands are switched on in the **Commands** tab, in the **FFY Pets** folder.
- **"That's switched off right now":** one of the `Allow...` switches is set to `false`.
- **"Save and Compile" error:** look for a missing `"`, `,` or `;` on the line it mentions.
