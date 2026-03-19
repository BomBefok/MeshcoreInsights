# MeshcoreInsights
A Graphical software interface to interact with Meshcore companion nodes.


# ⬡ MeshCore Insights

> **Desktop dashboard for MeshCore mesh radio networks**

> ⚠️ **This software is under active development.** Features may change and bugs may be present. Please report issues on GitHub and check for updated releases regularly. Your feedback directly shapes the roadmap.

MeshCore Insights connects to a MeshCore companion node via **USB serial or Bluetooth (BLE)** and provides a real-time dashboard — live node map, messaging, node analysis, remote management, and a debug console.

---

## Screenshots

*Coming soon*

---

## Features

- **Live Map** — Leaflet-based interactive map of all mesh nodes, colour-coded by last-heard time
- **Messaging** — Channel and direct messaging with path history and message path visualisation
- **Node Analysis** — Battery, SNR, telemetry gauges, noise floor graph, neighbour tables
- **Remote Management** — Login and send admin commands to remote nodes over the mesh
- **Debug Console** — Full raw event stream for troubleshooting
- **Offline Maps** — Download and use tile maps without internet
- **USB & BLE** — Connect via serial port or Bluetooth with auto-scanning
- **Dark / Light Theme** — Toggle between themes at any time
- **Delete Contacts** — Remove nodes from the radio's contact database via the GUI

---

--

## Installation

Download the latest compiled `.exe` from [Releases](https://github.com/BomBefok/MeshcoreInsights/releases).

---

## Quick Start

### USB Connection
1. Connect your MeshCore companion node via USB
2. Select **🔌 USB** in the top bar
3. Choose the correct COM port from the drop-down
4. Click **▶ Connect**

### Bluetooth (BLE) Connection
1. Select **📶 BLE** in the top bar
2. Click **📶 Scan / Connect**
3. Select your MeshCore device from the scan results (highlighted in cyan)
4. Click **⬡ Connect to Device** — pairing is handled automatically

> **Windows BLE note:** On first connection Windows pairs the device automatically. If connection fails, remove the device from Windows Bluetooth Settings, restart your MeshCore node, and connect again.

---

## User Manual

A full user manual is bundled with the compiled release as `MeshCore_Insights_Manual.docx`.

The manual covers:
- System requirements and installation
- USB and BLE connection setup
- All five tabs: Map, Communications, Node Analysis, Remote Management, Console
- Tools menu operations
- Deleting contacts
- Keyboard shortcuts
- Troubleshooting guide
- Known limitations

---

## Interface Overview

### Top Bar

| Element | Description |
|---------|-------------|
| 🔌 USB / 📶 BLE | Select connection type |
| Port / Device | COM port selector (USB) or selected device name (BLE) |
| ▶ Connect / ■ Disconnect | Connect or disconnect |
| ⊕ Fit Map | Zoom map to fit all nodes |
| 📡 Advert | Send flood advertisement to the mesh |
| 🗺 Offline Maps | Download map tiles for offline use |
| ☀/☾ Theme | Toggle dark/light theme |

### Tabs

| Tab | Purpose |
|-----|---------|
| **Map** | Live node map with side panel, search, and context actions |
| **Communications** | Channel and direct messaging with path history |
| **Node Analysis** | Detailed stats, telemetry, neighbours for selected node |
| **Remote Management** | Login and send commands to remote nodes |
| **Console** | Raw event stream for debugging |

### Node Context Menu (right-click any node)

- **Locate on Map** — centre map on the node
- **Discover Path** — trace path from local node to this node
- **Direct Message** — open a direct message conversation
- **Analyse Node** — open Node Analysis tab for this node
- **Request Neighbours** — ask the node for its neighbour table
- **Export Contact URI** — copy a shareable contact URI to clipboard
- **🗑 Delete Contact…** — permanently remove node from radio's contact database

---

## Tools Menu

| Tool | Shortcut | Description |
|------|----------|-------------|
| Clock Sync | Ctrl+Shift+C | Sync node clock to system time |
| Flood Advert | — | Send flood advert to entire mesh |
| Self Telemetry | — | Request telemetry from local node |
| Import Contact URI | — | Add a contact by pasting a URI |
| Discover Nodes | — | Trigger full node discovery scan |

---

## Troubleshooting

### No USB ports visible
- Ensure the USB driver for your node's chip (CH340, CP2102, etc.) is installed
- Click ↻ to refresh the port list
- Check the node is running **companion firmware**, not another variant
- Try a different USB cable (data cable, not charge-only)

### BLE connection fails on Windows
1. Open Windows Bluetooth Settings
2. Remove / forget the MeshCore device
3. Restart your MeshCore node
4. Re-scan and connect — pairing is automatic, no PIN needed

### Map shows no tiles
- Check your internet connection
- For offline use, download tiles first via **🗺 Offline Maps**

### Path map window doesn't open
- Install PyQtWebEngine: `pip install PyQtWebEngine`

---

## Known Limitations

| Area | Status |
|------|--------|
| BLE on Windows | Connection reliability under improvement — remove/re-pair if issues persist |
| Offline map tile download | Available; improved region selection planned |
| Multi-channel encryption | Key management not yet exposed in the GUI |
| Dark/light theme persistence | Resets to dark on restart — preference saving planned |
| Mobile / touch screens | Designed for desktop use; not touch-optimised |

---

## Contributing

Pull requests are welcome. Please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

*MeshCore Insights is not officially affiliated with the MeshCore project. It is a community-built companion tool.*
