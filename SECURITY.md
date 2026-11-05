# Security Policy

## Reporting a vulnerability

If you find a security issue in the Xeneon Widgets Helper, please report it
**privately**. Don't open a public issue.

1. Go to this repository's [Security tab](https://github.com/ensamvarg360/xeneon-widgets-helper/security).
2. Click **Report a vulnerability**.

The report stays private between you and the maintainer until a fix is
released. Please include:

- What you found and the steps to reproduce it.
- Your Helper version. It's shown at the top of the tray menu and in the
  installer's file name.
- The impact, if it isn't obvious: what could someone do with it, and from
  where (a website, another program on the PC, another device on the
  network)?

You should get an acknowledgement within a few days. Once a fix is released,
the changelog will say so, and you'll be credited unless you'd prefer not to be.

## Scope

In scope: the Helper and everything its installer ships. That includes the
tray app, the local server on port 3033, the temporary LAN sign-in listener,
the bundled widget backends (Steam Library, Tejpdeck, Volym), their
PowerShell bridges, and the installer itself.

Especially welcome: ways a **website open in your browser**, **another
device on your network**, or **another user account on the PC** could read
data through the Helper or make it act.

Out of scope: problems that require an attacker who can already run code as
your Windows user, since such a program could read your files directly
without the Helper. The same goes for issues in iCUE, Steam or Windows
themselves (please report those to their vendors).

## Supported versions

Only the [latest release](https://github.com/ensamvarg360/xeneon-widgets-helper/releases/latest)
receives fixes. The Helper doesn't update itself, so please check that you're
on the newest version before reporting.

## Verifying downloads

Every release includes the installer's SHA-256 checksum. See
"Verify your download" under [Install](README.md#install) in the README. The installer
is not code-signed yet.
