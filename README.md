# Shoutout Friend

`!so @streamer` posts a short, personal shoutout in chat, written by Claude from what that
streamer is playing. The stream title is sent as background only and never mentioned. No canned "go check them out" line.

> Status: early release. Tested against fakes and running in a real Firebot 5.66 (command and raid events).

## Install (Firebot 5)

1. Copy `shoutout-friend.js` into your Firebot profile's `scripts` folder
   (Settings → Scripts → Open Scripts Folder).
2. In Firebot, create a command (e.g. `!so`) with a **Run Custom Script** effect and pick
   `shoutout-friend.js`.
3. Fill in the parameters: your Anthropic API key (console.anthropic.com), and optionally the
   model, the voice and who sends the message.
4. Give the command a cooldown (30 seconds or more) and restrict it to mods, so a shoutout
   can't be spammed.

## What it sends to Claude

Only the streamer's display name, their current or last game, and their stream title (background only; the prompt forbids mentioning it, and treats it as data, not instructions). Nothing
about your own channel. A shoutout costs a fraction of a cent on a small model.

## Safety

- The reply is flattened to one line, and a leading `/`, `!` or `.` is stripped, so the model can't
  make your bot run a Twitch or Firebot command.
- If the key is missing, the streamer isn't found, or the API fails or is slow, it posts nothing.
  Firebot gives a script 10 seconds, so the call gives up at 8.

## Develop

`node --test` runs the tests with a faked Firebot and Claude. Set `ANTHROPIC_API_KEY` (and
`SHOUTOUT_TARGET`) to also try one real call.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

GPL-3.0-or-later. Copyright (C) 2026 Jerica Wilson. You can use and change it, but if you share a modified version it must also be GPL-3.0 with its source. See [LICENSE](LICENSE).
