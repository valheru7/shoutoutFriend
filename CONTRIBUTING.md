# Contributing

Bug reports and small pull requests are welcome.

- **Bugs:** open an issue with what you ran (`!so @name` or a raid), your Firebot version, and the line from Firebot's log
  (File → Open Logs Folder) that starts with `Shoutout Friend:`. Don't paste your API key.
- **Changes:** keep them small and readable. Run `node --test` before opening a pull request, and add a test for new behavior.
- **Safety rules stay:** a shoutout must never start with `/` or `!`, and the stream title stays background-only data
  (see the rules in `shoutout-friend.js`). Pull requests that loosen these will need a good reason.
- No dependencies, please. The script is a single file so it's easy to drop into Firebot's scripts folder.
