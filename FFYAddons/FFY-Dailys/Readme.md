# FFY Daily's

20 channel point redeems that each viewer can claim once a day.

```
Bob redeems "Daily Head Pat"
Chat: Bob has redeemed their daily head pat! That's 12 head pats so far.

Bob redeems it again the same day
Chat: Bob, you've already had your daily head pat today! Come back tomorrow. (Points refunded)
```

It keeps track of how many times each viewer has claimed each daily and how many days in a row they've done it. If someone tries to claim one twice in a day, they get their points back.

It doesn't need FFY Commands. It is Twitch only though, because it runs on channel points.

## The dailies

| Reward title (on Twitch) | What chat shows |
|---|---|
| **Daily Head Pat** | Bob has redeemed their daily head pat! That's 12 head pats so far. |
| **Daily Hug** | Bob has claimed their daily hug! Squeeze! (5 hugs so far) |
| **Daily Boop** | Bob got their daily boop on the snoot! Boop number 7! |
| **Daily High Five** | Bob slapped their daily high five! 3 day streak! |
| **Daily Cookie** | Bob grabbed their daily cookie! Nom nom. (9 cookies eaten) |
| **Daily Water** | Bob drank their daily glass of water! Stay hydrated! 4 day streak! |
| **Daily Stretch** | Bob did their daily stretch! Your back thanks you. |
| **Daily Pet Tax** | Bob paid their daily pet tax! The cat has been fed. (6 payments so far) |
| **Daily Check-In** | Bob checked in for the day! 10 day streak! |
| **Daily Compliment** | Bob's daily compliment: *(a random compliment)* |
| **Daily Fortune** | Bob cracked open their daily fortune cookie: *(a random fortune)* |
| **Daily Roast** | Bob asked for their daily roast: *(a random gentle roast)* |
| **Daily Dad Joke** | Bob's daily dad joke: *(a random dad joke)* |
| **Daily Vibe Check** | Bob's daily vibe check: *(a random vibe)* |
| **Daily Motivation** | Bob's daily motivation: *(a random pep talk)* |
| **Daily Snack** | Bob's daily snack is: *(a random snack)* |
| **Daily Spin** | Bob spun the daily wheel and won... *(a random prize)* |
| **Daily Lucky Number** | Bob's lucky number today is *(a random number)*! |
| **Daily Wisdom** | Bob's daily wisdom: *(a random wise-ish saying)* |
| **Daily Chaos** | Bob unleashed their daily chaos: *(something chaotic)* |

You don't need to use all of them. Only set up the ones you like.

## Setting it up

This one takes a few more steps than my other add-ons, because Twitch rewards have to be made by hand.

### 1. Import it

Download the **`FFY-Dailys`** file from this page. In Streamer.bot, click **Import** at the top, drag the file into the box and click **Import**.

### 2. Make the channel point rewards

Streamer.bot can't make the rewards for you, so you'll need to make one for each daily you want:

1. In Streamer.bot, go to **Platforms** → **Twitch** → **Channel Point Rewards**.
2. Right-click in the list and choose **Add**.
3. Set the **Title** to the reward title from the table above, e.g. `Daily Head Pat`. Capitals don't matter but the spelling has to be exact.
4. Pick a cost and anything else you want (colour, prompt, cooldown), then click **OK**.

> Make the rewards in Streamer.bot rather than on the Twitch website. Twitch only lets whichever app made a reward refund it. Rewards made on the website will still work, but nobody gets their points back if they try twice in one day.

### 3. Connect each reward

1. In the **Actions** tab, open the **FFY Daily's** group and click the **FFY Daily's** action.
2. Right-click in the **Triggers** box and go to **Add** → **Twitch** → **Channel Reward** → **Reward Redemption**.
3. Pick the reward (e.g. **Daily Head Pat**) and click **OK**.

Do that for every daily reward you made.

### 4. Check it's working

Right-click the **FFY Daily's** action and choose **Run Now**. A pop-up will tell you how many of the 20 rewards it found and which ones are missing. After that, redeem one on Twitch to test it properly.

## Changing the messages or adding your own

In the **Actions** tab, open **FFY Daily's** and double-click **Execute C# Code**. Between `EDIT BELOW` and `EDIT ABOVE`, every daily is one line like this:

```csharp
Daily("Daily Head Pat", "{user} has redeemed their daily head pat! That's {total} head pat{s} so far.");
```

The first part is the reward title, which has to match the reward on Twitch. The second part is what chat sees. Click **Save and Compile** after changing anything.

| Placeholder | Becomes |
|---|---|
| `{user}` | The viewer who redeemed it |
| `{total}` | How many times they've had this daily |
| `{streak}` | How many days in a row they've had it |
| `{s}` | An "s" when `{total}` isn't 1 |
| `{pick}` | One of the random picks listed after the message (see below) |

For random picks, put the choices after the message, separated by commas, and put `{pick}` where you want one to go:

```csharp
Daily("Daily Pizza", "{user}'s daily pizza topping: {pick}", "Pepperoni", "Pineapple", "Extra cheese", "Anchovies (brave)");
```

To add a completely new daily, add a `Daily(...)` line for it, make a reward with the same title (step 2) and connect it (step 3).

The "already claimed" message is the `AlreadyMessage` line. `{reward}` in there is the reward's name.

## Worth knowing

A "day" goes by your PC's clock, so it resets at midnight.

Totals and streaks are saved on each viewer. You can see them in **Global Variables** → **Persisted User Globals** → **Twitch** → their username. They're the ones that start with `ffyDaily.`.

If someone misses a day, their streak goes back to 1.

## If something's not working

**Nothing happens when someone redeems:** check the reward is added as a trigger on the **FFY Daily's** action (step 3).

**The Logs tab says "No Daily(...) line matches the reward":** the reward's title on Twitch doesn't match any of the `Daily(...)` lines. It's usually a spelling thing.

**People aren't getting refunded when they try twice:** that reward was made on the Twitch website. Make it in Streamer.bot instead (step 2).
