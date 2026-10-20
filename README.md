# CommandOS

A TempleOS-inspired text-mode desktop for the Windows console, written in C++ with the Win32 API.

CommandOS starts with a small boot loader menu, then switches the console to a white and blue two-pane interface with a live clock, mouse support, and window resizing. It's a hobby project for exploring low-level console programming: raw input events, a double-buffered screen, and a clean file structure that can grow into something bigger.

## Features

- **Boot loader menu:** choose Boot, Recovery Mode, or Safe Mode (Recovery and Safe Mode are placeholders for now).
- **Two-pane desktop:** white background with blue double-line borders, in the style of TempleOS.
- **Title bar:** dark blue bar with a live clock and a clickable `[X]` close button.
- **Mouse support:** hover and click, with the console's Quick Edit mode switched off while the desktop runs.
- **Live resizing:** the layout rebuilds itself when the console window changes size.
- **Flicker-free drawing:** every frame is built in a back buffer and written to the console in one call.
- **Left pane:** a title, a "Take Tour(y or n)?" question, and a `C:/Home>` prompt.
- **Personal Menu:** press `Ctrl+M` to open it (empty for now).

## Controls

| Where | Key | What it does |
|-------|-----|--------------|
| Boot loader | `0`, `1`, `2` + Enter | Boot, Recovery Mode, or Safe Mode |
| Desktop | `n` | Answer "no" to the tour question |
| Desktop | `Ctrl+M` | Open the Personal Menu |
| Personal Menu | `Esc` or `Ctrl+M` | Close the menu |
| Desktop | `Esc` | Quit |
| Desktop | Click `[X]` | Quit |

## Building

You need Windows and a C++ compiler (C++11 or later).

**MinGW-w64 (g++):**

g++ main.cpp console.cpp desktop.cpp leftpane.cpp -o CommandOS

**Visual Studio:** create an empty C++ Console App project, add all the `.cpp` and `.h` files, and build.

Run `CommandOS.exe` in a normal console window. A console font that supports box-drawing characters gives the best look, and most default fonts do.

## Project structure

| File | Purpose |
|------|---------|
| `main.cpp` | The boot loader menu; starts the desktop |
| `console.h` / `console.cpp` | The only code that touches the Win32 console: input modes and the double-buffered `Screen` |
| `desktop.h` / `desktop.cpp` | Title bar, frame, event loop, resize and mouse handling |
| `leftpane.h` / `leftpane.cpp` | The left pane and the Personal Menu |

## Roadmap

- Fill in the Personal Menu
- Content for the right pane
- Recovery Mode and Safe Mode
- A real command prompt
- Domain-Specific Language (DSL)
- Games

## Inspiration

CommandOS is inspired by the look of [TempleOS](https://templeos.org/). It's an independent project, uses none of TempleOS's code, and is not affiliated with it.
