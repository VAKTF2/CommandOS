# Changelog

All notable changes to CommandOS are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Planned
- Content for the Personal Menu
- Content for the right pane
- Recovery Mode and Safe Mode
- A real command prompt
- Domain-Specific Language
- Games

## [0.4] - 2026-10-18

### Added
- Left pane in its own files (`leftpane.h` / `leftpane.cpp`).
- Blue "Public Domain Operating System" title at the top of the left pane.
- "Take Tour(y or n)?" question; pressing `n` answers it, shows a green "NO" on the same line, and reveals a `C:/Home>` prompt.
- Personal Menu, opened with `Ctrl+M` and closed with `Esc` or `Ctrl+M` (empty for now).
- Text cursor placed after the tour question and after the prompt.

### Changed
- `Esc` now closes the Personal Menu when it is open, and quits the desktop otherwise.
- Clicking inside a pane no longer moves the text cursor; the left pane controls it.
- Minimum window height raised to 8 rows.
- Version bumped to V0.4.

## [0.3] - 2026-10-17

### Added
- Dark blue title bar with white text and a live clock (for example `Sat 10/17 21:07:33`).
- "CommandOS V0.3" label in pink, centered below the top border of each pane.
- Console window title set to the current version.

### Changed
- The `[X]` close button moved into the title bar.
- The frame now starts one row lower, below the title bar.
- The desktop redraws once per second so the clock keeps ticking.

## [0.2] - 2026-10-16

### Added
- Mouse support: hover highlight on the `[X]` close button, click to close, click inside a pane to move the text cursor.
- Live window resizing; the frame is rebuilt from the current console size.
- Double-buffered `Screen` class, so every frame is written to the console in a single call without flicker.
- `Esc` to quit the desktop.

### Changed
- Split the project into several files: `main.cpp` (boot loader), `console.h` / `console.cpp` (Win32 console layer), and `desktop.h` / `desktop.cpp` (desktop and event loop).
- Quick Edit mode is switched off while the desktop runs, and the original console settings are restored on exit.

## [0.1] - 2026-10-16

### Added
- Boot loader menu with three options: Boot, Recovery Mode, and Safe Mode (the last two print "Nothing yet!").
- Green boot screen after choosing Boot.
- White background with a blue double-line frame split into two panes, in the style of TempleOS.
