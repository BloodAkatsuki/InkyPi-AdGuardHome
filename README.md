# InkyPi AdGuard Home Plugin

An [InkyPi](https://github.com/fatihak/InkyPi) plugin that displays live statistics from your [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) DNS ad blocker on your e-ink display.

## Screenshot

<!-- Add a screenshot of the plugin running on your display here -->

## Features

- Protection status badge (enabled / disabled)
- Total queries, blocked queries and block rate with progress bar
- Safe Browsing, Safe Search and Parental Control counters
- Blocklist rule count
- Top 5 clients by query volume
- 24-hour query history chart (allowed vs. blocked)
- Customizable bar colors (blocked queries color, total queries bar background)
- Each section can be toggled on or off individually

## APIs Used

- **[AdGuard Home REST API](https://github.com/AdguardTeam/AdGuardHome/blob/master/openapi/openapi.yaml)** — built-in HTTP API, no external service or API key required.
  - `GET /control/status` — protection state and version
  - `GET /control/stats` — query statistics, top clients, 24h history
  - `GET /control/filtering/status` — blocklist rule count
- Authentication via HTTP Basic Auth (username + password configured in settings).
- Works with both IP addresses and domain names (including HTTPS with self-signed certificates, e.g. via Nginx Proxy Manager).

## Requirements

- AdGuard Home v0.107 or later

## Installation

Run the following command on your Raspberry Pi:

```bash
inkypi plugin install adguard_home https://github.com/BloodAkatsuki/InkyPi-AdGuardHome
```

## Configuration

| Setting | Description |
|---|---|
| **URL** | AdGuard Home address, e.g. `http://192.168.1.1`, `http://192.168.1.1:3000` or `https://adguard.example.com` |
| **Username** | AdGuard Home login username |
| **Password** | AdGuard Home login password |
| **Blocked queries color** | Color for blocked bars, text and progress fill (default: red `#c62828`) |
| **Total queries bar color** | Background color of total query bars in the chart (default: gray `#cccccc`) |
| **Display options** | Toggle each dashboard section individually |

## Status

Actively maintained.
