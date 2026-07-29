# ToriiHalo

ToriiHalo does two jobs. In game it PMs you when a score gives 0pp or your account status changes. On the Discord server it runs the slash commands below, from looking up scores to the coin economy.

## On Discord: getting started

::: alert-note
**These are Discord commands**
Everything in this section runs on the Torii Discord server, not in the game. Type a slash in any channel and Discord will show you the list as you type.
:::

Start with `/link`. It ties your Discord account to your Torii one, which means the other commands already know who you are and you can write `/top` instead of spelling out your username every time.

| Command | Arguments | What it does |
| :-- | :-- | :-- |
| `/link` | `<username or id>` | Point your Discord account at your Torii account, so the osu commands know who you are without typing your name every time. |
| `/whoami` |  | Check which Torii account you are currently linked to. |
| `/unlink` |  | Remove the link. |

## On Discord: scores and profiles

These read straight from Torii, so what you see on Discord is what the server has. Leave the user out of any of them and the bot uses your linked account.

| Command | Arguments | What it does |
| :-- | :-- | :-- |
| `/profile` | `[user] [mode]` | Torii profile stats for a player. Leave the user out to see your own linked account. |
| `/top` | `[user] [mode]` | Someone's best plays, sorted by pp. |
| `/recent` | `[user] [mode]` | Plays from the last 24 hours, fails included. |
| `/score` | `<id or url>` | One score in detail. Paste a score link straight from the site. |
| `/beatmap` | `<id or url>` | Beatmap info plus a peek at its leaderboard. |
| `/rankings` | `[mode] [country]` | The Torii global rankings. |

## On Discord: Torii Coins

Coins are the Discord server's own currency. You collect them by showing up, and they are separate from the points you earn in game by playing.

| Command | Arguments | What it does |
| :-- | :-- | :-- |
| `/daily` |  | Your once-a-day coins. Claiming on consecutive days builds a streak, and the streak bonus grows up to day 7. |
| `/work` |  | A smaller payout on a short cooldown, so there is always something to do between dailies. |
| `/balance` | `[member]` | How many coins you are sitting on, your streak, and your linked Torii account. |
| `/coinflip` | `<amount> <heads\|tails>` | Bet coins on a flip. Win and you double the bet, lose and it is gone. |
| `/pay` | `<member> <amount>` | Send coins to somebody else. |
| `/coins_top` |  | The richest people on the server. |

::: alert-warning
**Coins are not pp**
Nothing you do with coins touches your rank, your pp or your scores. They live on Discord.
:::

## On Discord: the rest

| Command | Arguments | What it does |
| :-- | :-- | :-- |
| `/owoify` | `<text>` | Ruins your text. That is the whole feature. |
| `/ping` |  | Checks the bot is awake. |

The bot also posts on its own: recent plays as score cards, o!rdr render notifications and the daily challenge. Those need no command.

## In game: when a score gives 0pp

If a play submits but earns no pp, ToriiHalo PMs you the reason in game. The three you might see:

> **ToriiHalo says**
> Your score gave 0pp! Your accuracy was 71.4%. Relax and Autopilot scores need at least 75% accuracy to earn pp.

> **ToriiHalo says**
> Your score gave 0pp! You changed Flashlight settings. Only default Flashlight settings earn pp, set size, delay and combo-based size back to their defaults.

> **ToriiHalo says**
> Your score gave 0pp, it did not meet the requirements to earn pp.

The full list of what zeroes pp is on the [Scoring & pp](/wiki/Scoring) page.

## In game: when your account is restricted

If your account gets restricted, ToriiHalo sends a PM in game, and it is re-sent every time you reconnect so you do not miss it:

> **ToriiHalo says**
> You are restricted, please wait 1 month before your appeal through a ticket in the discord server.

What a restriction means and how to appeal is on the [Restrictions & Appeals](/wiki/Restrictions) page.
