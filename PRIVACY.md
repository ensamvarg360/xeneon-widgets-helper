# Privacy

This page explains what data the Xeneon Widgets Helper handles, where it goes
and where it is kept. It applies to the Helper as downloaded from this
repository's [Releases](https://github.com/ensamvarg360/xeneon-widgets-helper/releases).

## In short

- The Helper has **no server of its own** and **collects nothing** about you.
  The author of the Helper receives no data from it.
- There is **no telemetry, analytics, advertising or crash reporting**.
- Everything the Helper stores stays **on your PC**, in your Windows user
  profile.
- The only internet services the Helper contacts are **Steam's**, only if you
  use the Steam Library widget, **adsb.lol** and **planespotters.net**, only
  if you use the Flyg widget, and **GitHub**, for Helper updates.

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

To check for updates, the Helper asks GitHub (`api.github.com`) for the latest
published version, shortly after it starts and then once a day, unless you
turn **Check for Updates Automatically** off in the tray menu. Only when you
choose **Download and Install** does it download the installer and its
checksum from GitHub. These requests carry nothing about you beyond what any
web request does (your IP address). GitHub's handling of them is covered by
the [GitHub Privacy Statement](https://docs.github.com/site-policy/privacy-policies/github-general-privacy-statement).

The Helper's own pages (Helper Status and the Steam and printer setup pages)
load nothing from the internet. Your browser (not the Helper) visits Steam's
own sign-in and API-key pages when you choose to sign in.

Only when you use the **Flyg** widget, to two public aviation services:

| Sent to | Data | Purpose |
|---|---|---|
| `api.adsb.lol` | The location chosen in the widget's settings (latitude and longitude, rounded to 4 decimals, about 10 m) and a search radius | Fetch the aircraft currently around that place |
| `api.planespotters.net` | An aircraft's 24-bit ICAO address (public, broadcast by the aircraft itself) | Find a photo of that aircraft when you tap it |

The location is whatever you chose: a city, or exact coordinates if you typed
them. **Choosing a city is the private option.** Flyg sends nothing else about
you beyond what any web request does (your IP address), and stores nothing.
The Helper's log never records the location.

The **Tejpdeck**, **Volym** and **Skrivare** widgets send **nothing** off
your PC. Skrivare talks only to your own Bambu Lab printer, on your local
network (see below).

## Local network

When you choose to sign in to the Steam Library widget with your phone, the
Helper makes its sign-in page reachable on your local network for at most 120
seconds, or until sign-in finishes. Only the sign-in pages are usable from
another device during that time. Your library data and the game controls are
not. See [Connections it accepts](README.md#connections-it-accepts) in the README.

When you use the **Skrivare** widget, the Helper connects to the Bambu Lab
printer whose address you entered, over TLS on your local network. It sends
the printer's serial number and LAN access code (the printer needs them to let
it read) and receives the printer's status and, on the larger widget sizes,
camera pictures. The camera pictures are passed to the widget and not saved.
The connections close shortly after the widget stops asking.

## Data stored on your PC

| Where | What |
|---|---|
| `%APPDATA%\xeneon-widgets-helper\config.json` | Your SteamID, your Steam Web API key (in plain text), your widget theme choice, and a random local access token |
| `%APPDATA%\xeneon-widgets-helper\music-*.json` | Tejpdeck's chosen folder or playlist, favorites, player settings (volume, shuffle, repeat) and its local access token |
| `%APPDATA%\xeneon-widgets-helper\volym-token.json` | Volym's local access token |
| `%APPDATA%\xeneon-widgets-helper\skrivare-config.json` | Skrivare's printer: its local IP address, serial number and LAN access code (in plain text). **Forget printer** on the printer setup page deletes it. |
| `%APPDATA%\xeneon-widgets-helper\widgets-seen.json` | Which widgets (by name, such as `steam` or `skrivare`) have connected to the Helper, and when each was last seen, so the Helper Status page only shows the widgets you have |
| `%APPDATA%\xeneon-widgets-helper\helper.log` (and `helper.log.1`) | A log of what the Helper did, such as which widgets connected, errors, requests it refused or that failed (the address, status and origin only, never what was sent), and folder paths used by Tejpdeck. It rotates at 5 MB. |
| `%APPDATA%\xeneon-widgets-helper\update-check-disabled` | Present only while automatic update checks are turned off |
| `%TEMP%\xeneon-widgets-helper-update\` | The last update installer you chose to download |
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
