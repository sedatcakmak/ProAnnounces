# ProAnnounces

An auto-announcement plugin for Spigot/Paper. Define any number of multi-line announcements and let the plugin broadcast them on a fixed interval, sequentially or in random order, with an optional minimum-players gate and per-world filtering.

## Features

- Unlimited multi-line announcements defined in `config.yml`.
- Configurable broadcast interval (seconds).
- Sequential or random announcement order.
- Minimum-players threshold — skips broadcasts when too few players are online.
- Optional per-world mode — only players in listed worlds receive announcements.
- Optional sound played alongside each broadcast.
- Built-in placeholders (`%player%`, `%online%`, `%world%`, `%ping%`, etc.) plus PlaceholderAPI support.
- Hex / RGB color support (`#RRGGBB`) and `%header%`, `%footer%`, `%prefix%`, `%center%` helpers.
- Per-player toggle command (`/announces toggle`).

## Requirements

- Minecraft / Spigot 1.16+ (built against Spigot API 1.16.4).
- Java 8 or newer.
- Optional: PlaceholderAPI for extended placeholders.

## Commands

- `/proannounces` (aliases: `/proannounce`, `/announces`, `/announce`) — base command.
  - `info` — show current announcement state.
  - `toggle` — enable / disable announcements for yourself.
  - `reload` — reload `config.yml`.

## Permissions

Configurable under `settings.permissions` in `config.yml`. Defaults:

- `command` — empty (everyone).
- `toggle` — empty (everyone).
- `info` — `announces.info`.
- `reload` — `announces.reload`.

Set any permission to `''` to disable the check for that subcommand.

## Installation

1. Drop `ProAnnounces.jar` into `plugins/`.
2. Start (or restart) the server to generate `config.yml`.
3. Edit `plugins/ProAnnounces/config.yml`, then `/proannounces reload`.

## Configuration

`config.yml` controls:

- `settings.reload` — broadcast interval in seconds.
- `settings.random` — random vs. sequential order.
- `settings.minimumPlayers` — minimum online player count to broadcast.
- `settings.sound` — optional sound on broadcast.
- `settings.worlds` — restrict announcements to specific worlds.
- `messages.header` / `footer` / `prefix` — reusable formatting tokens.
- `announces` — your announcement entries (each a list of lines).
