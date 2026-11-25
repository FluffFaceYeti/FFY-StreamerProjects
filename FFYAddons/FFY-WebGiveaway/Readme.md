# FFY Web Giveaway

Your very own giveaway website. Viewers pop over, log in with Twitch and spend their points on tickets, even when you're offline, asleep or on holiday. Then you draw the winner live on stream with confetti.

```
Chat: 🎁 A giveaway for a Steam Key has started! Enter here: https://yourname.github.io/giveaway/
(Mia logs in on the site, sees she has 1,240 Fluff, and grabs 5 tickets)
Chat: @Mia entered the giveaway with 5 tickets!
...
(You press Draw on your control page, from your PC or your phone, and the winner pops up on stream)
Chat: 🎉 The winner of a Steam Key is @Mia with a 12% chance!
```

- **Open all the time.** Run a giveaway for a day, a week or a month, and people can enter whenever suits them.
- **Uses your [FFY Points](../FFY-Points/Readme.md).** Viewers earn points in Streamer.bot while you're live, and spend them on the site while you're offline. Their balance stays the same in both places.
- **Your control page** starts giveaways, sets a draw date, shows who's in, and draws, redraws or cancels with everyone's points refunded. It works on your phone too.
- **Enter from chat too.** Viewers can type `!tickets 5` (or `!tickets max`) in chat while you're live, and use the site when you're offline.
- **Chat knows what's going on.** Messages go out when a giveaway starts and when someone wins, and for every entry too if you like.
- **A winner overlay** for OBS, with confetti and their chance of winning.
- **Make it yours:** your banner, profile picture, background, colours, and your own name and icon for points.
- **Your own web address.** Got a domain? Point something like `giveaway.yoursite.com` at it instead of the GitHub address.
- **Fair for everyone.** Subscribers don't get extra points or tickets, so it keeps to Twitch's rules.

It's completely free. Everything runs on your own GitHub and your own Supabase (a free online database), so nobody else holds your viewers' points.

> **Disclaimer:** I (FluffFaceYeti) am not responsible if you go over your Supabase free limit and get charged. It runs on your own Supabase account, so any bill from Supabase is yours. The [setup guide](https://github.com/FluffFaceYeti/FFYGiveaway/blob/main/SETUP.md#disclaimer) lists the free limits, with examples of what uses them.

It's a website you set up once, which takes about 15 minutes, plus an FFY Points import for Streamer.bot that the setup makes for you.

---

## Getting it

### 👉 [Make my own copy](https://github.com/new?template_name=FFYGiveaway&template_owner=FluffFaceYeti)

Name it `giveaway`, set it to **Public**, and click **Create repository**. Then follow the setup guide and you're away.

- **[Setup guide](https://github.com/FluffFaceYeti/FFYGiveaway/blob/main/SETUP.md)**: seven steps, start to finish.
- **[Setup helper](https://flufffaceyeti.github.io/FFYGiveaway/setup.html?new)**: fill in your details and it writes all the fiddly bits for you, with copy buttons.

You'll need free accounts on **GitHub** and **Supabase**, your Twitch, and **Streamer.bot**. No coding, just copying and pasting.

---

## Using your own website address

Don't fancy sharing `yourname.github.io/giveaway`? If you own a domain, you can put the giveaway on your own address, like `giveaway.yoursite.com`. You add one DNS record wherever you bought the domain (123 Reg, GoDaddy, Namecheap, Cloudflare...), and your main website isn't touched.

It works even if your main site is on Wix, Shopify or Squarespace, because only the `giveaway.` part points to GitHub. The end of the setup guide shows you how, and the setup helper gives you the extra Twitch link to add.

Once it's set up, old `github.io` links forward to your new address by themselves, so nothing you've already shared breaks.
