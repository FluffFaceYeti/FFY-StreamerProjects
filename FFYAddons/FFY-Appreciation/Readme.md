# FFY_Appreciation

Let your chat show each other some love. Viewers hug, kiss, high-five, wave and appreciate each other, and it pops up on stream with both of their pictures and emojis floating everywhere.

```
Bob: !hug @Mia
Chat: 🤗 @Bob gave @Mia a big hug! That's 12 hugs for Mia.
Bob: !appreciate @Mia you always make me laugh
Chat: ❤️ @Bob appreciates @Mia! you always make me laugh That's 3 appreciations for Mia.
```

It works on its own, so you don't need FFY Commands. Twitch only.

## Installing

> **⚠️ Warning: this clashes with FFY Interactions.** Both have `!hug`, `!kiss`, `!highfive`, `!boop` and `!pat`. If you've got both, these five show up as `!hug (Copy)` and so on in the **FFY_Appreciation** folder, and both packs answer when someone uses them.
>
> **To fix it:** go to the **FFY Interactions** folder in the **Commands** tab and untick **Enabled** on those five. The `(Copy)` ones are the ones you want to keep, and that bit of the name doesn't matter.

In Streamer.bot, click **Import** at the top, drag in the **`FFY_Appreciation`** file and click **Import**. The commands switch on by themselves, and you'll find them in the **FFY_Appreciation** folder in the **Commands** tab, where you can change their cooldowns and permissions.

## The commands

| Command | What it does |
|---|---|
| `!appreciate @name message` | Tells someone you appreciate them. The message is optional and shows on stream. |
| `!hug @name` | A big hug |
| `!kiss @name` | A kiss |
| `!highfive @name` | A high five |
| `!boop @name` | A boop on the nose |
| `!pat @name` | A head pat |
| `!cuddle @name` | A cuddle |
| `!wave`, `!airhug`, `!thumbsup` and more | See **The gentle commands** below |
| `!appreciated @name` | How much love someone's had. Leave the name off to see your own. |
| `!mostappreciated` | The top 5 most appreciated people |
| `!testappreciation` | Mods and you only. Sends a test card to the overlay. |

Leave the name off, or use `everyone`, and it goes to the whole chat. Each viewer can use one of these every 30 seconds. You don't have a cooldown.

## The gentle commands

Not everyone likes hugs and kisses, even pretend ones, and not everyone wants a big animation or feels like replying. These were made with autistic and other neurodivergent viewers in mind, but they're for anyone. There's no touching in any of them, and nobody has to reply. They use a calm card that fades in, with no floating emojis or moving pictures.

| Command | What it does |
|---|---|
| `!wave @name` | A friendly wave |
| `!airhug @name` | A hug with no touching |
| `!thumbsup @name` | A thumbs up, and they don't need to reply |
| `!stim @name` | Happily stimming alongside someone |
| `!parallel @name` | Hanging out quietly next to someone, with no talking needed |
| `!infodump @name` | Lets someone know you'd love to hear about their special interest |
| `!spoons @name` | Gives someone a spare spoon, for when their energy's low |
| `!fidget @name` | Offers someone a fidget toy |
| `!blanket @name` | Offers someone a cosy weighted blanket |
| `!headphones @name` | Offers someone noise-cancelling headphones |

Like the others, leave the name off and it goes to everyone.

Want every card calm? Switch on **Calm cards for everything** on the settings page.

To make one of your own commands calm, use `Gentle` instead of `Add` at the start of its line.

## Changing things

Open the **FFY_Appreciation** action in the **Actions** tab, double-click **Execute C# Code**, edit the `Settings` part at the top and click **Save and Compile**.

| Setting | Starts as | What it does |
|---|---|---|
| `ChatMessages` | `true` | Replies in chat. |
| `Overlay` | `true` | Sends cards to the overlay. |
| `ViewerMessages` | `true` | Lets viewers add a message to `!appreciate`. Web links get removed. |
| `CooldownSeconds` | 30 | How long a viewer waits between commands. |
| `MessageLength` | 100 | The longest a viewer's message can be. |
| `TopCount` | 5 | How many people show on `!mostappreciated`. |

Viewer messages show on your stream without you checking them first, so set `ViewerMessages = false;` if you'd rather not have that.

To reword something, change its `Add` or `Message` line. To say something when someone's on cooldown, fill in the empty `wait` message. You can use `{user}` and `{seconds}` in it.

**Adding your own, like `!bow`:**

1. Add a line to the `Settings` part, copying the others:

   ```
   Add("bow", "🙇", "bow", "bows", "{user} bowed to {target}!", "{user} bowed to everyone!", "{user} bowed to a mirror.");
   ```
2. In the **Commands** tab, add a command called `!bow`, tick **Enabled** and set it to **Start** so people can add a name after it.
3. In the **Actions** tab, add that command as a trigger on the **FFY_Appreciation** action.

## The overlay

1. In Streamer.bot, go to **Servers/Clients > WebSocket Server** and make sure it's running.
2. Keep **`FFY_Appreciation-Overlay.html`** and **`FFY_Appreciation-Settings.html`** in the same folder, and open the settings page in your browser.
3. Pick what shows and how it looks. There are six colour themes to start from, and the preview updates as you go.
4. Click **Copy link for OBS**.
5. In OBS, add a **Browser** source, paste the link into **URL** (leave **Local file** unticked) and set the size to **1920 x 1080**.
6. Type `!testappreciation` in chat to check it's working.

**Address:** use `127.0.0.1` if OBS and Streamer.bot are on the same PC. On a dual PC setup, use the IP address of the PC running Streamer.bot.

If lots of cards come in at once they show one after another, and it holds up to 3 in the queue. Any more than that get skipped on the overlay, but they still count. Cards with others waiting behind them fade in calmly and stay up for 3 seconds at most, which stops a burst of commands from dragging down your OBS frame rate.

## Troubleshooting

| Problem | Try this |
|---|---|
| `!hug` gets two replies, or a "73% power" reply | That's FFY Interactions as well. See the warning under **Installing**. |
| The overlay shows nothing | Check the corner of the overlay for a connection message, and that the address is right for your setup. |
| It shows the old settings | Copy the link again and paste it over the old one. |
| "I can't find anyone called..." | Check the spelling. It has to be a real Twitch name. |
