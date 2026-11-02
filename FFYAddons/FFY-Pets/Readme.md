# FFY Pets

Give your chat some pets to look after. Dogs, cats, chickens, goats, llamas and a load more. You can have one set of pets the whole chat shares, or let every viewer adopt their own. They get fed, walked, played with and taught tricks, and the bond grows the more they're looked after.

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

There are 27 kinds of pet, from dogs and cats up to Highland Cows, Mooshrooms and a Baby Dragon. Every kind has its own sound, food, tricks, walks and games.

It doesn't need FFY Commands, and it works on Twitch, Kick and YouTube.

## Installing

Download the **`FFY-Pets`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

The commands are already switched on, but nothing happens until a pet's been adopted. Do that with `!registerpet`, e.g. `!registerpet Biscuit dog`. Until then, the other commands will just tell chat how.

## Two ways to play

### One set of pets for the whole chat (`SharedPet = true;`)

Chat looks after the pets together. First, you or a mod adopts the chat's pet, e.g. `!registerpet Biscuit dog`. After that, anyone can feed, walk, play with or train each pet, once a day each. Whoever's quickest gets to do it, and everyone after them sees *"Biscuit has already been fed today! (by @Bob)"*.

If chat has more than one pet (that's `PetAmount`), `!feedpet` feeds whichever one's still hungry. Once they've all eaten, chat sees *"All the pets have been fed!"*.

To swap the chat's pet for a different one, a mod types `!releasepet Biscuit` and then adopts the new one, like `!registerpet Clucky chicken`.

### Everyone gets their own (`SharedPet = false;`)

Each viewer adopts their own pet with `!registerpet` and looks after it themselves:

```
!registerpet Biscuit dog
!registerpet Lady Clucksworth chicken
```

If they leave the kind off, they get a surprise. `PetAmount` sets how many pets each viewer is allowed. To swap one, they `!releasepet` it first and then adopt another.

## Commands

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

If there's more than one pet, add its name to say which one you mean, like `!feedpet Nugget`, `!pettrick Biscuit` or `!renamepet Biscuit Sir Biscuit`.

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

They all have their own walks and games as well. The cat refuses to wear its lead, the goat ends up on top of a car, and the sloth takes three hours to get to the gate.

Kinds with two words work fine: `!registerpet Bessie highland cow`, `!registerpet Steve minecraft cow` or `!registerpet Toast baby dragon`.

Every bit of care gives the pet some XP, and every 1,000 XP its bond goes up a level: Stranger, Acquaintance, Buddy, Good Friend, Best Friend, Inseparable and finally Soulmate. Chat gets a message each time it levels up.

## Switches

These are at the top of the settings. Set them to `true` (on) or `false` (off), or a number where it says so:

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

## Changing other things

In the **Actions** tab, open the **FFY Pets** group, then the **FFY Pets** action, and double-click **Execute C# Code**. It's all between `EDIT BELOW` and `EDIT ABOVE`. Click **Save and Compile** after you change anything.

| Setting | What it does |
|---|---|
| `CuddleCooldownSeconds = 60;` | The wait between cuddles, for each viewer. |
| `TrainingsPerTrick = 3;` | Training sessions needed to learn each new trick. |
| `FeedXp`, `WalkXp`, `PlayXp`, `TrainXp`, `CuddleXp`, `XpPerLevel` | How much bond each kind of care gives, and how much XP each bond level needs. |
| `Bonds(...)` | The bond level names, in order. |
| `Kind(...)` lines | The pets: `Kind("name", "sound", "foods", "tricks", "walk", "play")`. Split lists with `\|`. In the walk and play lines, `{pet}` is the pet's name. |
| The `Message("...", "...")` lines | Every message chat sees. Change the wording, but keep the `{...}` words. |

Here's what a new kind of pet looks like:

```csharp
Kind("Penguin", "Honk!", "a fish|a bucket of sardines|a squid",
    "slide on its belly|waddle|flap its wings|dive for fish",
    "{pet} slid all the way to the shops on its belly!",
    "{pet} played in the snow and threw snowballs with its flippers!");
```

## Worth knowing

Everything's saved in the **Global Variables** tab as `ffy.pets`. If you delete it, everyone's pets start again from scratch.

Switching between the two modes won't lose anything. The chat's pets and everyone's own pets are saved separately.

If you're updating from the very first version, that one gave chat Biscuit the Dog automatically. To swap Biscuit for something else, a mod types `!releasepet Biscuit` and then `!registerpet` with the new name and kind.

"Today" goes by your PC's clock and resets at midnight.

If `!pet` or `!pettop` get spammed, give them a cooldown in the **Commands** tab.

## If something's not working

**No reply:** check the commands are switched on in the **FFY Pets** folder in the **Commands** tab.

**"That's switched off right now":** one of the `Allow...` switches is set to `false`.

**Save and Compile error:** look for a missing `"`, `,` or `;` on the line it mentions.
