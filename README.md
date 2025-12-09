# EDCoPTER2.0-public-releases

# Quick User Guide

This document explains how to install and run the EDCoPTER desktop application (Electron installer) and the most common user tasks.

Installation (Windows)
- Download the latest installer (EXE) from your project's Releases page.
- Run the installer and follow the prompts (default install path recommended).
- If prompted by Windows Defender / SmartScreen, choose "More info" → "Run anyway" if you trust this build.

Firewall & Permissions
- On first run the app may need firewall access for WebSocket (8088), HTTP (4500) and TCP bridge (9096).
- On Windows run the provided `setup-firewall.ps1` as Administrator to add recommended rules.

First Run
- Launch EDCoPTER from Start Menu (or run the installed `edcopter.exe`).
- In the Server Controller window:
  - Choose the network adapter to bind to.
  - Enter the IP address where the Python EDCoPilot is running (use `127.0.0.1` if on same machine).
  - Click Save, then Open EDCoPTER in Browser to open the UI.

Headless / Server Mode
- The packaged app supports a headless mode for server-only use:
  - `edcopter --headless --port 4500`
  - Access the UI at `http://localhost:4500` or `http://<your-ip>:4500` from the network.

Auto-update
- Updates are handled by the app and shown in the UI when available.

Troubleshooting (common)
- WebSocket connection fails: verify EDCoPilot is running.
- UI not loading: confirm the `edcopter/` folder exists and contains `index.html`.
- Installer won't run: ensure antivirus or SmartScreen isn't blocking the binary.

Privacy & Data
- Local configuration and logs are stored in `%USERPROFILE%\.edcopter2.0\` (Windows). No telemetry is sent by default.

