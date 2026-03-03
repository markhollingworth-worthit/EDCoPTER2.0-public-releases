# Quick User Guide

This document explains how to install and run the EDCoPTER desktop application (Electron installer) and the most common user tasks.

## Installation (Windows)
- Download the latest installer (EXE) from the Releases page or `https://edcopter.net`.
- Run the installer and follow the prompts (default install path recommended).
- If prompted by Windows Defender / SmartScreen, choose "More info" → "Run anyway" if you trust this build.

First Run
- Launch EDCoPTER Launcher from Start Menu or Desktop (or run the installed `edcopter.exe`).
- In the Server Controller window:
  - Choose the network adapter to bind to.
  - Enter the IP address where the Python EDCoPilot is running (use `127.0.0.1` if on same machine).
  - Click Save, then Open EDCoPTER in Browser to open the UI.

Headless / Server Mode
- The packaged app supports a headless mode for server-only use:
  - `edcopter --headless --port 4500`
  - Access the UI at `http://localhost:4500` or `http://<your-ip>:4500` from the network.

| Option           | Alias | Description                   | Default   |
|------------------|-------|-------------------------------|-----------|
| `--headless`     | `-h`  | Run without GUI (server only) | false     |
| `--port`         | `-p`  | HTTP/WebSocket server port    | 4500      |
| `--ip`           | -     | Server IP address             | 0.0.0.0   |
| `--edcopilot-ip` | -     | EDCoPilot TCP server IP       | 127.0.0.1 |
| `--debug`        | `-d`  | Enable debug logging          | false     |
| `--help`         | -     | Show help message             | -         |

Auto-update
- Updates are handled by the app and shown in the UI when available.

## Troubleshooting (common)
- WebSocket connection fails: verify EDCoPilot is running.
- UI not loading: confirm the `edcopter/` folder exists and contains `index.html`.
- Installer won't run: ensure antivirus or SmartScreen isn't blocking the binary.

Privacy & Data
- Local configuration and logs are stored in `%USERPROFILE%\.edcopter2.0\` (Windows). No telemetry is sent by default.

## Disclaimers

### Warranty & liability
- This software is provided **"as is"** and **without warranties or conditions of any kind**, whether express, implied, or statutory, including (without limitation) implied warranties of merchantability, fitness for a particular purpose, and non-infringement.
- To the maximum extent permitted by applicable law, the authors and contributors will **not be liable** for any direct, indirect, incidental, special, consequential, or exemplary damages (including, without limitation, loss of profits, data, or business interruption) arising out of or in connection with the software or the use of the software, even if advised of the possibility of such damage.

### Security / network use
- Running EDCoPTER in headless/server mode may expose an HTTP/WebSocket service on your network.
- If you use `--ip 0.0.0.0` (the default), EDCoPTER will bind to **all** network interfaces. Only do this on trusted networks, and ensure your firewall rules restrict access appropriately.
- Do **not** expose EDCoPTER directly to the public internet without additional protections (e.g., VPN, reverse proxy with authentication/TLS, IP allowlists).

### Support & maintenance
- This user guide and the software may change without notice.
- Support is provided on a best-effort basis (or may be unavailable), and there is no guarantee of fixes, updates, or continued compatibility with future operating system or dependency changes.