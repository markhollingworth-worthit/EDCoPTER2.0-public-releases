# Changelog

All notable changes to EDCoPTER are documented in this file.

This project follows semantic versioning.

---

# [2.0.0] - 2026-03-XX

## 🚀 Stable Release

First fully stable release following the 2.0 beta cycle.

Includes all improvements from v2.0.0-beta.1 → v2.0.0-beta.39.

### Added
- Stable & Beta update channel support with policy management
- Manual update check functionality
- Browser compatibility checks
- Alternate command panel font option
- Custom icon font (DeckIconFont)
- Touch gesture support (swipe, pinch, double-tap)
- Shape-only button mode
- Custom background image support for layouts
- Guidance Computer panel
- Ships panel with search
- Stations panel with sorting
- Mining stats panel
- Exobiology panel
- Discovery estimator
- Trade route parsing & UI
- Time Trials with leaderboard
- Suit Manager panel
- Weapons panel
- Station Facts panel
- Command Reference panel
- Blueprints management
- Prospector announce management
- Translation & language support
- HTTPS + Secure WebSocket (WSS) support
- Screen Wake Lock API support
- MQTT integration
- GPU hardware acceleration toggle

### Changed
- Refactored WebSocket handling and reconnection logic
- Improved command routing logic
- Refactored settings UI and configuration handling
- Standardized `.edcopter2.0` user data path
- Major UI responsiveness improvements across components
- Introduced TableSortingService for consistent sorting
- Unified loading / error / empty state handling
- Improved CI/CD workflows and cross-platform packaging
- Enhanced mobile & iPad layout handling

### Fixed
- Improved session persistence and client IP handling
- Resolved routing conflicts when already on target route
- Fixed keybind request issues during reconnection
- Improved termination handling
- Corrected Flight Assist Off animation flag
- Various UI alignment and responsiveness fixes

---

# 2.0.0 Beta Cycle

## [2.0.0-beta.39]
### Added
- Updater policy management with stable and beta groups
- Commander identity extraction from voice logs

## [2.0.0-beta.38]
### Added
- Browser compatibility endpoint and UI indicator

## [2.0.0-beta.37]
### Added
- Alternate command panel font support

## [2.0.0-beta.36]
### Changed
- Major table refactor and sorting service introduction
- Enhanced settings input validation
- Improved header dropdown behavior

### Fixed
- Prevent unnecessary navigation when already on route

---

## Earlier 2.0.0 Betas (1–35)

During the 2.0 beta cycle, the following major systems were introduced:

### Added
- Cross-platform packaging (Windows / Linux / macOS)
- Auto-updater integration
- Ships, Stations, Mining, Exobiology, Discovery, Trade, Time Trials
- Suit Manager, Weapons, Station Facts, Command Reference
- Custom layout backgrounds
- DeckIconFont integration
- MQTT connection publishing
- Translation system
- Secure HTTPS support
- Screen Wake Lock API

### Changed
- Full UI responsiveness overhaul
- Routing & WebSocket architecture improvements
- Settings refactor and state management improvements
- Global loading / error state components

### Fixed
- WebSocket termination handling
- Bookmark routing issues
- Keybind handling improvements
- Multiple UI consistency fixes
