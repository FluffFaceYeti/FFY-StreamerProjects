# FFY Plugin for OBS Studio

A Twitch-powered OBS automation plugin that shows and hides sources when something happens on your stream: chat commands, bot replies, channel point redemptions, follows, raids, bits, and viewer walk-ons.

Requires **OBS Studio 31 or newer** on **Windows (64-bit)**.

---

## Install Guide

1. Close OBS.
2. Copy `ffy-plugin.dll` from this folder into:

   ```text
   C:\Program Files\obs-studio\obs-plugins\64bit
   ```

   Windows will ask for admin permission. (`ffy-plugin.pdb` is optional. It only makes crash reports readable.)
3. Open OBS, click **Docks** and you will now see **FFY Plugin**.

**Updating:** close OBS and replace `ffy-plugin.dll`. Your rules, walk-ons and Twitch login are stored separately and are kept.

Only install one copy. If you previously put the plugin in `C:\ProgramData\obs-studio\plugins\ffy-plugin`, delete that folder, because OBS can't load the same plugin twice.

---

# Connecting Twitch

The Twitch box at the top of the dock has one button.

## Log in with Twitch (recommended)

1. Click **Log in with Twitch**.
2. Your browser opens on Twitch with a short code. Check it matches the code shown in the dock, then click **Authorize**.
3. The plugin connects to your channel automatically.

Log in with the **channel owner's** Twitch account. Some features only work for the owner (see the table below).

Once connected, the status line shows what's active, for example:

```text
Connected (yourchannel) as yourchannel: chat, channel points, bits, follows, raids
```

The login is stored encrypted for your Windows account, checked every hour and renewed automatically. Click **Log Out** to remove it.

## Without logging in (read-only)

Click **Choose channel** in the Twitch box and enter a channel name. The plugin reads chat anonymously:

* Chat commands, bot reply triggers and walk-ons work.
* Channel points, follows, raids, bits and chat replies don't.

## What needs what

| Feature                     | Not logged in | Logged in | Logged in as the channel owner |
| --------------------------- | :-----------: | :-------: | :----------------------------: |
| Chat commands and walk-ons  | ✓             | ✓         | ✓                              |
| Chat replies                |               | ✓         | ✓                              |
| Raids                       |               | ✓         | ✓                              |
| Follows                     |               | mods only | ✓                              |
| Channel points and bits     |               |           | ✓                              |

To watch a different channel, click **Change channel** in the Twitch box.

---

# Features

NOTE: Sources are found directly in your scenes, inside groups, and as nested scenes. The plugin toggles the scene item itself, so a source has to be *in* a scene (or group) to be shown.

## Command-Based Source Triggers

Trigger OBS sources from Twitch chat commands.

Example:

```text
!waffles
```

Shows the selected OBS source for the configured duration.

Anything after the command is ignored, so `!waffles @friend` works too.

---

## Username-Specific Commands

Restrict commands to a specific Twitch user.

Example:

| Command | Username | Result                               |
| ------- | -------- | ------------------------------------ |
| pickle  | username | Only username can trigger the source |
| cry     | username | Only username can trigger the source |

Example:

```text
!pickle
```

Only triggers if sent by the configured user.

If you also have a general `!pickle` rule, that user gets their own version and everyone else gets the general one.

Use the viewer's Twitch **login name** (the one in their channel URL), not their display name.

---

## Trigger Value Commands (Bot Reply Contains)

Trigger sources based on a bot's reply.

Useful for all the available commands in the project and much more.

Example Rule:

| Command | Bot reply contains |
| ------- | ------------------ |
| pp      | 15 inches          |

Workflow:

User types:

```text
!pp
```

Bot replies:

```text
Your PP is 15 inches today!
```

The plugin sees:

```text
15 inches
```

inside the bot message and triggers the source.

Notes:

* The bot must reply within **30 seconds** of the command.
* Matching ignores upper/lower case, but the text must otherwise appear exactly. If your command replies with, for example, "You have hit 8/10 shots" and you want it to trigger for 10/10, your trigger must be `10/10`.
* If several viewers use commands at once, each bot reply is matched to the right viewer's command.
* The reply has to come from a known bot account (StreamElements, Nightbot, Streamlabs, Fossabot, Mix It Up, Streamer.bot, Moobot, Wizebot and others). A bot running under a custom account name isn't recognised.

---

## Instant Commands

Leave **Bot reply contains** empty.

Example:

| Command | Bot reply contains |
| ------- | ------------------ |
| shots   | *(empty)*          |

User types:

```text
!shots
```

The source plays straight away, without waiting for a bot.

---

## Channel Points, Follows, Raids and Bits

Choose the event in **Trigger on**. These need you to be logged in (see the table above).

