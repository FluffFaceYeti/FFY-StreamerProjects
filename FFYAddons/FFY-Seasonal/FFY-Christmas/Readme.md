# FFY Christmas

Christmas commands for chat, and the star of the show is **Santa's naughty or nice list**.

This plugs into **FFY Commands**, so get that installed first.

## Installing

Grab the **`FFY-Christmas`** file from this page, then in Streamer.bot hit **Import** at the top, drop the file in and click **Import**.

The commands switch on by themselves, so you can type `!grinch` straight away to check it's working.

You can turn off any you don't like. Find them in the **FFY Christmas** folder in the **Commands** tab and untick **Enabled**.

## Commands (16)

| Command | What it is | Example reply |
|---|---|---|
| `!grinch` | 0–100 % | @Bob, you're 50% Grinch today! Hands off the presents! |
| `!elf` | 0–100 % | @Bob, you're 50% elf today! Back to the workshop! |
| `!festive` | 0–100 % | @Bob, your festive spirit is at 50% today! |
| `!snowman` | 1–300 cm | @Bob, you built a 151cm snowman today! |
| `!eggnog` | 0–20 glasses | @Bob, you've had 10 glasses of eggnog today! Steady on! |
| `!sprouts` | 0–100 % | @Bob, you love sprouts 50% today! |
| `!present` | 12 choices | @Bob, your Christmas present today is: Socks (again)! |
| `!elfname` | 10 choices | @Bob, your elf name today is: Jingle Sparklesocks! |
| `!reindeer` | 10 choices | @Bob, you're pulling the sleigh as Dasher today! |
| `!jumper` | 8 choices | @Bob, your Christmas jumper today has a Flashing Rudolph Nose on it! |
| `!cracker` | 6 choices | @Bob pulled a cracker! Today's joke: What do you call a reindeer with no eyes? No idea! |
| `!snowball @Sam` | Interaction | @Bob Threw a snowball at @Sam with 73% power! |
| `!giftwrap @Sam` | Interaction | @Bob Gift-wrapped @Sam with 73% power! |
| `!grinchofday` | Grinch of the Day | Who won today. Win it by getting 100% on `!grinch` |
| `!santa` / `!santa @Sam` | Naughty or nice | Ho ho ho! Santa checked the list... @Sam is on the **NICE list**! |
| `!santastats` / `!santastats @Sam` | Santa history | Santa Stats for @Sam \| Nice: 3 \| Naughty: 5 \| Last result: NAUGHTY |

## Santa's naughty or nice list

Type `!santa` (or `!santa @someone`) and Santa checks his list to see if they're **NICE** or **NAUGHTY**. `!santastats` shows everyone's track record, and that's kept forever, so there's no hiding.

By default you get a new result every day. To change how long a result sticks, open **FFY Santa** (it's in the **FFY Christmas** group in the Actions tab) and change `resultDays`:

```csharp
Set("resultDays", 1);   // a new result every day
Set("resultDays", 7);   // the same result for a week
Set("resultDays", 25);  // one result that lasts all of December
```

| Setting | What it does |
|---|---|
| `resultDays` | How many days a NICE or NAUGHTY result lasts. `1` = every day. |
| `naughtyChance` | The chance of NAUGHTY, out of 100. `40` means 40%. |
| `alwaysNice` | People who are always NICE (lowercase usernames): `Set("alwaysNice", List("yourname", "yourmod"));` |
| `message` | The reply. Use `{target}` and `{result}`. |
| `statsMessage` | The `!santastats` reply. Use `{target}`, `{nice}`, `{naughty}` and `{last}`. |
| `noHistoryMessage` | Shown when someone has no Santa history yet. |

## Making changes

It all lives in the **Actions** tab under the **FFY Christmas** group. Open an action, double-click **Execute C# Code**, change whatever's between `EDIT BELOW` and `EDIT ABOVE`, then click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Christmas Numbers** | The number commands (min, max and the reply) |
| **FFY Christmas Lists** | The pick-from-a-list commands |
| **FFY Christmas Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Christmas Of The Day** | The "of the Day" titles |
| **FFY Santa** | Santa's settings |
| **FFY Christmas Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Christmas Setup** | Runs once on import |

If you want to add your own, follow the bit in the FFY Commands guide about adding a number or list command, and put it in **FFY My Number Commands** or **FFY My List Commands**. That way an update won't wipe it.

Special users, user variables, the switches and `!top` for the interactions from FFY Commands all work with these too.

## If something's not working

No replies at all usually means **FFY Commands** isn't installed. The **Logs** tab will show `[FFY Christmas]` lines if the pack is running. If just one command isn't replying, check it's ticked in the **FFY Christmas** folder in the **Commands** tab.

For anything else, there's a troubleshooting section in the FFY Commands guide.
