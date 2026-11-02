# FFY Commands for Streamer.bot

A big bundle of daft chat commands for your stream. `!pp`, `!beard`, `!drink`, `!hug @someone`, duels, dice, leaderboards, "Daddy of the Day"... 200 of them in total.

It works on Twitch, Kick and YouTube, and it all runs inside Streamer.bot (version 1.0 or newer). There are no websites, servers or extra programs. You can change any reply or add your own commands by copying a few lines and editing them.

You don't need to know how to code. I'll show you exactly where to click.

> If you want every last detail, the **[Complete Guide (QuickGuide.md)](QuickGuide.md)** goes into everything properly, with loads of copy-and-paste examples and a list of all 200 commands.

## Contents

**Getting started**
1. [Install it](#1-install-it)
2. [Two things to set first](#2-two-things-to-set-first)
3. [Finding your way around](#3-finding-your-way-around)
4. [How to change something (the basics)](#4-how-to-change-something-the-basics)

**Adding your own stuff**
5. [Make Streamer.bot listen for a new command](#5-make-streamerbot-listen-for-a-new-command) (every new command needs this)
6. [Add a number command](#6-add-a-number-command) (like `!pp`)
7. [Add a list command](#7-add-a-list-command) (like `!drink`)
8. [Add an interaction](#8-add-an-interaction) (like `!hug @someone`)
9. [Add an "of the Day" title](#9-add-an-of-the-day-title) (like Daddy of the Day)
10. [Give a viewer their own special reply](#10-give-a-viewer-their-own-special-reply)
11. [More things you can add](#11-more-things-you-can-add) (countdowns, dice, duels, reply commands, add-ons)

**Settings and help**
12. [Switch things on and off](#12-switch-things-on-and-off)
13. [Other settings](#13-other-settings)
14. [Something isn't working](#14-something-isnt-working)
15. [Good to know](#15-good-to-know)

# Getting started

## 1. Install it

There are two parts to it. **FFY Commands** itself (the `FFYCommands` file) is the "brain". It holds your settings and `!leaderboard`, and everyone needs it, so it goes in first. The commands themselves come in **packs** grouped by theme, like **FFY Stats**, **FFY Interactions** or **FFY Games**, and you only install the ones you want.

### Step 1: install FFY Commands

1. Download the **`FFYCommands`** file from this page. This is the file for a first install. Updates use a different one, which I'll get to below.
2. Open **Streamer.bot**.
3. Click **Import** in the bar at the top.
4. Drag the file into the box.
5. Click **Import**.

### Step 2: install the packs you want

Go into the **[Packs](Packs/Readme.md)** folder, open a pack, download its file (e.g. **`FFY-Stats`**) and import it the same way. Repeat for as many packs as you like, in whatever order.

| Pack | What's in it |
|---|---|
| **[FFY Interactions](Packs/FFY-Interactions/Readme.md)** (14) | Hug, slap, boop and more with `!hug @someone`. Includes consent (`!accept` / `!deny`) and `!top`. |
| **[FFY Games](Packs/FFY-Games/Readme.md)** (16) | Duels, dice, rock-paper-scissors, tug of war and more. |
| **[FFY Stats](Packs/FFY-Stats/Readme.md)** (29) | Beard, PP, daddy, mommy, sigma, brainrot and more, plus their "of the Day" titles. |
| **[FFY Personality](Packs/FFY-Personality/Readme.md)** (31) | Rizz, sass, chaos, main character energy and more. |
| **[FFY Emotions](Packs/FFY-Emotions/Readme.md)** (20) | Happiness, anger, caffeine, hangry and more. |
| **[FFY Skills](Packs/FFY-Skills/Readme.md)** (15) | Aim, stealth, cooking, flirting and more. |
| **[FFY Actions](Packs/FFY-Actions/Readme.md)** (17) | Punch, kickflip, uppercut, dodge and more. |
| **[FFY Gym](Packs/FFY-Gym/Readme.md)** (8) | Lift, deadlift, bench press, sprint and more. |
| **[FFY Carry](Packs/FFY-Carry/Readme.md)** (3) | Carry weight, items and gold. |
| **[FFY Pirate](Packs/FFY-Pirate/Readme.md)** (18) | Pirate skills, outfits, sails and kegs, plus Pirate and Captain of the Day. |
| **[FFY Sea of Thieves](Packs/FFY-Sea-of-Thieves/Readme.md)** (12) | Sea of Thieves reputations and skills, plus the `!sotfest` countdown. |
| **[FFY Picks](Packs/FFY-Picks/Readme.md)** (10) | A random pick for the day: animal, drink, colour, fish, outfit, power and element. |
| **[FFY Magic](Packs/FFY-Magic/Readme.md)** (6) | Auras, elemental items, wizard items, patronus and more. |

A pack's commands switch on as soon as you import it. Try typing `!beard` in chat (that one's in FFY Stats).

To turn a single command on or off, go to the **Commands** tab, open its folder (e.g. **FFY Stats**), click the command (e.g. **!beard**) and tick or untick **Enabled**. If you want to switch every FFY command on or off in one go, go to the **Actions** tab, open the **FFY Core** group, right-click **FFY Enable All Commands** (or **FFY Disable All Commands**) and pick **Run Now**.

### Updating later

When there's a new version, download the **`FFYCommands-update`** file and import it over the top, the same way as before. You don't need to delete anything first. It keeps your settings (FFY Config, FFY Switches), special users and interactions, Single Values, Do Not Track, Of The Day, Countdowns, your **FFY My ...** actions and your commands.

What it *does* replace is anything you changed inside the built-in actions, like FFY Stats. So put your own changes in the **FFY My** actions instead. [Section 21 of the Complete Guide](QuickGuide.md#21-keeping-your-changes-safe-from-updates) explains how.

If you're coming from version 1 (before there were packs), import `FFYCommands-update` and then import the packs you use. Their commands won't reply until you've done that. Your settings and **FFY My** actions are kept.

To update a pack, just import its file again over the top. Bear in mind this switches all its commands back on and resets their cooldowns and permissions, so only bother when the pack has actually changed.

I'd really recommend making a backup before you update. Click **Export** in Streamer.bot's top bar, tick every action that starts with **FFY**, and save the export text in a Notepad file. If anything of yours goes missing after the update, you can copy your lines back out of it, or import the backup to put those actions back exactly how they were. [There's more on that here](QuickGuide.md#before-you-update-make-a-backup-recommended).

## 2. Two things to set first

### Your channel name

This makes your viewers' daily results unique to your channel.

1. Go to the **Actions** tab.
2. Find the **FFY Helpers** group and click the little arrow to open it.
3. Click **FFY Config**.
4. On the right, under **Sub-Actions**, double-click **Execute C# Code**. A window full of code will open.
5. Find this line:
   ```csharp
   Set("channelName", "");
   ```
6. Type your channel name between the two quote marks:
   ```csharp
   Set("channelName", "YourChannelName");
   ```
7. Click **Save and Compile** at the bottom, then close the window.

### Your on/off switches

These are in **FFY Switches**, in the same **FFY Helpers** group. Open it the same way (steps 3 to 7 above). Every switch has a line above it saying what it does. Set it to `true` (on) or `false` (off) and click **Save and Compile**. [Section 12](#12-switch-things-on-and-off) has more on them.

## 3. Finding your way around

Everything you need is in two tabs in Streamer.bot.

### The Commands tab

This is your list of chat commands (`!pp`, `!drink`, `!hug` and so on), with a folder for each pack:

| Folder | What's in it |
|---|---|
| FFY Interactions | Hug, slap, boop and more with `!hug @someone`. Includes consent (`!accept` / `!deny`) and `!top`. |
| FFY Games | Duels, dice, rock-paper-scissors, tug of war and more. |
| FFY Stats | Beard, PP, daddy, mommy, sigma, brainrot and more, plus their "of the Day" titles. |
| FFY Personality | Rizz, sass, chaos, main character energy and more. |
| FFY Emotions | Happiness, anger, caffeine, hangry and more. |
| FFY Skills | Aim, stealth, cooking, flirting and more. |
| FFY Actions | Punch, kickflip, uppercut, dodge and more. |
| FFY Gym | Lift, deadlift, bench press, sprint and more. |
| FFY Carry | Carry weight, items and gold. |
| FFY Pirate | Pirate skills, outfits, sails and kegs, plus Pirate and Captain of the Day. |
| FFY Sea of Thieves | Sea of Thieves reputations and skills, plus the `!sotfest` countdown. |
| FFY Picks | A random pick for the day: animal, drink, colour, fish, outfit, power and element. |
| FFY Magic | Auras, elemental items, wizard items, patronus and more. |
| FFY Leaderboards | `!leaderboard` (part of FFY Commands itself) |

You can switch commands off here (untick **Enabled**) or give them a cooldown, just like any other Streamer.bot command.

### The Actions tab

| Group | What's in it | Do I edit it? |
|---|---|---|
| **FFY Core** | **FFY Setup** (runs on import), **FFY Enable All Commands**, **FFY Disable All Commands** | Just run them when needed |
| **FFY Commands** | **FFY Commands**, the "brain" that answers every command, and **FFY My Triggers**, where your own commands' triggers go | Only add triggers to **FFY My Triggers** |
| **FFY Helpers** | Settings, switches, special replies, "of the day" titles, countdowns | Yes |
| **FFY Number Commands** | **FFY My Number Commands**, for your own number commands | Yes |
| **FFY List Commands** | **FFY My List Commands**, for your own list commands | Yes |
| **One group per pack** (FFY Stats, FFY Games...) | The pack's data actions (like **FFY Stats** or **FFY Duels**), plus **<Pack> Triggers** and **<Pack> Setup** | The data actions, yes. Never the code of Triggers or Setup |

I call the ones you're allowed to edit **data actions**. Change those as much as you want.

## 4. How to change something (the basics)

You edit every data action the same way:

1. Go to the **Actions** tab.
2. Open the group and click the action, for example **FFY Drinks** in **FFY Picks**.
3. On the right, under **Sub-Actions**, double-click **Execute C# Code**.
4. Scroll down to the bit between these two lines:
   ```
   // ===== EDIT BELOW =====
   ...your lines are here...
   // ===== EDIT ABOVE =====
   ```
   Only change things between those two lines.
5. Make your change.
6. Click **Save and Compile** at the bottom.
7. Close the window. Give it about 30 seconds and your change will be working in chat.

### What the lines look like

Every line is a `Set(...)`. Here's `!drink`:

```csharp
Set("drink", "list", List("Coffee", "Tea", "Martini"));
Set("drink", "template", "{sender}, your drink of the day is {item}!");
Set("drink", "variable", "Drink of the day");
```

You can read it like a sentence: *for the command **drink**, set the **list** to Coffee, Tea, Martini.*

### A few rules

1. The first word is the command's name, without the `!`. So every line for `!drink` starts with `Set("drink", ...`.
2. Text goes inside "quote marks". Numbers and `true`/`false` don't.
3. Every line ends with a `;`
4. `List(...)` holds more than one thing, with commas in between: `List("Coffee", "Tea", "Martini")`
5. A line starting with `//` is switched off. It's just a note. Take the `//` away to switch it on.
6. If you copy another command to start from, change the first word on **every** line. Otherwise you'll overwrite the one you copied. (Everyone does this at least once!)

### If "Save and Compile" shows an error

Don't panic, nothing's broken in chat. The error tells you which line the problem's on, and it's nearly always one of these:

- a missing `"` quote mark
- a missing `)` bracket
- a missing `;` at the end
- a `"` *inside* your text (write it as `\"` instead, like `"She said \"hi\""`)

Fix it and click **Save and Compile** again.

### Words in curly brackets

These get swapped for the real thing when the reply goes out:

| Write this | Chat shows |
|---|---|
| `{sender}` | Whoever typed the command, e.g. @Bob |
| `{target}` | Whoever they tagged, e.g. @Sam |
| `{value}` | The number they got (number commands) |
| `{item}` | The thing they got (list commands) |

# Adding your own stuff

## 5. Make Streamer.bot listen for a new command

Every brand-new command needs two things. It needs its lines in a data action (sections 6 to 11 show you what to write), and it needs this section, so Streamer.bot knows to listen out for it in chat.

I'll use `!snack` as the example. Just swap in your own command's name.

### Step A: create the command

1. Go to the **Commands** tab.
2. Right-click in the empty space in the list and choose **Add**.
3. In the window that pops up:
   - **Name:** `!snack`
   - **Commands:** `!snack`
   - **Location:** Start
   - **Group:** pick an FFY folder, for example *FFY List Commands* (or type a new name starting with `FFY `)
   - **Sources:** tick **Twitch**, **Kick** and/or **YouTube**, wherever you stream
   - Make sure **Enabled** is ticked
4. Click **OK**.

### Step B: connect it to FFY My Triggers

1. Go to the **Actions** tab.
2. Open the **FFY Commands** group and click the **FFY My Triggers** action.
3. On the right, find the **Triggers** box at the top.
4. Right-click inside it and choose **Add** → **Core** → **Commands** → **Command Triggered**.
5. Pick **!snack** from the **Command** drop-down.
6. Click **OK**.

Done. Now add the command's lines (see the next sections) and type `!snack` in chat.

> Use **FFY My Triggers** for this, not FFY Commands. Updates never touch FFY My Triggers, so your triggers stay put.

## 6. Add a number command

This gives each viewer a number that stays the same all day, like `!pp` or `!beard`. Let's make **`!coolness`**.

Chat will see something like: `@Bob, you're 73% cool today!`

### Part 1: add the lines

1. In the **Actions** tab, open **FFY Number Commands** and click **FFY My Number Commands** (updates never touch this one).
2. Double-click **Execute C# Code**.
3. Paste this just above `// ===== EDIT ABOVE =====`:
   ```csharp
   // coolness
   Set("coolness", "min", 0);
   Set("coolness", "max", 100);
   Set("coolness", "template", "{sender}, you're {value}% cool today!");
   Set("coolness", "unit", "%");
   Set("coolness", "variable", "Coolness today");
   ```
4. Click **Save and Compile**.

Here's what each line does:

| Line | What it does | Change it to... |
|---|---|---|
| `min` / `max` | The lowest and highest number they can get | Any numbers, e.g. 1 and 10 |
| `template` | The message in chat | Your own words. Keep `{value}` where the number goes. Make it as fun as you like! |
| `unit` | Added after the number when it's saved (see section 15) | `%`, `cm`, `kg` or `""` for nothing |
| `variable` | The name it's saved under in the viewer's info | Any name. Or delete this line to not save it |

> If you want decimals like 4.5, add `Set("coolness", "step", 0.5);`

### Part 2: make Streamer.bot listen

Do [section 5](#5-make-streamerbot-listen-for-a-new-command) for `!coolness`, then try `!coolness` in chat. Viewers can check someone else's with `!coolness @someone` too.

## 7. Add a list command

This gives each viewer one thing from a list, and it stays the same all day (like `!drink`). Let's make **`!snack`**.

Chat will see: `@Bob, your snack today is Popcorn!`

### Part 1: add the lines

1. In **FFY List Commands**, click **FFY My List Commands** (updates never touch it) and double-click **Execute C# Code**.
2. Paste this above `// ===== EDIT ABOVE =====`:
   ```csharp
   // snack
   Set("snack", "list", List("Cookies", "Crisps", "Popcorn"));
   Set("snack", "template", "{sender}, your snack today is {item}!");
   Set("snack", "variable", "Snack today");
   ```
3. Click **Save and Compile**.

You can put as many things in the list as you want: `List("Cookies", "Crisps", "Popcorn", "Grapes", "Pizza")`.

### Part 2: make Streamer.bot listen

Do [section 5](#5-make-streamerbot-listen-for-a-new-command) for `!snack`.

## 8. Add an interaction

This is one viewer doing something to another. Let's make **`!tickle @someone`**.

Chat will see: `@Bob Tickled @Sam with 73% power!`

1. Open **FFY Interactions** (it's in the **FFY Interactions** group, from the Interactions pack) and add this above `// ===== EDIT ABOVE =====`:
   ```csharp
   Add("tickle");
   ```
   Click **Save and Compile**.
2. Open **FFY Action Words** and add the word that goes in the message:
   ```csharp
   Set("tickle", "Tickled");
   ```
   Click **Save and Compile**.
3. If you want, open **FFY Top Titles** and add titles for `!top tickle`:
   ```csharp
   Set("tickle", "senders", "Top Ticklers");
   Set("tickle", "receivers", "Most Tickled");
   ```
4. Do [section 5](#5-make-streamerbot-listen-for-a-new-command) for `!tickle`.

People can also type `!tickle` by itself (to tickle themselves) or `!tickle everyone`.

> If **consentRequired** is switched on (see [section 12](#12-switch-things-on-and-off)), the other person gets asked first and replies with `!accept` or `!deny`.

## 9. Add an "of the Day" title

The first person each day to hit a certain result wins a title, like **Daddy of the Day**, and anyone can ask who's got it.

Chat will see:
- When someone wins: `@Bob, you're 100% cool today! You are the Coolness of the Day!`
- When someone asks with `!coolnessofday`: `@Bob is the Coolness of the Day!`
- Before anyone's won: `Nobody is Coolness of the Day yet!`

### For a number command (win with an exact number)

1. Open **FFY Of The Day** (in **FFY Helpers**) and paste this above `// ===== EDIT ABOVE =====`:
   ```csharp
   // coolness
   Set("coolness", "title", "Coolness");
   Set("coolness", "winValue", 100);
   Set("coolness", "whoCommands", List("coolnessofday"));
   Set("coolness", "noWinnerMessage", "Nobody is Coolness of the Day yet!");
   ```
2. Click **Save and Compile**.
3. Do [section 5](#5-make-streamerbot-listen-for-a-new-command) for **`!coolnessofday`**.

### For a list command (win by getting a certain thing)

Use `winItemContains` instead of `winValue`. In this one, whoever gets something with "popcorn" in it wins:

```csharp
// snack
Set("snack", "title", "Snack");
Set("snack", "winItemContains", "popcorn");
Set("snack", "whoCommands", List("snackofday"));
Set("snack", "noWinnerMessage", "Nobody has won Snack of the Day yet!");
```

### A few things to know

- The "who won" command has to end in `ofday`, like `!coolnessofday` or `!snackofday`.
- `title` is the name that gets shown, e.g. "You are the **Coolness** of the Day!".
- If you want different wording when someone asks who won, add:
  ```csharp
  Set("coolness", "whoMessage", "{winner} is the {title} of the Day with {value}%!");
  ```
- Titles reset at midnight.

## 10. Give a viewer their own special reply

You can make a command always say something special for one person.

So when SomeViewer types `!beard`, chat sees: `@SomeViewer, your beard is legendary!`

1. Open **FFY Special Users** (in **FFY Helpers**) and double-click **Execute C# Code**.
2. Paste this above `// ===== EDIT ABOVE =====`:
   ```csharp
   Set("someviewer", "beard", "@SomeViewer, your beard is legendary!");
   ```
   The first bit is their username in lowercase, the second is the command (no `!`), and the third is what chat should say.
3. Click **Save and Compile**.

Add as many as you like, for different people or different commands. You don't need to touch the Commands tab for these, because the command's already there.

### Special interactions

Same idea, but for interactions, and it lives in **FFY Special Interactions**. This one kicks in whenever *someviewer* hugs *theirfriend*:

```csharp
Set("someviewer", "theirfriend", "hug", "value", 1000);
Set("someviewer", "theirfriend", "hug", "message", "@{sender} gave @{target} a {value}% bear hug!");
```

Put `"anyone"` instead of a username to match everyone, e.g. *anyone* hugging *theirfriend*.

## 11. More things you can add

For all of these, open the action named, paste the lines above `// ===== EDIT ABOVE =====`, click **Save and Compile**, then do [section 5](#5-make-streamerbot-listen-for-a-new-command) for each new command.

### Add-ons (separate imports)

These are extra packs that go on top, and each one has its own guide:

| Add-on | What it adds | Needs FFY Commands? |
|---|---|---|
| **FFY Seasonal** | A pack for every time of year: Valentine's, Easter, St Patrick's, Summer, Halloween, Bonfire Night, ThanksGiving, Christmas (with Santa) and New Year | Yes |
| **FFY Game Packs** | Commands for the game you're playing: Fortnite, Minecraft and Gears Of War | Yes |
| **FFY Daily's** | 20 daily channel point redeems, like *"Bob has redeemed their daily head pat!"* Each viewer can claim each one once a day | No |
| **FFY Pokemon** | Open Pokémon booster packs (10 cards plus an Energy, with PSA grades and values), god packs, 1-1 Pikachus, `!keep`, `!sell all` or `!sell bulk`, `!binder`, `!bestcards`, and a season reset after however many days you choose | No |
| **FFY Dino** | `!dig` for fossils, complete dinosaur skeletons for your `!museum`, amber and 1-1 legendary fossils | No |
| **FFY Mining** | `!mine` for ores and gems, `!sellores`, `!upgrade` your pickaxe, BIG FIND diamonds and 1-1 gems | No |
| **FFY Pets** | Pets for chat: one chat pet everyone shares, or every viewer adopts their own. Feed, walk, play, train tricks and cuddle | No |
| **FFY Bounty** | Put a price on someone's head, hunt them down to claim it, or lie low in a hideout | No |
| **FFY Counters** | 20 counters, like `!pickle` (+1), `!setpickle 5` and `!pickles` (shows the count) | No |

They're all in the **[FFYAddons folder](../FFYAddons/Readme.md)**. Install whichever you want the same way you installed this.

### Countdown (FFY Countdowns)

Counts down to the same date every year, like a stream birthday on 14 March:

```csharp
Set("birthday", "month", 3);
Set("birthday", "day", 14);
Set("birthday", "message", "{sender}, only {days} days, {hours} hours and {minutes} minutes until the stream birthday!");
```

### Dice (FFY Dice)

A random roll that's different every time. Here's a normal 6-sided dice:

```csharp
Set("d6", "min", 1);
Set("d6", "max", 6);
Set("d6", "label", "D6");
Set("d6", "action", "rolled");
Set("d6", "crits", true);
```
Chat shows: `@Bob, you rolled a d6 and got **4**!`. With `crits` set to `true`, rolling a 6 adds **CRITICAL SUCCESS!** and a 1 adds **CRITICAL FAIL!**.

You can use words instead of numbers too, like a magic 8 ball:

```csharp
Set("magic8", "min", 0);
Set("magic8", "max", 2);
Set("magic8", "label", "magic 8 ball");
Set("magic8", "action", "shook");
Set("magic8", "faces", List("Yes", "No", "Ask again later"));
```
One thing to watch: with words, `min` is always `0` and `max` is *one less* than the number of words. There are 3 words here, so `max` is 2.

### Duel (FFY Duels)

Two viewers compare their numbers from a number command. This one uses `!coolness` from section 6:

```csharp
Set("coolduel", "stat", "coolness");
Set("coolduel", "seedKey", "coolness");
Set("coolduel", "matchSelf", true);
Set("coolduel", "selfMessage", "{sender} tried to duel themselves... awkward.");
Set("coolduel", "tieMessage", "{sender} and {target} are equally cool at {value}%!");
Set("coolduel", "outcomes", List(
    "{winner} is {winnerValue}% cool and leaves {loser} ({loserValue}%) in the cold!",
    "{loser} tried, but {winner}'s {winnerValue}% coolness was too much."
));
```
For `!coolduel @Sam`, chat shows: `@Bob is 91% cool and leaves @Sam (40%) in the cold!`

`stat` and `seedKey` are the number command being compared, and you put the same name in both. `outcomes` is a list, and one gets picked at random. You can use `{winner}`, `{loser}`, `{winnerValue}` and `{loserValue}` in them.

### Reply command (always about one person)

For example, a `!hype` that always talks about one particular viewer: `@someviewer is the best!`. These need their own action, but you only have to make it once:

1. In the **Actions** tab, right-click **FFY Special Users** and choose **Duplicate**.
2. Right-click the copy, choose **Rename** and call it **FFY Reply Commands**.
3. Open its **Execute C# Code**. Near the top, change:
   ```csharp
   private const string DataPath = "helpers/specialusers";
   ```
   to:
   ```csharp
   private const string DataPath = "helpers/replycommands";
   ```
4. Delete the example lines between EDIT BELOW and EDIT ABOVE and paste in:
   ```csharp
   Set("hype", "target", "someviewer");
   Set("hype", "niceChance", 0.5);
   Set("hype", "niceReplies", List("is the best!", "is a legend!"));
   Set("hype", "otherReplies", List("is... fine, I guess.", "forgot to log in today."));
   ```
5. Click **Save and Compile**, then do section 5 for `!hype`.

`niceChance` of 0.5 means it's 50/50. Set it to 0.9 and it'll pick a nice reply 9 times out of 10.

### Santa

`!santa` and `!santastats` have moved to the **FFY Christmas** add-on (see Add-ons above).

# Settings and help

## 12. Switch things on and off

Open **FFY Switches** (in **FFY Helpers**), set things to `true` (on) or `false` (off) and click **Save and Compile**.

| Switch | What it does |
|---|---|
| `consentRequired` | **Ask first.** When on, `!hug @Sam` asks: *"@Bob wants to hug @Sam! @Sam, type !accept or !deny within 60 seconds."* Once Sam accepts, Bob doesn't need to ask again for the rest of the day. |
| `saveToUserVariables` | **Save results.** Saves each viewer's results to their info in Streamer.bot (see section 15). |
| `replyAsBot` | **Who replies.** On = your bot account. Off = your own account. |
| `ofTheDayEnabled` | **"Of the Day" titles.** Off = no titles, and the `!...ofday` commands stay quiet. |
| `specialUsersEnabled` | **Special replies** from FFY Special Users. |
| `specialInteractionsEnabled` | **Special interactions** from FFY Special Interactions. |

### Switch off one command

The easiest way is in the **Commands** tab. Click the command and untick **Enabled**.

## 13. Other settings

These are in **FFY Config** (in **FFY Helpers**):

| Setting | What it does |
|---|---|
| `channelName` | Your channel name (see [section 2](#2-two-things-to-set-first)). |
| `timeZone` | When your "day" starts. Leave it as `""` to use your PC's clock. Or use a **Windows** time zone name: `"GMT Standard Time"` (UK), `"Eastern Standard Time"` (US East), `"Pacific Standard Time"` (US West)... **Not** `"Europe/London"`, which Streamer.bot doesn't understand. The full list is in the [Complete Guide](QuickGuide.md#set-your-time-zone-optional). |
| `consentTimeoutSeconds` | How many seconds people get to type `!accept` or `!deny`. |
| Disabled commands | A list of commands that never reply. Delete the `//` in front of the example line to use it. |

## 14. Something isn't working

Go through these in order.

**The command doesn't reply at all**
1. In the **Commands** tab, is the command there, and is **Enabled** ticked?
2. Also in the **Commands** tab, is the right platform ticked under **Sources** (Twitch, Kick, YouTube)?
3. For your own commands, go to **Actions** → **FFY My Triggers**. Is there a **Command Triggered** trigger for it in the **Triggers** box? (See [section 5](#5-make-streamerbot-listen-for-a-new-command).)
4. Check your lines. Does every one start with **this command's name**? For `!snack`, they all have to start `Set("snack", ...`. This is the most common mistake when you've copied another command!
5. Did you click **Save and Compile**, and give it 30 seconds?
6. Is the feature switched off in FFY Switches?

**"Save and Compile" shows an error**
Check the line it mentions for a missing `"`, `)` or `;`. There's more in [section 4](#if-save-and-compile-shows-an-error).

**Still stuck?**
Open the **Logs** tab in Streamer.bot and look for lines starting with **`[FFY]`**. For example, this one:
`[FFY] !snack gave no reply. No data action has lines starting Set("snack", ...)` means the command doesn't have any lines yet, or they start with the wrong name.

## 15. Good to know

**Results change at midnight.** Everyone keeps the same `!pp`, `!drink` and so on all day, then gets a new one after midnight. That's midnight in **your** time (see `timeZone`), and it's the same for every viewer.

**Results get saved.** When someone uses a command on themselves, their result is saved in Streamer.bot. You can see them in the **Global Variables** tab → **Persisted User Globals** → the platform (**Twitch**, **Kick** or **YouTube**) → their username. You'll see things like **PP size today = 6 inches**, and you can use them in your other actions and overlays.

**Today's winners and leaderboards** are kept in the **Global Variables** tab as `ffy.state`, and they reset at midnight. Santa history (from FFY Christmas) is kept forever. If you want to wipe the lot, delete `ffy.state`.

**`ffy.datacache`** (also in Global Variables) is what lets commands answer straight away after a restart. Leave it alone, it looks after itself.

**Built-in games** (in the **FFY Games** pack): `!rps`, `!rpsls`, `!tugofwar`, `!diceroll`, `!coinflip`, `!highorlow` and `!compat`. Then there's `!leaderboard` (or `!leaderboard users`), which is part of FFY Commands itself, and `!top highfive` (or any interaction that isn't in FFY Do Not Track) in the **FFY Interactions** pack.

**Keeping your changes safe from updates:** put them in the **FFY My ...** actions. If you want to add to a built-in action (like FFY Of The Day), duplicate it, call the copy **FFY My ...**, keep its `DataPath` and keep only your own lines in it. They get added on top, and updates never touch them. The [Complete Guide, section 21](QuickGuide.md#21-keeping-your-changes-safe-from-updates) has the full details.

For a lot more detail, with extra examples, every data action explained and all 200 commands, see the **[Complete Guide](QuickGuide.md)**.
