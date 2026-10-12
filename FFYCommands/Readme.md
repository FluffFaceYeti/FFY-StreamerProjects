# FFY Commands for Streamer.bot

Fun chat commands for your stream: `!pp`, `!beard`, `!drink`, `!hug @someone`, duels, dice, leaderboards, "Daddy of the Day" and lots more (200 in total).

- Works on **Twitch, Kick and YouTube**.
- Runs inside **Streamer.bot** (version 1.0 or newer). No websites, servers or extra programs.
- You can change any reply, or add your own commands, by copying and editing a few lines.

You don't need to know how to code. This page shows you exactly where to click.

> **Want every detail?** The **[Complete Guide (QuickGuide.md)](QuickGuide.md)** covers everything in depth, with lots of copy-and-paste examples and a list of all 200 commands.

---

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

---

# Getting started

## 1. Install it

FFY Commands comes in two parts:

- **FFY Commands** (the `FFYCommands` file): the "brain", your settings and `!leaderboard`. **Everyone needs this, and it goes in first.**
- **Packs**: the commands themselves, grouped by theme, like **FFY Stats**, **FFY Interactions** or **FFY Games**. Install only the ones you want.

### Step 1: install FFY Commands

1. Download the **`FFYCommands`** file from this page. (This is the **first install** file. Updates use a different file, see below.)
2. Open **Streamer.bot**.
3. Click **Import** in the bar at the top of the window.
4. Drag and drop the file into the box.
5. Click **Import**.

### Step 2: install the packs you want

Open the **[Packs](Packs/Readme.md)** folder, open a pack, download its file (e.g. **`FFY-Stats`**) and import it the same way. Do this for each pack you want, in any order.

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

Each pack's commands are **switched on as soon as you import it**. Type `!beard` in your chat to test (it's in FFY Stats).

**Switching commands on and off:** click the **Commands** tab, open a folder (e.g. **FFY Stats**), click a command (e.g. **!beard**), and tick or untick **Enabled**. To switch every FFY command on or off at once, go to the **Actions** tab → **FFY Core** group, right-click **FFY Enable All Commands** (or **FFY Disable All Commands**) and choose **Run Now**.

