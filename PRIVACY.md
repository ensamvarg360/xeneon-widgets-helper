# Privacy

This page explains what data the Xeneon Widgets Helper handles, where it goes
and where it is kept. It applies to the Helper as downloaded from this
repository's [Releases](https://github.com/ensamvarg360/xeneon-widgets-helper/releases).

## In short

- The Helper has **no server of its own** and **collects nothing** about you.
  The author of the Helper receives no data from it.
- There is **no telemetry, analytics, advertising or crash reporting**, and no
  update check.
- Everything the Helper stores stays **on your PC**, in your Windows user
  profile.
- The only internet services the Helper contacts are **Steam's**, and only if
  you use the Steam Library widget.

## Data that leaves your PC

Only when you use the **Steam Library** widget, and only to Valve's Steam
services:

| Sent to | Data | Purpose |
|---|---|---|
| `api.steampowered.com` | Your Steam Web API key, your SteamID, and game app IDs | Fetch your library, recently played games, profile, friends list, achievements and game news |
| `store.steampowered.com` | A game's app ID | Fetch that game's store description and screenshots |
| `steamcommunity.com` | The sign-in response Steam sent to your browser | Confirm your "Sign in through Steam" login |

These requests go directly from your PC to Steam over HTTPS. Valve's handling
of them is covered by the
[Steam Privacy Policy](https://store.steampowered.com/privacy_agreement/).

Your browser (not the Helper) also contacts Google Fonts when it shows the
Helper's local status page, and visits Steam's own sign-in and API-key pages
when you choose to sign in.

The **Tejpdeck** and **Volym** widgets send **nothing** off your PC.

## Local network

When you choose to sign in to the Steam Library widget with your phone, the
Helper makes its sign-in page reachable on your local network for at most 120
seconds, or until sign-in finishes. Only the sign-in pages are usable from
another device during that time. Your library data and the game controls are
not. See [Connections it accepts](README.md#connections-it-accepts) in the README.

## Data stored on your PC

| Where | What |
|---|---|
| `%APPDATA%\xeneon-widgets-helper\config.json` | Your SteamID, your Steam Web API key (in plain text), your widget theme choice, and a random local access token |
| `%APPDATA%\xeneon-widgets-helper\music-*.json` | Tejpdeck's chosen folder or playlist, favorites, player settings (volume, shuffle, repeat) and its local access token |
| `%APPDATA%\xeneon-widgets-helper\volym-token.json` | Volym's local access token |
| `%APPDATA%\xeneon-widgets-helper\helper.log` (and `helper.log.1`) | A log of what the Helper did, such as which widgets connected, errors, and folder paths used by Tejpdeck. It rotates at 5 MB. |
| `%TEMP%\xeneon-steam-helper-crash.log` | Startup and crash diagnostics |

The Helper also reads, **without storing or sending**:

- Steam's install location, library folders and installed-game manifests,
  and which Steam game is running.
- Audio files, tags and cover art in the music folders or playlists you pick
  for Tejpdeck, and folder names while you browse for one.
- What other apps report to Windows as "now playing" (title, artist, cover
  art), and per-app volume levels, for Tejpdeck and Volym to display.

## Removing your data

- **Steam Web API key:** revoke it on [Steam's API key page](https://steamcommunity.com/dev/apikey).
  That stops it working everywhere, including in the Helper.
- **Everything else:** quit the Helper and delete
  `%APPDATA%\xeneon-widgets-helper\`. Uninstalling the Helper leaves this
  folder in place, so delete it yourself if you want your settings gone.

## Changes

If a future version changes anything on this page, the change will be listed
in the [changelog](CHANGELOG.md) for that version.

## Contact

Questions about this page: [open an issue](https://github.com/ensamvarg360/xeneon-widgets-helper/issues).
