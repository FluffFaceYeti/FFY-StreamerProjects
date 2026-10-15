# FFY Gears Of War

Gears of War commands for your stream: active reloads, Gnashers, chainsaw duels, curb stomps and more. An add-on for **FFY Commands**.

> **You need FFY Commands installed first.** This add-on uses it to work. Install FFY Commands, then this.

---

## Installing

1. Make sure **FFY Commands** is already installed.
2. Download the **`FFY-Gears-Of-War`** file from this page.
3. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

Done. The commands are switched on for you. Type `!activereload` in chat to test.

**Only want some of them?** In the **Commands** tab, open the **FFY Gears Of War** folder and untick **Enabled** on the ones you don't want.

---

## The commands (20)

| Command | What it is | Example reply |
|---|---|---|
| `!activereload` | 0–100 % | @Bob, you nailed 50% of your active reloads today! |
| `!gnasher` | 0–100 % | @Bob, your Gnasher accuracy is 50% today! Wall-bounce ready. |
| `!lancer` | 0–100 % | @Bob, your Lancer chainsaw is revving at 50% today! BRRRRRR! |
| `!cog` | 0–100 % | @Bob, you're 50% COG today! Brothers to the end. |
| `!locust` | 0–100 % | @Bob, you're 50% Locust today... Emergence Day is coming. |
| `!thrashball` | 0–100 % | @Bob, your Thrashball skills are at 50% today! The Cole Train approves! |
| `!headshots` | 0–50 headshots | @Bob, you popped 25 heads today! POP! |
| `!wallbounce` | 0–100 % | @Bob, you're wall-bouncing at 50% today! Bounce bounce bounce! |
| `!downed` | 0–30 times | @Bob, you got downed 15 times today! Somebody revive this Gear! |
| `!hammerofdawn` | 0–100 % | @Bob, your Hammer of Dawn is 50% charged today! Light 'em up! |
| `!gearsweapon` | 18 choices | @Bob, your weapon of choice today is the Lancer! |
| `!gearscharacter` | 16 choices | @Bob, today you're fighting as Marcus Fenix! |
| `!locusttype` | 15 choices | @Bob, in the Locust Horde you'd be a Drone today! |
| `!execution` | 10 choices | @Bob's signature execution today: Curb Stomp! |
| `!gearsquote` | 38 choices + 7 rare (3% chance) | @Bob's Gears quote of the day: "Let's do this!" - Marcus |
| `!curbstomp @Sam` | Interaction | @Bob Curb stomped @Sam with 73% power! |
| `!revive @Sam` | Interaction | @Bob Revived @Sam with 73% power! |
| `!chainsaw @Sam` | Duel | @Bob won the chainsaw duel against @Sam (87 vs 38)! BRRRRRR! |
| `!cogofday` | COG of the Day | Who won today. Win it by getting 100% on `!cog` |
| `!locustofday` | Locust of the Day | Who won today. Win it by getting 100% on `!locust` |

---

## Changing things

Everything is in the **Actions** tab, in the **FFY Gears Of War** group. Each action is edited the same way as in FFY Commands: open it, double-click **Execute C# Code**, change the lines between `EDIT BELOW` and `EDIT ABOVE`, and click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Gears Of War Numbers** | The number commands (min, max and the reply) |
| **FFY Gears Of War Lists** | The pick-from-a-list commands |
| **FFY Gears Of War Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Gears Of War Duels** | The duels |
| **FFY Gears Of War Of The Day** | The "of the Day" titles |
| **FFY Gears Of War Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Gears Of War Setup** | Runs once on import |

To add a command of your own, follow the FFY Commands guide (adding a number or list command), and put its lines in **FFY My Number Commands** or **FFY My List Commands**, so updates never touch them.

All the FFY Commands features work with these commands too: special users, user variables, the switches, and `!top` for the interactions.

---

## Troubleshooting

- **No reply at all:** is **FFY Commands** installed? Check the **Logs** tab for `[FFY Gears Of War]`.
- **One command doesn't reply:** is it switched on in the **Commands** tab (the **FFY Gears Of War** folder)?
- **Anything else:** see the troubleshooting section in the FFY Commands guide.