> **Updating to a newer version later?** Download the **`FFYCommands-update`** file, and import it the same way (drag and drop it into the Import box) over the top. No need to delete anything. Your settings (FFY Config, FFY Switches), special users and interactions, **FFY My ...** actions and your commands are all kept. Changes made inside built-in actions like FFY Stats *are* replaced, so put your changes in the **FFY My** actions. The [Complete Guide, section 21](QuickGuide.md#21-keeping-your-changes-safe-from-updates) explains how.
>
> **Updating from version 1 (before packs)?** Import `FFYCommands-update`, then import the packs you use. Until you do, their commands won't reply. Your settings and **FFY My** actions are kept.
>
> **Updating a pack:** import the pack's file again, over the top. This switches all its commands back on and resets their cooldowns and permissions, so only do it when the pack has changed.
>
> **Before updating, make a backup (recommended):** click **Export** in the top bar of Streamer.bot, tick every action starting with **FFY**, and save the export text in a Notepad file. If anything of yours goes missing after the update, copy your lines back from it, or import the backup to restore those actions exactly as they were. [More detail](QuickGuide.md#before-you-update-make-a-backup-recommended).

---

## 2. Two things to set first

### Your channel name

This makes your viewers' daily results unique to your channel.

1. Click the **Actions** tab.
2. Find the group called **FFY Helpers** and click the little arrow to open it.
3. Click **FFY Config**.
4. On the right, under **Sub-Actions**, double-click **Execute C# Code**. A window with code in it opens.
5. Find this line:
   ```csharp
   Set("channelName", "");
   ```
6. Type your channel name between the two quote marks:
   ```csharp
   Set("channelName", "YourChannelName");
   ```
7. Click **Save and Compile** at the bottom of the window, then close it.

### Your on/off switches

In the same **FFY Helpers** group, open **FFY Switches** the same way (steps 3 to 7 above). Each switch has a line above it explaining what it does. Change `true` (on) or `false` (off), then click **Save and Compile**. There's more about them in [section 12](#12-switch-things-on-and-off).

---

## 3. Finding your way around

Everything lives in two tabs in Streamer.bot.

### The Commands tab

This is the list of chat commands (`!pp`, `!drink`, `!hug` and so on), with one folder per pack:

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

Here you can switch a command off (untick **Enabled**) or give it a cooldown, the same as any Streamer.bot command.

### The Actions tab

| Group | What's in it | Do I edit it? |
|---|---|---|
| **FFY Core** | **FFY Setup** (runs on import), **FFY Enable All Commands**, **FFY Disable All Commands** | Just run them when needed |
| **FFY Commands** | **FFY Commands**, the "brain" that answers every command, and **FFY My Triggers**, where your own commands' triggers go | Only add triggers to **FFY My Triggers** |
| **FFY Helpers** | Settings, switches, special replies, "of the day" titles, countdowns | Yes |
| **FFY Number Commands** | **FFY My Number Commands**, for your own number commands | Yes |
| **FFY List Commands** | **FFY My List Commands**, for your own list commands | Yes |
| **One group per pack** (FFY Stats, FFY Games...) | The pack's data actions (like **FFY Stats** or **FFY Duels**), plus **<Pack> Triggers** and **<Pack> Setup** | The data actions, yes. Never the code of Triggers or Setup |

Everything you're allowed to edit is called a **data action**. You can change those as much as you like.

---

## 4. How to change something (the basics)

Every data action is edited the same way.

1. Go to the **Actions** tab.
2. Open the group and click the action, for example **FFY Drinks** in **FFY Picks**.
3. On the right, under **Sub-Actions**, double-click **Execute C# Code**.
4. Scroll to the part between these two lines:
   ```
   // ===== EDIT BELOW =====
   ...your lines are here...
   // ===== EDIT ABOVE =====
   ```
   **Only change things between these two lines.**
5. Make your change.
6. Click **Save and Compile** at the bottom.
7. Close the window. Your change works in chat within **30 seconds**.

### What the lines look like

Every line is a `Set(...)`. Here's `!drink`:

```csharp
Set("drink", "list", List("Coffee", "Tea", "Martini"));
Set("drink", "template", "{sender}, your drink of the day is {item}!");
Set("drink", "variable", "Drink of the day");
```

Read it like a sentence: *for the command **drink**, set the **list** to Coffee, Tea, Martini.*

### The golden rules

1. **The first word is the command's name**, without the `!`. Every line for `!drink` starts `Set("drink", ...`.
2. **Text goes inside "quote marks".** Numbers and `true`/`false` don't need them.
3. **Every line ends with `;`**
4. **`List(...)` holds more than one thing**, separated by commas: `List("Coffee", "Tea", "Martini")`
5. **A line starting with `//` is switched off.** It's just a note. Delete the `//` to switch it on.
6. **Copying another command to start from?** Change the first word on **every** line, or you'll overwrite the command you copied.

### If "Save and Compile" shows an error

Don't panic: nothing is broken in chat. The error message tells you which line has a problem. It's almost always one of these:

- a missing `"` quote mark
- a missing `)` bracket
- a missing `;` at the end
- a `"` *inside* your text (write it as `\"` instead, like `"She said \"hi\""`)

Fix it, and click **Save and Compile** again.

### Words in curly brackets

These get swapped for real values when the reply is sent:

| Write this | Chat shows |
|---|---|
| `{sender}` | Whoever typed the command, e.g. @Bob |
| `{target}` | Whoever they tagged, e.g. @Sam |
| `{value}` | The number they got (number commands) |
| `{item}` | The thing they got (list commands) |

---

# Adding your own stuff

## 5. Make Streamer.bot listen for a new command

Every brand-new command needs **two things**:

- **Its lines** in a data action (sections 6 to 11 show you what to write).
- **This section**, so Streamer.bot knows to listen for it in chat.

We'll use `!snack` as the example. Swap in your own command's name.

### Step A: create the command

1. Click the **Commands** tab.
2. **Right-click** in the empty space in the list, and choose **Add**.
3. In the window that opens:
   - **Name:** `!snack`
   - **Commands:** `!snack`
   - **Location:** Start
   - **Group:** pick an FFY folder, for example *FFY List Commands* (or type a new name starting with `FFY `)
   - **Sources:** tick **Twitch**, **Kick** and/or **YouTube**, wherever you stream
   - Make sure **Enabled** is ticked
4. Click **OK**.

### Step B: connect it to FFY My Triggers

1. Click the **Actions** tab.
2. Open the **FFY Commands** group and click the **FFY My Triggers** action.
3. On the right, find the **Triggers** box at the top.
4. **Right-click** inside the Triggers box and choose **Add** → **Core** → **Commands** → **Command Triggered**.
5. In the **Command** drop-down, choose **!snack**.
6. Click **OK**.

That's it. Now add the command's lines (next sections) and type `!snack` in chat.

> **Tip:** use **FFY My Triggers**, not FFY Commands. Updates never touch FFY My Triggers, so your triggers are kept.

---

## 6. Add a number command

Gives each viewer a number that stays the same all day (like `!pp` or `!beard`). We'll make **`!coolness`**.

**What chat will see:** `@Bob, you're 73% cool today!`

### Part 1: add the lines

1. In the **Actions** tab, open **FFY Number Commands** and click **FFY My Number Commands** (updates never touch it).
2. Double-click **Execute C# Code**.
3. Just above `// ===== EDIT ABOVE =====`, paste:
   ```csharp
   // coolness
   Set("coolness", "min", 0);
   Set("coolness", "max", 100);
   Set("coolness", "template", "{sender}, you're {value}% cool today!");
   Set("coolness", "unit", "%");
   Set("coolness", "variable", "Coolness today");
   ```
4. Click **Save and Compile**.

What each line means:

| Line | What it does | Change it to... |
|---|---|---|
| `min` / `max` | The lowest and highest number they can get | Any numbers, e.g. 1 and 10 |
| `template` | The message in chat | Your own words. Keep `{value}` where the number goes. Make it as fun as you like! |
| `unit` | Added after the number when it's saved (see section 15) | `%`, `cm`, `kg` or `""` for nothing |
| `variable` | The name it's saved under in the viewer's info | Any name. Or delete this line to not save it |

> Want decimals like 4.5? Add `Set("coolness", "step", 0.5);`

### Part 2: make Streamer.bot listen

Follow [section 5](#5-make-streamerbot-listen-for-a-new-command) for `!coolness`. Then type `!coolness` in chat. Viewers can also check someone else with `!coolness @someone`.

---

## 7. Add a list command

Gives each viewer one thing from a list, the same all day (like `!drink`). We'll make **`!snack`**.

**What chat will see:** `@Bob, your snack today is Popcorn!`

### Part 1: add the lines

1. In **FFY List Commands**, click **FFY My List Commands** (updates never touch it) and double-click **Execute C# Code**.
2. Paste above `// ===== EDIT ABOVE =====`:
   ```csharp
   // snack
   Set("snack", "list", List("Cookies", "Crisps", "Popcorn"));
   Set("snack", "template", "{sender}, your snack today is {item}!");
   Set("snack", "variable", "Snack today");
   ```
3. Click **Save and Compile**.

Add as many things to the list as you like: `List("Cookies", "Crisps", "Popcorn", "Grapes", "Pizza")`.

### Part 2: make Streamer.bot listen

Follow [section 5](#5-make-streamerbot-listen-for-a-new-command) for `!snack`.

---

## 8. Add an interaction

One viewer does something to another. We'll make **`!tickle @someone`**.

**What chat will see:** `@Bob Tickled @Sam with 73% power!`

1. Open **FFY Interactions** (in the **FFY Interactions** group, from the Interactions pack), and above `// ===== EDIT ABOVE =====` add:
   ```csharp
   Add("tickle");
   ```
   Click **Save and Compile**.
2. Open **FFY Action Words** and add the word that appears in the message:
   ```csharp
   Set("tickle", "Tickled");
   ```
   Click **Save and Compile**.
3. *(Optional)* Open **FFY Top Titles** and add titles for `!top tickle`:
   ```csharp
   Set("tickle", "senders", "Top Ticklers");
   Set("tickle", "receivers", "Most Tickled");
   ```
4. Follow [section 5](#5-make-streamerbot-listen-for-a-new-command) for `!tickle`.

Viewers can also type `!tickle` on its own (to tickle themselves) or `!tickle everyone`.

> **Consent:** if **consentRequired** is switched on (see [section 12](#12-switch-things-on-and-off)), the other person is asked first, and they reply `!accept` or `!deny`.

---

## 9. Add an "of the Day" title

The first person each day to hit a certain result wins a title, like **Daddy of the Day**. Anyone can then ask who won.

**What chat will see:**
- When someone wins: `@Bob, you're 100% cool today! You are the Coolness of the Day!`
- When someone asks with `!coolnessofday`: `@Bob is the Coolness of the Day!`
- Before anyone's won: `Nobody is Coolness of the Day yet!`

### For a number command (win with an exact number)

1. Open **FFY Of The Day** (in **FFY Helpers**) and paste above `// ===== EDIT ABOVE =====`:
   ```csharp
   // coolness
   Set("coolness", "title", "Coolness");
   Set("coolness", "winValue", 100);
   Set("coolness", "whoCommands", List("coolnessofday"));
   Set("coolness", "noWinnerMessage", "Nobody is Coolness of the Day yet!");
   ```
2. Click **Save and Compile**.
3. Follow [section 5](#5-make-streamerbot-listen-for-a-new-command) for **`!coolnessofday`**.

### For a list command (win by getting a certain thing)

Swap `winValue` for `winItemContains`. Whoever gets something with "popcorn" in it wins:

```csharp
// snack
Set("snack", "title", "Snack");
Set("snack", "winItemContains", "popcorn");
Set("snack", "whoCommands", List("snackofday"));
Set("snack", "noWinnerMessage", "Nobody has won Snack of the Day yet!");
```

### Things to know

- The **"who won" command must end in `ofday`**, like `!coolnessofday` or `!snackofday`.
- `title` is the name shown, e.g. "You are the **Coolness** of the Day!".
- Want different wording when someone asks who won? Add:
  ```csharp
  Set("coolness", "whoMessage", "{winner} is the {title} of the Day with {value}%!");
  ```
- Titles reset at midnight.

---

## 10. Give a viewer their own special reply

Make a command say something special for one person, every time.

**What chat will see when SomeViewer types `!beard`:** `@SomeViewer, your beard is legendary!`

1. Open **FFY Special Users** (in **FFY Helpers**) and double-click **Execute C# Code**.
2. Paste above `// ===== EDIT ABOVE =====`:
   ```csharp
   Set("someviewer", "beard", "@SomeViewer, your beard is legendary!");
   ```
   - 1st word: their **username in lowercase**.
   - 2nd word: the **command** (without `!`).
   - 3rd: **what chat should say**.
3. Click **Save and Compile**.

Add as many lines as you like, for different people or different commands. No need to touch the Commands tab, since the command already exists.

### Special interactions

The same idea for interactions, in **FFY Special Interactions**. Whenever *someviewer* hugs *theirfriend*:

```csharp
Set("someviewer", "theirfriend", "hug", "value", 1000);
Set("someviewer", "theirfriend", "hug", "message", "@{sender} gave @{target} a {value}% bear hug!");
```

Use `"anyone"` in place of a username to match everybody, e.g. *anyone* hugging *theirfriend*.

---

## 11. More things you can add

For each of these, open the action shown, paste the lines above `// ===== EDIT ABOVE =====`, click **Save and Compile**, and then do [section 5](#5-make-streamerbot-listen-for-a-new-command) for each new command.

### Add-ons (separate imports)

Extra packs you can install on top, each with its own guide:

| Add-on | What it adds | Needs FFY Commands? |
|---|---|---|
| **FFY Christmas** | Santa's naughty or nice list (results can last a day or longer), `!present`, `!grinch`, `!reindeer`, `!cracker`, `!snowball @someone`, Grinch of the Day and more | Yes |
| **FFY Halloween** | `!costume`, `!pumpkin`, `!spooky`, `!candy`, `!trickortreat`, `!spook @someone`, plus Nightmare Before Christmas ones like `!jack`, `!oogieboogie` and `!whatsthis` | Yes |
| **FFY ThanksGiving** | `!turkey`, `!gobble`, `!pie`, `!thankful`, `!leftovers`, a `!wishbone @someone` duel, Turkey of the Day and more | Yes |
| **FFY Daily's** | 20 daily channel point redeems, like *"Bob has redeemed their daily head pat!"* Each viewer can claim each one once a day | No |
| **FFY Pokemon** | Open a Pokémon card each day (with a PSA grade and value), `!keep` or `!sell` it, `!binder` to see your collection, and a season reset after however many days you choose | No |
| **FFY Counters** | 20 counters, like `!pickle` (+1), `!setpickle 5` and `!pickles` (shows the count) | No |

Each add-on is its own import file with its own guide. Install the ones you want, the same way as this one.

### Countdown (FFY Countdowns)

Counts down to a date every year, like a stream birthday on 14 March:

```csharp
Set("birthday", "month", 3);
Set("birthday", "day", 14);
Set("birthday", "message", "{sender}, only {days} days, {hours} hours and {minutes} minutes until the stream birthday!");
```

### Dice (FFY Dice)

A random roll, different every time. A 6-sided dice:

```csharp
Set("d6", "min", 1);
Set("d6", "max", 6);
Set("d6", "label", "D6");
Set("d6", "action", "rolled");
Set("d6", "crits", true);
```
Chat shows: `@Bob, you rolled a d6 and got **4**!`. With `crits` set to `true`, a 6 adds **CRITICAL SUCCESS!** and a 1 adds **CRITICAL FAIL!**.

Want words instead of numbers? Like a magic 8 ball:

```csharp
Set("magic8", "min", 0);
Set("magic8", "max", 2);
Set("magic8", "label", "magic 8 ball");
Set("magic8", "action", "shook");
Set("magic8", "faces", List("Yes", "No", "Ask again later"));
```
**Note:** with words, `min` is always `0` and `max` is *one less* than the number of words. Here that's 3 words, so `max` is 2.

### Duel (FFY Duels)

Two viewers compare their number from a number command. This uses `!coolness` from section 6:

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
Chat shows (for `!coolduel @Sam`): `@Bob is 91% cool and leaves @Sam (40%) in the cold!`

- `stat` and `seedKey`: the number command to compare. Put the same name in both.
- `outcomes`: one is picked at random. You can use `{winner}`, `{loser}`, `{winnerValue}` and `{loserValue}`.

### Reply command (always about one person)

For example, `!hype` always talks about one particular viewer: `@someviewer is the best!`. These need their own action, which you only make once:

1. In the **Actions** tab, right-click **FFY Special Users** and choose **Duplicate**.
2. Right-click the copy, choose **Rename**, and call it **FFY Reply Commands**.
3. Open its **Execute C# Code**. Near the top, change:
   ```csharp
   private const string DataPath = "helpers/specialusers";
   ```
   to:
   ```csharp
   private const string DataPath = "helpers/replycommands";
   ```
4. Delete the example lines between EDIT BELOW and EDIT ABOVE, and paste:
   ```csharp
   Set("hype", "target", "someviewer");
   Set("hype", "niceChance", 0.5);
   Set("hype", "niceReplies", List("is the best!", "is a legend!"));
   Set("hype", "otherReplies", List("is... fine, I guess.", "forgot to log in today."));
   ```
5. Click **Save and Compile**, then do section 5 for `!hype`.

`niceChance` 0.5 means it's half and half. 0.9 would pick a nice reply 9 times out of 10.

### Santa

`!santa` and `!santastats` are now part of the **FFY Christmas** add-on (see Add-ons above).

---

# Settings and help

## 12. Switch things on and off

Open **FFY Switches** (in **FFY Helpers**). Change `true` (on) or `false` (off), then click **Save and Compile**.

| Switch | What it does |
|---|---|
| `consentRequired` | **Ask first.** When on, `!hug @Sam` asks: *"@Bob wants to hug @Sam! @Sam, type !accept or !deny within 60 seconds."* Once Sam accepts, Bob doesn't need to ask again for the rest of the day. |
| `saveToUserVariables` | **Save results.** Saves each viewer's results to their info in Streamer.bot (see section 15). |
| `replyAsBot` | **Who replies.** On = your bot account. Off = your own account. |
| `ofTheDayEnabled` | **"Of the Day" titles.** Off = no titles, and the `!...ofday` commands stay quiet. |
| `specialUsersEnabled` | **Special replies** from FFY Special Users. |
| `specialInteractionsEnabled` | **Special interactions** from FFY Special Interactions. |

### Switch off one command

The easiest way: in the **Commands** tab, click the command and untick **Enabled**.

---

## 13. Other settings

These are in **FFY Config** (in **FFY Helpers**):

| Setting | What it does |
|---|---|
| `channelName` | Your channel name (see [section 2](#2-two-things-to-set-first)). |
| `timeZone` | When your "day" starts. Leave it as `""` to use your PC's clock. Or use a **Windows** time zone name: `"GMT Standard Time"` (UK), `"Eastern Standard Time"` (US East), `"Pacific Standard Time"` (US West)... **Not** `"Europe/London"`, which Streamer.bot doesn't understand. The full list is in the [Complete Guide](QuickGuide.md#set-your-time-zone-optional). |
| `consentTimeoutSeconds` | How many seconds people get to type `!accept` or `!deny`. |
| Disabled commands | A list of commands that never reply. Delete the `//` in front of the example line to use it. |

---

## 14. Something isn't working

Work down this list:

**The command doesn't reply at all**
1. **Commands tab:** is the command there, and is **Enabled** ticked?
2. **Commands tab:** is the right platform ticked under **Sources** (Twitch, Kick, YouTube)?
3. **Actions tab → FFY My Triggers** (your own commands): is there a **Command Triggered** trigger for it in the **Triggers** box? (See [section 5](#5-make-streamerbot-listen-for-a-new-command).)
4. **Your lines:** does every line start with **this command's name**? For `!snack`, every line must start `Set("snack", ...`. *(This is the most common mistake when copying another command!)*
5. **Did you click Save and Compile?** And wait 30 seconds?
6. **Is the feature switched off** in FFY Switches?

**"Save and Compile" shows an error**
Look at the line it mentions for a missing `"`, `)` or `;`. See [section 4](#if-save-and-compile-shows-an-error).

**Still stuck?**
Click the **Logs** tab in Streamer.bot and look for lines starting with **`[FFY]`**. For example:
`[FFY] !snack gave no reply. No data action has lines starting Set("snack", ...)` means the command has no lines yet, or they start with the wrong name.

---

## 15. Good to know

- **Results change at midnight.** Everyone keeps the same `!pp`, `!drink` and so on all day, and gets a new one after midnight. "Midnight" means **your** time (see `timeZone`), the same for every viewer.
- **Saved results:** when someone uses a command on themselves, their result is saved in Streamer.bot. To see them, click the **Global Variables** tab → **Persisted User Globals** → the platform (**Twitch**, **Kick** or **YouTube**) → select their username. You'll see things like **PP size today = 6 inches**. You can use these in your other actions and overlays.
- **Today's winners and leaderboards** are kept in the **Global Variables** tab, as `ffy.state`. They reset at midnight. Santa history (FFY Christmas) is kept forever. To wipe everything, delete `ffy.state`.
- **`ffy.datacache`** (also in Global Variables) lets commands answer instantly after a restart. Leave it alone; it looks after itself.
- **Built-in games** (in the **FFY Games** pack): `!rps`, `!rpsls`, `!tugofwar`, `!diceroll`, `!coinflip`, `!highorlow`, `!compat`. Plus `!leaderboard` (or `!leaderboard users`), part of FFY Commands itself, and `!top highfive` (or any interaction that isn't in FFY Do Not Track) in the **FFY Interactions** pack.
- **Keeping your changes safe from updates:** put them in the **FFY My ...** actions. To add to a built-in action (like FFY Of The Day), duplicate it, name the copy **FFY My ...**, keep its `DataPath`, and keep only your own lines. They're added on top, and updates never touch them. Full details are in the [Complete Guide, section 21](QuickGuide.md#21-keeping-your-changes-safe-from-updates).
- The **[Complete Guide](QuickGuide.md)** has much more detail, with extra examples, every data action explained, and all 200 commands.
