#  FFY Christmas

Festive, silly Christmas commands for your stream, including **Santa's naughty or nice list**. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Christmas`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!grinch` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Christmas** folder and untick **Enabled** on the ones you don't want.

---

## The commands (16)

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

---

## Santa's naughty or nice list

`!santa` (or `!santa @someone`) puts them on the **NICE** or **NAUGHTY** list. `!santastats` shows their history, which is kept forever.

**How long a result lasts:** open **FFY Santa** (Actions tab → **FFY Christmas** group) and change `resultDays`:

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

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Christmas** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Christmas Numbers** | The number commands (min, max and the reply) |
| **FFY Christmas Lists** | The pick-from-a-list commands |
| **FFY Christmas Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Christmas Of The Day** | The "of the Day" titles |
| **FFY Santa** | Santa's settings |
| **FFY Christmas Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Christmas Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Christmas]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Christmas** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
