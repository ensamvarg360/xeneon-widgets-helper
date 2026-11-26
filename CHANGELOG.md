# Changelog

User-facing changes in each public release of the Xeneon Widgets Helper.
Download any version from
[Releases](https://github.com/ensamvarg360/xeneon-widgets-helper/releases).

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and versions follow [Semantic Versioning](https://semver.org/). Versions not
listed here were test builds that were never published publicly.

## [Unreleased]

## [0.0.16] - 2026-11-26

### Added

- Tells you when a new version is out, with a Windows notification and an
  **Install Update** item in the tray menu. **Download and Install**
  downloads it from GitHub, checks its checksum, installs it and restarts the
  Helper. The daily check can be turned off with **Check for Updates
  Automatically**.
- Support for the **Skrivare** widget, which shows your Bambu Lab printer's
  progress, temperatures and camera. The Helper reads the printer over your
  local network and never controls it.
- Support for the **Flyg** widget, which shows live air traffic around a
  place you choose. The Helper fetches the aircraft from adsb.lol, sending
  only that place's location, and a photo of an aircraft you tap from
  planespotters.net, sending only that aircraft's public ID.
- A new **Helper Status** page with a card for each of your widgets that
  needs setting up, such as Steam sign-in or your printer. Each card shows
  whether that widget is connected and opens its setup page. Cards appear
  only for widgets you have added to your Edge.
- The Helper's log now records requests it refused or that failed, which
  makes problems easier to track down. It never records what was sent.

### Security

- Websites open in your browser can no longer reach the Tejpdeck, Volym,
  Skrivare or Flyg widgets' parts of the Helper through a sandboxed frame.
  Before, such a page could change app volumes, control playback, list your
  folders or see the printer camera.
- The Helper now refuses requests addressed to any name other than this PC,
  so a website can't reach it by re-pointing its own domain at your PC.
- Steam sign-in is only accepted when it was started from the Helper's own
  setup page, so a website can't switch the Steam Library widget to someone
  else's account.
- The Helper no longer reads settings from a stray `.env` file in the folder
  it starts in.

### Changed

- A new icon, showing the Xeneon Edge display, for the tray, the installer
  and the app. It replaces the old crosshair.
- **Helper Status** in the tray menu now opens that page
  (`http://localhost:3033/helper`) instead of Steam's setup page. Steam's
  setup page is still there, one click away.
- Steam's setup page and the printer setup page now match the Helper Status
  page, with a **Back** button to it. Steam's page no longer loads anything
  from the internet.

## [0.0.15] - 2026-11-05

First public release.

### Added

- Hosts the local backends for the **Steam Library**, **Tejpdeck** and
  **Volym** widgets on one local port (`127.0.0.1:3033`).
- Tray menu with the installed version, a **Widgets** list showing which
  widgets are currently connected, the Helper status page, **Start with
  Windows**, **View Logs**, **Restart Helper** and **Quit**.
- Starts with Windows by default. You can turn this off from the tray menu,
  and uninstalling removes the startup entry.
- Every widget backend refuses requests from websites open in your browser.
  Only packaged iCUE widgets and the Helper's own pages are answered.
- Each release ships with a SHA-256 checksum file.

[0.0.15]: https://github.com/ensamvarg360/xeneon-widgets-helper/releases/tag/v0.0.15
[0.0.16]: https://github.com/ensamvarg360/xeneon-widgets-helper/releases/tag/v0.0.16
