# omaxrs

The Omarchy bar plugin for [xrs](https://github.com/mahdjalili/xrs), a lightweight Xray proxy client.

This project was extracted from the `plugin/` directory of xrs. The plugin is maintained here; the proxy client remains in the xrs repository.

## Features

- View connection status and the active server in the bar.
- Left-click to open the proxy panel; right-click to connect or disconnect.
- Switch servers and toggle TUN mode.
- View active routing rules and test server latency.
- Update subscriptions and open the xrs terminal interface.

## Requirements

- [xrs](https://github.com/mahdjalili/xrs) installed and available on the desktop session's `PATH`, with proxy nodes configured.
- An Omarchy Quickshell bar with a compatible plugin host providing the `qs.Commons` and `qs.Ui` modules used by this plugin.
- `foot` for the panel's **TUI** action.

The plugin uses the xrs CLI, including `xrs status --json`, to read status and perform actions. It does not bundle xrs or Xray-core.

## Installation

Clone this repository:

```bash
git clone https://github.com/mahdjalili/omaxrs.git
```

Install the repository's contents into your bar's plugin directory using your plugin host's installation procedure, then enable the **Proxy** widget. Keep `manifest.json`, `BarWidget.qml`, and `Panel.qml` together. The plugin ID remains `xrs` for compatibility with existing bar configurations; if your host requires directory names to match plugin IDs, use `xrs` as the installed directory name.

The required UI components come from the bar's plugin host; these QML files are not a standalone Quickshell application.

To update a Git-based installation, run `git pull --ff-only` in its checkout and reload the plugin using your bar's usual procedure.

## Files

- `manifest.json`: plugin metadata and bar widget entry point.
- `BarWidget.qml`: bar button and panel loader.
- `Panel.qml`: proxy controls and xrs CLI integration.

## License

MIT, see [LICENSE](LICENSE).
