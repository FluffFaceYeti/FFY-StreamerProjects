# FFY_AutoShoutout

Give your friends a shoutout automatically. Add their names, and the first time each of them chats during your stream, they get a shoutout in chat, on an OBS overlay, or both.

```
Bob: hey hey!
Chat: Go check out @Bob at https://twitch.tv/bob! They were last playing Sea of Thieves.
Bob: how's the stream going?
(nothing, Bob has had their shoutout for this stream)
```

- Works on its own. You don't need FFY Commands.
- Works on **Twitch, Kick and YouTube**.
- Give anyone their **own custom message**.
- Keep it in chat, or switch on the **OBS overlay** and pick its colours and what it shows.

On the overlay it looks like this:

```
Please send some love to Bob!
Last playing: Sea of Thieves
Followage: 6 years 2 months
twitch.tv/bob
```

---

## Installing

1. Download the **`FFY_AutoShoutout`** file from this page.
2. In Streamer.bot, click **Import** in the bar at the top, drag and drop the file into the box, and click **Import**.
3. Open the **FFY_AutoShoutout** action in the **Actions** tab, double-click its **Execute C# Code** sub-action, and add your people (see below).
4. Click **Save and Compile**.

The chat and Stream Online / Offline triggers for Twitch, Kick and YouTube are already set up.

---

## Adding people

Everything you edit is at the very top of the code, in the `Settings` part. Replace the two examples with your own people, one line each:

```csharp
Shoutout("Bob");
Shoutout("Mia");
Shoutout("Sam", "Everybody give {user} a follow, they're the best baker on Twitch! {link}");
```

- `Shoutout("Bob");` uses the default message.
- `Shoutout("Sam", "...");` gives them their own message.
- Capital letters and a leading `@` don't matter.

After any change, click **Save and Compile**.

### Words you can use in a message

| Word | Becomes |
|---|---|
| `{user}` | Their name. In chat it's `@Bob`, on the overlay it's `Bob` |
| `{link}` | Their channel link |
| `{game}` | What they last played (Twitch only) |
| `{title}` | Their stream title (Twitch only) |

Change `DefaultMessage` to change the chat message for everyone without their own. `NoGameText` fills in `{game}` and `{title}` when there isn't one, so nothing is left blank.

`OverlayMessage` is the main line on the overlay, for everyone without their own message. Someone with their own message shows it there too, with `{link}` left out, because the card has its own link line.

---

## The switches

`true` = on, `false` = off.

| Switch | Starts as | What it does |
|---|---|---|
| `ChatMessage` | `true` | Sends the shoutout in chat. |
| `Overlay` | `true` | Shows the shoutout on the OBS overlay. Set it to `false` to keep everything in chat. |
| `TwitchShoutout` | `false` | Also uses Twitch's own `/shoutout`. Twitch only allows one every 2 minutes and only while you're live, so some may not go through. |
| `OnlyWhileLive` | `true` | Only gives shoutouts while you're live. Set it to `false` to give them any time. |

`StreamRestartMinutes` (starts at 15): if your stream drops and comes back within this many minutes, it counts as the same stream, so nobody gets a second shoutout.

**How it knows you're live:** Streamer.bot's Stream Online trigger, or OBS streaming if Streamer.bot is connected to OBS. If you open Streamer.bot after you've gone live and it isn't connected to OBS, shoutouts stay off until the next Stream Online. Set `OnlyWhileLive = false;` if that happens to you.

---

## The overlay

You can skip this if you're keeping it in chat.

1. In Streamer.bot, go to **Servers/Clients > WebSocket Server**, and make sure it's running.
2. Download **`FFY_AutoShoutout-Overlay.html`** and **`FFY_AutoShoutout-Settings.html`** and keep them in the same folder.
3. Open **`FFY_AutoShoutout-Settings.html`** in your browser. Flip the switches and pick your colours, and the preview updates as you go.
4. Click **Copy link for OBS**.
5. In OBS, add a **Browser** source, paste the link into **URL** (leave **Local file** unticked), and set the size to **1920 x 1080**.

If you change a setting later, copy the link again and paste it over the old one. The old link keeps the old look.

### What you can change

- **Show or hide:** picture, heading, main line, last game played, followage, channel link
- **Colours:** card background and how solid it is, accent, main line, details
- **Style:** font, picture shape, rounded corners, heading text
- **Placement:** position, size, seconds on screen, animation (slide, pop or fade)

If several people turn up at once, their shoutouts show one after another, so nobody gets missed.

**Followage** is how long they've followed your channel, from Twitch. The line is left out if they don't follow you, on Kick and YouTube, or if Twitch doesn't answer. If it never shows for anyone, Streamer.bot's log says why, and your Twitch broadcaster account in Streamer.bot may need logging in again.

---

## Testing

| Command | What it does |
|---|---|
| `!testshoutout` | Mods only. Runs a shoutout for the first person on your list. |
| `!testshoutout Bob` | Mods only. Runs a shoutout for Bob, using their own message if they have one. |

A test uses your chat and overlay switches, but doesn't use up anyone's shoutout and doesn't send a Twitch `/shoutout`. It works even when you're offline.

---

## When does everyone get another shoutout?

Every new stream. The list clears when Stream Online fires, so each person gets one shoutout per stream.

## Troubleshooting

| Problem | Try this |
|---|---|
| Nobody gets a shoutout | Are you live? Set `OnlyWhileLive = false;` to check. Did you click **Save and Compile**? |
| One person doesn't get one | Check the spelling of their name. They only get one per stream, so try `!testshoutout name`. |
| The overlay shows nothing | Is `Overlay = true;`? Is the WebSocket Server running? Any problem with the connection shows in the bottom corner of the overlay. |
| The overlay says the port is OBS's | Use the port from Streamer.bot's WebSocket Server (usually 8080), not OBS's. |
| The overlay wants a password | Add it in the settings page and copy the link again. |
| There's a letter instead of a picture | There's no picture for that person, or it couldn't load. This can happen on Kick and YouTube. |
