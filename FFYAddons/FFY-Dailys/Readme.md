# FFY Daily's

**20 daily channel point redeems** for Twitch. Each viewer can claim each one **once a day**:

```
Bob redeems "Daily Head Pat"
Chat: Bob has redeemed their daily head pat! That's 12 head pats so far.

Bob redeems it again the same day
Chat: Bob, you've already had your daily head pat today! Come back tomorrow. (Points refunded)
```

- Works on its own. You don't need FFY Commands.
- **Twitch only**, because it uses channel points.
- Keeps each viewer's **total** and **day streak** for every daily.
- If someone tries twice in one day, their points are **refunded**.

---

## The 20 daily's

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

You don't have to use all 20. Just set up the ones you want.

---

## Installing

### Step 1: import it

1. Download the **`FFY-Dailys`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.

### Step 2: create the channel point rewards

Streamer.bot can't create rewards by itself, so make one for each daily you want:

1. In Streamer.bot, go to **Platforms** → **Twitch** → **Channel Point Rewards**.
2. **Right-click** in the list and choose **Add**.
3. Set the **Title** to **exactly** the reward title from the table above, e.g. `Daily Head Pat`. Capitals don't matter, but the spelling does.
4. Set the **cost**, and anything else you like (colour, prompt, cooldown).
5. Click **OK**.

> **Create the rewards in Streamer.bot, not on the Twitch website.** Twitch only lets the app that created a reward refund or complete it. Rewards made on the Twitch website still work, but nobody gets a refund if they try twice in a day.

### Step 3: connect each reward

1. Click the **Actions** tab, open the **FFY Daily's** group, and click the **FFY Daily's** action.
2. In the **Triggers** box, **right-click** → **Add** → **Twitch** → **Channel Reward** → **Reward Redemption**.
3. Pick the reward, e.g. **Daily Head Pat**, and click **OK**.
4. Do this for each daily reward you created.

### Step 4: check it

Right-click the **FFY Daily's** action and choose **Run Now**. A pop-up tells you how many of the 20 rewards it found, and which are missing. Then redeem one on Twitch to test.

---

## Changing the messages or adding your own

1. **Actions tab** → **FFY Daily's** → double-click **Execute C# Code**.
2. Between `EDIT BELOW` and `EDIT ABOVE`, each daily is one line:
   ```csharp
   Daily("Daily Head Pat", "{user} has redeemed their daily head pat! That's {total} head pat{s} so far.");
   ```
   - The **first part** is the reward title, matching the reward on Twitch.
   - The **second part** is what chat shows.
3. Click **Save and Compile**.

| Placeholder | Becomes |
|---|---|
| `{user}` | The viewer who redeemed it |
| `{total}` | How many times they've had this daily |
| `{streak}` | How many days in a row they've had it |
| `{s}` | An "s" when `{total}` isn't 1 |
| `{pick}` | One of the random picks listed after the message (see below) |

**Random picks:** add choices after the message, separated by commas, and use `{pick}` where one should go:

```csharp
Daily("Daily Pizza", "{user}'s daily pizza topping: {pick}", "Pepperoni", "Pineapple", "Extra cheese", "Anchovies (brave)");
```

**Adding a brand-new daily:** add its `Daily(...)` line, create a reward with the same title (Step 2), and connect it (Step 3).

**The "already claimed" message:** change the `AlreadyMessage` line. `{reward}` is the reward's name.

---

## Good to know

- **A "day"** follows your PC's clock and resets at midnight.
- **Totals and streaks** are saved on each viewer. To see them, go to **Global Variables** → **Persisted User Globals** → **Twitch** → their username. They're the ones starting `ffyDaily.`.
- **Missing a day** resets the streak to 1.

---

## Troubleshooting

- **Nothing happens when someone redeems:** is the reward added as a trigger on the **FFY Daily's** action (Step 3)?
- **The Logs tab says "No Daily(...) line matches the reward":** the reward's title on Twitch doesn't match any `Daily(...)` line. Check the spelling.
- **Points aren't refunded on a second try:** the reward was made on the Twitch website. Make it in Streamer.bot instead (Step 2).
