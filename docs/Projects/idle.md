# idle

`idle` is my first online, [zero-player](https://en.wikipedia.org/wiki/Zero-player_game){target=_blank} game. Previously, I hosted this myself and you could play it at [idle.intrand.io](https://idle.intrand.io){target=_blank}, but that's no longer true.

## Design

`idle` is comprised of the following components:

* `db`: A Mongo database containing the world states, players, characters, items, NPCs, maps, etc.
* `api`: The gatekeeper between the database and the rest of the stack
* `web`: A graphical representation of the API data
* `engine`: Analyzes world state from the API and updates it accordingly; makes "progress" happen
* `discord`: Bot that sits in discord servers watching for people to be online so they receive "credit" for playing

This is akin to twitch.tv "channel points" in that the player passively accumulates "progress" (levels, stats, items, etc) by simply being logged in to a discord server alongside the bot.

## Status

Back burner project.

Once in a blue moon I'll update it and make some progress, but this is now closed-source due to relative inactivity. I've also stopped hosting things myself, so it's difficult to care about making updates right now.
