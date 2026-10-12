# FFY Counters

Keep a running count of anything, like how many pickles you've eaten, or how many times you've died, raged or crashed.

```
Viewer: !pickle
Chat: FluffFaceYeti has eaten 5 pickles!
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- Counts are **kept forever**. They don't reset at midnight, and they survive a restart.

---

## Installing

1. Download the **`FFY-Counters`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!pickle` in chat to test.

Then **make the `!set...` commands mods only** (see [Permissions](#permissions)), so chat can't change your counts.

---

## How it works

Every counter has **three commands**. Here they are for pickles:

| Command | What it does | Chat shows |
|---|---|---|
| `!pickle` | Adds 1 | FluffFaceYeti has eaten 6 pickles! |
| `!pickles` | Shows the count | FluffFaceYeti has eaten 6 pickles! |
| `!setpickle 10` | Sets it to 10 | FluffFaceYeti has eaten 10 pickles! |
| `!setpickle -1` | Takes 1 off | FluffFaceYeti has eaten 9 pickles! |
| `!setpickle +3` | Adds 3 | FluffFaceYeti has eaten 12 pickles! |

It always says `1 time` but `2 times`, and never goes below 0.

---

## The 20 counters

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

Your channel name is filled in automatically.

---

## Permissions

You'll probably want only mods to change counts:

1. Click the **Commands** tab and open the **FFY Counters** folder.
2. Open a `!set...` command, e.g. **!setpickle**.
3. In its **Permissions** settings, limit it to moderators.
4. Click **OK**.

You can also give `!pickle` and the others a **cooldown** there, so chat can't spam them.

---

## Adding your own counter

We'll add `!cat` / `!cats` / `!setcat`.

### Step 1: add the line

1. **Actions tab** → **FFY Counters** group → **FFY Counters** → double-click **Execute C# Code**.
2. Between `EDIT BELOW` and `EDIT ABOVE`, add a line under the others:
   ```csharp
   Counter("cat", "cats", "{streamer} has pet the cat {count} time{s}!");
   ```
   - 1st part: the **add** command (`!cat`)
   - 2nd part: the **show** command (`!cats`)
   - 3rd part: **what chat says**
3. Click **Save and Compile**.

### Step 2: add the three commands

For `!cat`, `!cats` and `!setcat`:

1. **Commands tab:** right-click → **Add**. Set **Name** and **Commands** to e.g. `!cat`, **Location** to Start, **Group** to `FFY Counters`, tick your platforms and **Enabled**, then click **OK**.
2. **Actions tab:** click the **FFY Counters** action. In the **Triggers** box, right-click → **Add** → **Core** → **Commands** → **Command Triggered**, pick the command, and click **OK**.

### Writing the sentence

| Placeholder | Becomes |
|---|---|
| `{streamer}` | Your channel name |
| `{count}` | The number |
| `{s}` | An "s" when the count isn't 1, so you get `1 time` but `2 times` |

**Your name shows wrong?** Find `StreamerName = "";` in the same code and type your name between the quote marks.

---

## Good to know

- **Counts are saved** in the **Global Variables** tab as `counter.pickle`, `counter.crash` and so on. You can edit or delete them there.
- **Coming from an older FFY Counters?** Your old counts are kept, and old commands like `!removecrash` or `!crashcount` are switched off when you import. You can delete them.

---

## Troubleshooting

- **No reply:** is the command switched on in the **Commands** tab, and is it a trigger on the **FFY Counters** action?
- **Commands named "... (Copy)":** Streamer.bot adds "(Copy)" when you import a command whose name already exists. Delete the old commands, delete the copies, and import again.
- **Anything else:** check the **Logs** tab for **FFY Counters**.
