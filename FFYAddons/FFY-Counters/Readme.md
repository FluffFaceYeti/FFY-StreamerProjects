# FFY Counters

Count anything you like. How many pickles you've eaten, how many times you've died, raged, crashed... you get the idea.

```
Viewer: !pickle
Chat: FluffFaceYeti has eaten 5 pickles!
```

You don't need FFY Commands for this one, and it works on Twitch, Kick and YouTube. Counts never reset on their own. They carry on past midnight and through restarts until you change them.

If you want, the counts can show up on screen in OBS too. That's optional, and it's explained in [Showing a counter in OBS](#showing-a-counter-in-obs) further down.

## Installing

Download the **`FFY-Counters`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

The commands are already on, so type `!pickle` in chat to try it.

One thing I'd do straight away is make the `!set...` commands mods only, otherwise chat can change your counts to whatever they like. [Permissions](#permissions) shows you how.

## How it works

Each counter comes with three commands. For pickles they look like this:

| Command | What it does | Chat shows |
|---|---|---|
| `!pickle` | Adds 1 | FluffFaceYeti has eaten 6 pickles! |
| `!pickles` | Shows the count | FluffFaceYeti has eaten 6 pickles! |
| `!setpickle 10` | Sets it to 10 | FluffFaceYeti has eaten 10 pickles! |
| `!setpickle -1` | Takes 1 off | FluffFaceYeti has eaten 9 pickles! |
| `!setpickle +3` | Adds 3 | FluffFaceYeti has eaten 12 pickles! |

It gets "1 time" and "2 times" right, and it won't go below 0.

## All 20 counters

| Add 1 | Show | Set | Chat shows |
|---|---|---|---|
| `!pickle` | `!pickles` | `!setpickle` | FluffFaceYeti has eaten 5 pickles! |
| `!crash` | `!crashes` | `!setcrash` | FluffFaceYeti has crashed 5 times! |
| `!death` | `!deaths` | `!setdeath` | FluffFaceYeti has died 5 times! |
| `!rage` | `!rages` | `!setrage` | FluffFaceYeti has raged 5 times! |
| `!fail` | `!fails` | `!setfail` | FluffFaceYeti has failed 5 times! |
| `!yell` | `!yells` | `!setyell` | FluffFaceYeti has yelled 5 times! |
| `!jumpscare` | `!jumpscares` | `!setjumpscare` | FluffFaceYeti has been jumpscared 5 times! |
| `!coffee` | `!coffees` | `!setcoffee` | FluffFaceYeti has had 5 coffees! |
| `!hydrate` | `!hydrates` | `!sethydrate` | FluffFaceYeti has hydrated 5 times! |
| `!typo` | `!typos` | `!settypo` | FluffFaceYeti has made 5 typos! |
| `!lag` | `!lags` | `!setlag` | The stream has lagged 5 times! |
| `!sneeze` | `!sneezes` | `!setsneeze` | FluffFaceYeti has sneezed 5 times! Bless you! |
| `!burp` | `!burps` | `!setburp` | FluffFaceYeti has burped 5 times! |
| `!clutch` | `!clutches` | `!setclutch` | FluffFaceYeti has clutched up 5 times! |
| `!win` | `!wins` | `!setwin` | FluffFaceYeti has won 5 times! |
| `!loss` | `!losses` | `!setloss` | FluffFaceYeti has lost 5 times! |
| `!oops` | `!oopses` | `!setoops` | FluffFaceYeti has said oops 5 times! |
| `!swear` | `!swears` | `!setswear` | FluffFaceYeti has sworn 5 times! |
| `!fall` | `!falls` | `!setfall` | FluffFaceYeti has fallen 5 times! |
| `!bug` | `!bugs` | `!setbug` | FluffFaceYeti has found 5 bugs! |

It fills your channel name in by itself.

## Permissions

You probably only want mods changing the counts. To do that:

1. Go to the **Commands** tab and open the **FFY Counters** folder.
2. Open one of the `!set...` commands, like **!setpickle**.
3. Under **Permissions**, limit it to moderators.
4. Click **OK**, and do the same for the other `!set...` ones.

While you're in there, you can give `!pickle` and friends a cooldown so chat can't spam them.

## Adding your own counter

As an example, let's make `!cat` / `!cats` / `!setcat`.

### First, add the line

1. In the **Actions** tab, open the **FFY Counters** group, then the **FFY Counters** action, and double-click **Execute C# Code**.
2. Somewhere between `EDIT BELOW` and `EDIT ABOVE`, under the other counters, add:
   ```csharp
   Counter("cat", "cats", "{streamer} has pet the cat {count} time{s}!");
   ```
   The first bit is the add command (`!cat`), the second is the show command (`!cats`), and the third is what chat sees.
3. Click **Save and Compile**.

### Then add the three commands

Do this for each of `!cat`, `!cats` and `!setcat`:

1. In the **Commands** tab, right-click and pick **Add**. Set **Name** and **Commands** to the command (e.g. `!cat`), **Location** to Start and **Group** to `FFY Counters`. Tick your platforms and **Enabled**, then click **OK**.
2. In the **Actions** tab, click the **FFY Counters** action. Right-click in the **Triggers** box, go to **Add** → **Core** → **Commands** → **Command Triggered**, pick your command and click **OK**.

### Writing what chat sees

| Placeholder | Becomes |
|---|---|
| `{streamer}` | Your channel name |
| `{count}` | The number |
| `{s}` | An "s" when the count isn't 1, so you get `1 time` but `2 times` |

If your name comes out wrong, find `StreamerName = "";` in the same code and put your name between the quotes.

## Showing a counter in OBS

Any counter can update a bit of text on screen as well. The moment someone types `!death`, `!setdeath` or `!deaths`, the text changes.

### 1. Connect Streamer.bot to OBS

You can skip this if you've already done it for something else.

In OBS, go to **Tools** → **WebSocket Server Settings**, tick **Enable WebSocket server** and click **Show Connect Info** to get the password. Then in Streamer.bot, go to the **Stream Apps** tab, right-click under **OBS** and choose **Add**. Put the password in and tick **Auto Connect**.

### 2. Add a text source in OBS

In whichever scene you want it, add a **Text (GDI+)** source and name it something like `Death Counter`. Style it however you want.

### 3. Point the counter at it

1. In the **Actions** tab, open the **FFY Counters** group, then the **FFY Counters** action, and double-click **Execute C# Code**.
2. Add the text source's name, and what you want it to say, onto the end of that counter's line:
   ```csharp
   Counter("death", "deaths", "{streamer} has died {count} time{s}!", "Death Counter", "Deaths: {count}");
   ```
   The 4th bit is the OBS text's name, and it has to match OBS exactly, capitals and all. The 5th bit is what the text shows. Leave it off if you just want the number.
3. Click **Save and Compile**.

Now type `!deaths` in chat and the text will fill in with the current count.

### Optional: fill the texts in when OBS connects

If you want your texts to be right as soon as Streamer.bot connects to OBS, without anyone typing anything, click the **FFY Counters** action in the **Actions** tab. Then right-click in the **Triggers** box, choose **Add** → **OBS Studio** → **Connected** and click **OK**.

To fill them in once right now, right-click the **FFY Counters** action and choose **Test Trigger**.

## Worth knowing

The counts are saved in the **Global Variables** tab as `counter.pickle`, `counter.crash` and so on, and you can edit or delete them there.

If you used an older version of FFY Counters, your old counts are kept. Old commands like `!removecrash` or `!crashcount` get switched off when you import, and you can delete them.

If you've added your own counters, be careful when you update. Importing replaces the code, so copy your `Counter(...)` lines somewhere safe first, paste them back in afterwards and click **Save and Compile**.

## If something's not working

**No reply:** make sure the command is switched on in the **Commands** tab and is set as a trigger on the **FFY Counters** action.

**OBS text isn't changing:** the text source's name has to match the 4th part of the counter's line exactly, capitals included. Also check OBS shows as connected in the **Stream Apps** tab. If it can't reach OBS, the **Logs** tab will say `OBS isn't connected`.

**Commands called "... (Copy)":** Streamer.bot does this when you import a command with a name that already exists. Delete the old commands and the copies, then import again.

For anything else, look for **FFY Counters** in the **Logs** tab.
