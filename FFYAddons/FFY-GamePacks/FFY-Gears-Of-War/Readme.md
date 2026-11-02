# FFY Gears Of War

Gears of War commands. Active reloads, Gnashers, chainsaw duels, curb stomps and plenty more.

This plugs into **FFY Commands**, so get that installed first.

## Installing

Grab the **`FFY-Gears-Of-War`** file from this page, then in Streamer.bot hit **Import** at the top, drop the file in and click **Import**.

The commands switch on by themselves, so you can type `!activereload` straight away to check it's working.

You can turn off any you don't like. Find them in the **FFY Gears Of War** folder in the **Commands** tab and untick **Enabled**.

## Commands (20)

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

## Making changes

It all lives in the **Actions** tab under the **FFY Gears Of War** group. Open an action, double-click **Execute C# Code**, change whatever's between `EDIT BELOW` and `EDIT ABOVE`, then click **Save and Compile**.

| Action | What's in it |
|---|---|
| **FFY Gears Of War Numbers** | The number commands (min, max and the reply) |
| **FFY Gears Of War Lists** | The pick-from-a-list commands |
| **FFY Gears Of War Interactions**, **Action Words**, **Top Titles** | The interactions |
| **FFY Gears Of War Duels** | The duels |
| **FFY Gears Of War Of The Day** | The "of the Day" titles |
| **FFY Gears Of War Triggers** | Connects the commands to FFY Commands. Don't edit its code |
| **FFY Gears Of War Setup** | Runs once on import |

If you want to add your own, follow the bit in the FFY Commands guide about adding a number or list command, and put it in **FFY My Number Commands** or **FFY My List Commands**. That way an update won't wipe it.

Special users, user variables, the switches and `!top` for the interactions from FFY Commands all work with these too.

## If something's not working

No replies at all usually means **FFY Commands** isn't installed. The **Logs** tab will show `[FFY Gears Of War]` lines if the pack is running. If just one command isn't replying, check it's ticked in the **FFY Gears Of War** folder in the **Commands** tab.

For anything else, there's a troubleshooting section in the FFY Commands guide.