| Trigger on     | What to fill in                                                    |
| -------------- | ------------------------------------------------------------------ |
| Channel points | **Reward name**, exactly as it appears on Twitch (case doesn't matter) |
| Follow         | Nothing extra                                                      |
| Raid           | **Minimum viewers** (optional); **Only from channel** (optional)   |
| Bits           | **Minimum bits** (optional)                                        |

**Tiers:** bits and raids play only the highest minimum that's reached. With rules at 100 bits and 1000 bits, a 1500-bit cheer plays only the 1000 one.

---

## Who Can Use It

For chat commands, **Who can use it** limits a rule to Everyone, Subscriber, VIP, Moderator or Broadcaster. Higher roles always qualify, so a Moderator rule also works for the broadcaster.

---

## Cooldowns

* **Cooldown:** after the rule plays, nobody can trigger it again for this long.
* **Per viewer:** each viewer has to wait this long before triggering it again.

Set either one to **Off** to disable it.

---

## Chat Replies

Type a message in **Chat reply** and the plugin posts it in chat when the rule plays. This needs you to be logged in.

| Placeholder | Becomes                                         |
| ----------- | ----------------------------------------------- |
| `{user}`    | The viewer's name                               |
| `{amount}`  | Bits cheered, raid viewers or channel point cost |

Example:

```text
Thanks for the {amount} bits, {user}!
```

Replies are limited to 15 every 30 seconds so you stay inside Twitch's chat limits.

---

## Multiple Source Support

A rule can control multiple OBS sources.

Tick one or more sources in the Sources list when creating a rule. When triggered, all ticked sources are shown together.

Any source with video can be used: images, media, VLC, browser sources, text, captures, colour sources, scenes and groups.

If you rename a source in OBS, your rules and walk-ons update automatically. A source that no longer exists shows as **(not in OBS)** and works again if you bring it back.

---

## Hide When Video Ends

Tick **Hide when video ends** to hide everything in the rule once its video finishes, instead of guessing the duration. The **Show for** time then becomes a maximum (0 = no limit).

Videos always restart from the beginning when they're triggered.

---

# Walk-On System

The walk-on system plays a source automatically the first time a viewer chats each stream.

Example:

| Username | Source         |
| -------- | -------------- |
| username | Entrance Video |
| username | Sparkles       |

When that user sends a message in chat:

```text
Hello everyone!
```

their configured walk-on source is shown automatically.

* If several walk-ons happen at once, they play **one after another** instead of interrupting each other.
* A walk-on can have a **Chat reply** too, e.g. `Welcome in, {user}!`.
* Click **Reset Walk-Ons** to let every walk-on play again (handy for testing).

---

# Creating a Rule

1. Open the FFY Plugin dock and go to the **Rules** tab.
2. Choose what triggers it in **Trigger on**.
3. Enter a **Command** (with or without the `!`) or the **Reward name**.
4. (Optional) Fill in **Bot reply contains**, **Username**, **Who can use it**, **Cooldown** and **Chat reply**.
5. Tick one or more sources.
6. Set **Show for** (in milliseconds; 5000 = 5 seconds), or tick **Hide when video ends**.
7. Click **Test** to preview it, then **Add as New**.

## Editing a Rule

1. Click the rule in the table. Its settings load into the form.
2. Change what you need.
3. Click **Save Changes**.

**Add as New** on a loaded rule makes a copy. **Delete** removes the selected rule. **Clear** empties the form.

---

## Command Examples

### Simple Command

| Command | Bot reply contains | Username |
| ------- | ------------------ | -------- |
| waffles |                    |          |

Result:

```text
!waffles
```

Shows the source immediately.

---

### Username Command

| Command | Bot reply contains | Username |
| ------- | ------------------ | -------- |
| pickle  |                    | username |

Result:

```text
!pickle
```

Only works for username.

---

### Trigger Value Command

| Command | Bot reply contains | Username |
| ------- | ------------------ | -------- |
| pp      | 15 inches          |          |

Result:

```text
!pp
```

The bot must reply with something containing:

```text
15 inches
```

before the source appears.

---

### Channel Point Reward

| Trigger on     | Reward name | Chat reply                 |
| -------------- | ----------- | -------------------------- |
| Channel points | Hydrate     | {user} says drink water!   |

Plays when anyone redeems **Hydrate**.

---

# Backups (Export / Import)

* **Export...** saves all rules and walk-ons into one file.
* **Import...** loads them back, for example after reinstalling or on another PC. You can **Replace** your current rules or **Add** to them.

Your settings are stored automatically in:

```text
%APPDATA%\obs-studio\plugin_config\ffy-plugin\
```

Settings from older versions of the plugin are copied over automatically the first time the new version runs.

---

# Troubleshooting

## Command Doesn't Trigger

Check:

* The Twitch box says **Connected**.
* The source exists in OBS and is ticked in the rule.
* The command matches (with or without `!` is fine).
* Username restrictions use the viewer's login name.
* **Who can use it** isn't set higher than the viewer's role.
* The rule isn't on cooldown.
* Trigger values match the bot response.

---

## Trigger Value Doesn't Work

Open OBS's log (**Help > Log Files > View Current Log**) and search for `FFY Plugin`. When a rule fires you'll see a line like:

```text
[FFY Plugin] Chat command rule 'pp' triggered by username
```

Verify the bot message contains the trigger text and arrives within 30 seconds.

Example:

Trigger:

```text
15
```

Bot message:

```text
Your PP is 15 inches today
```

Works, but **also** matches "150", "215" and so on, because they contain "15".

Trigger:

```text
15 inches
```

Bot message:

```text
Your PP is 15 inches today
```

Works, and only for 15.

---

## Channel Points / Bits / Follows Don't Trigger

* Make sure you're logged in, and that the status line lists the feature (e.g. "channel points").
* Channel points and bits only work when logged in as the **channel owner**.
* Follows need the channel owner or a moderator.
* For channel points, the reward name must match the one on Twitch.

---

## Login Problems

* **"Twitch refused the login request: invalid client"**: the Twitch application behind the plugin isn't set up correctly. In the Twitch developer console its **Client Type** must be **Public**.
* **"The plugin needs new Twitch permissions. Log in again."**: the plugin gained features that need extra permissions. Click **Log in with Twitch** again.
* **"Your Twitch login expired"**: log in again.

---

## Source Doesn't Appear

Check:

* The source is in a scene (or group, or nested scene).
* The source isn't marked **(not in OBS)** in the rule.
* **Show for** is greater than 0, or **Hide when video ends** is ticked.

## Source Vanishes Early

Check:

* For videos, tick **Hide when video ends** instead of guessing the length.
* Otherwise, set **Show for** to the source's length plus 1 second (1000 ms).

