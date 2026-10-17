# SDL3 (Wind Fork)

This is a fork of [libsdl-org/SDL](https://github.com/libsdl-org/SDL) maintained for the **Wind** game engine and editor.

## Differences from Upstream

### Windows (Win32)
- **Topmost window Z-order on hover (E20):** Disabled `WIN_OnWindowEnter` calling `WIN_SetWindowPositionInternal` on mouse hover for `SDL_WINDOW_ALWAYS_ON_TOP` windows. Hovering over a window no longer alters or scrambles the Z-order of topmost or owned windows.
- **Window Owner & Topmost state (E20):** In `WIN_SetWindowParent`:
  - Dispatched `SetWindowPos` with `SWP_FRAMECHANGED` to properly inform the Win32 window manager of the owner change (`GWLP_HWNDPARENT`).
  - Preserved `SDL_WINDOW_ALWAYS_ON_TOP` state (`HWND_TOPMOST`), preventing Windows from implicitly stripping topmost status when assigning a parent.

---

Simple DirectMedia Layer (SDL for short) is a cross-platform library
designed to make it easy to write multi-media software, such as games
and emulators.

You can find the latest release and additional information at:
https://www.libsdl.org/

Installation instructions and a quick introduction is available in
[INSTALL.md](INSTALL.md)

This library is distributed under the terms of the zlib license,
available in [LICENSE.txt](LICENSE.txt).

Enjoy!

Sam Lantinga (slouken@libsdl.org)
