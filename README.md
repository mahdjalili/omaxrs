<p align="center">
  <img src="logo.png" alt="xrs and omaxrs logo" width="144" height="144" />
</p>

<h1 align="center">omaxrs</h1>

<p align="center">
  Control your xrs connection from the Omarchy bar.
</p>

<p align="center">
  <a href="#installation">Install</a> ·
  <a href="#usage">Usage</a> ·
  <a href="#troubleshooting">Troubleshooting</a> ·
  <a href="https://github.com/mahdjalili/xrs">xrs client</a>
</p>

---

**omaxrs** brings [xrs](https://github.com/mahdjalili/xrs), a lightweight Xray proxy client, to the Omarchy Quattro desktop. Check your connection, switch servers, and manage proxy settings from a single bar widget.

## Preview

<p align="center">
  <img src="preview.png" alt="omaxrs marketplace banner with the xrs logo and proxy panel" width="960" />
</p>

<p align="center">
  <sub>xrs controls for the Omarchy bar · <a href="assets/panel.png">View the original panel screenshot</a></sub>
</p>

## Features

- See connection status and the active server from the bar widget.
- Connect or disconnect with a right-click.
- Select a server and test its latency.
- Toggle TUN mode and inspect active routing rules.
- Refresh subscriptions or open the xrs terminal interface.

## Requirements

| Dependency | Purpose |
| --- | --- |
| **Omarchy Quattro** | Provides the Quickshell plugin host and its `qs.Commons` and `qs.Ui` imports. |
| **[xrs](https://github.com/mahdjalili/xrs)** | Provides the proxy client. Install it on the desktop session's `PATH` and configure proxy nodes before enabling the widget. |
| **foot** | Opens the terminal interface through the panel's **TUI** action. |

omaxrs calls the xrs CLI, including `xrs status --json`. Install and configure the client using the [xrs instructions](https://github.com/mahdjalili/xrs); xrs manages TUN support and any required privileges. The plugin does not bundle xrs or Xray-core, and its QML files require the Omarchy shell host.

## Installation

On your Omarchy desktop, run:

```bash
omarchy plugin add https://github.com/mahdjalili/omaxrs.git --enable
```

The **omaxrs** widget appears in the right bar section by default. Its plugin ID is `io.github.mahdjalili.omaxrs`.

### Migrating from the previous xrs widget

If you used the original `xrs` plugin, disable it before installing omaxrs to avoid duplicate widgets and status polling:

```bash
omarchy plugin disable xrs
```

For a copy installed through Omarchy's plugin manager, remove it with `omarchy plugin remove xrs`. For a manually installed copy, back it up and remove it using its original installation procedure. Then install omaxrs with the command above.

The new plugin ID has separate bar placement and settings; existing widget settings are not migrated automatically. Your xrs client and configuration are unaffected.

## Usage

| Action | Result |
| --- | --- |
| Left-click the bar widget | Open or close the proxy panel. |
| Right-click the bar widget | Connect or disconnect. |
| Select a server in the panel | Switch the active server. |
| Toggle TUN | Change TUN mode through xrs. |
| **Ping** | Test server latency. |
| **Update** | Refresh subscriptions. |
| **TUI** | Open the xrs terminal interface in foot. |

## Update

```bash
omarchy plugin update io.github.mahdjalili.omaxrs
```

## Disable or remove

Hide the widget while keeping it installed:

```bash
omarchy plugin disable io.github.mahdjalili.omaxrs
```

Remove the plugin checkout:

```bash
omarchy plugin remove io.github.mahdjalili.omaxrs
```

An active xrs connection continues after the widget is removed. Disconnect first if needed. Removing the plugin leaves xrs, Xray-core, subscriptions, and client configuration intact.

## Troubleshooting

| Symptom | Check |
| --- | --- |
| No status or servers appear | Run `xrs status --json`. Confirm that xrs is configured and available on the desktop session's `PATH`. |
| The **TUI** action does not open a terminal | Confirm that `foot` is installed. |
| Connection or TUN actions fail | Diagnose the error with xrs directly; the client manages these operations. |

## Development

This plugin was extracted from the `plugin/` directory of xrs and is maintained here. The proxy client remains in the [xrs repository](https://github.com/mahdjalili/xrs).

Validate the manifest from this repository on an Omarchy system:

```bash
omarchy plugin validate .
```

This checks the manifest and entry points. Before release, test the integration on a running Omarchy desktop: connection status, panel opening and closing, connect/disconnect, server selection, TUN switching, latency tests, subscription refresh, TUI launch, and removal.

### Repository layout

| File | Purpose |
| --- | --- |
| [manifest.json](manifest.json) | Plugin metadata and bar widget entry point. |
| [BarWidget.qml](BarWidget.qml) | Bar button and panel loader. |
| [Panel.qml](Panel.qml) | Proxy controls and xrs CLI integration. |
| [logo.png](logo.png) | Shared xrs/omaxrs logo used in this README. |
| [preview.png](preview.png) | Root marketplace banner with the logo and plugin UI. |
| [assets/panel.png](assets/panel.png) | Original, unmodified panel screenshot. |

See the [official publishing guide](https://plugins.omarchy.org/publish.html) for marketplace asset conventions and publishing preparation.

## License

[MIT](LICENSE)
