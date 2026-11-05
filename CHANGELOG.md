# Changelog

User-facing changes in each public release of the Xeneon Widgets Helper.
Download any version from
[Releases](https://github.com/ensamvarg360/xeneon-widgets-helper/releases).

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and versions follow [Semantic Versioning](https://semver.org/). Versions not
listed here were test builds that were never published publicly.

## [Unreleased]

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
