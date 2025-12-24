# WindowsTools

A collection of personal efficiency tools.

All tools in this repository are licensed under CC BY-ND 4.0.

After running a tool, you may find it running in the system tray. Right-click the tray icon to open a context menu where you can exit the application.

> [!CAUTION]
> The following operations may or may not be flagged as suspicious by Anti-Virus or Anti-Cheat software. Use them at your own risk.
>
> `cmd-boss-key.exe` and `screenshot-boss-key.exe` use the `RegisterHotKey` API to register global key combinations.
>
> `smart_paste.exe` uses `SetWindowsHookEx(WH_KEYBOARD_LL, ..., GetModuleHandle(NULL), 0)` to monitor keyboard activity.
>
> `cmd-boss-key.exe` and `smart_paste.exe` use COM interfaces to retrieve the file system path of the currently focused Windows Explorer window.
>
> `screenshot-boss-key.exe` draws a topmost overlay window containing the current screenshot (created using `BitBlt`) and detects which window is under the cursor using `GetTopWindow`, `GetWindowLong`, `GetWindowRect`, `PtInRect`, `GetAncestor`, and `GetNextWindow`.
>
> I have used `cmd-boss-key.exe` and `screenshot-boss-key.exe` in several EAC-protected games and have seen no negative effects on my game account.

> [!NOTE]
> More than 50% of the code is AI-generated. I created these tools for personal efficiency improvements and to quickly resolve my own needs, rather than for polished production use.

## Terminal Boss Key Utility (cmd-boss-key.exe)

Registers the global key combination <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>T</kbd>. Upon pressing this combination, a Windows terminal will spawn, similar to the behavior in Ubuntu systems. Additionally, if your currently focused window is Windows Explorer, the terminal will open with your current explorer path as the working directory.

## Screenshot Boss Key Utility (screenshot-boss-key.exe)

Registers the global key combination <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd>. Upon pressing this combination, the current screen is captured and drawn onto a darkened overlay, where you may drag to select a region or snap to a window. Right-click the overlay to close it, or double-click (Left Mouse Button) to copy the selected region to the clipboard.

## Smart Paste (smart_paste.exe)

Monitors the key combination <kbd>Ctrl</kbd>+<kbd>V</kbd> via a low-level keyboard hook. If the clipboard contains text or image data and the currently focused window is Windows Explorer, pressing this key combination will paste that data as a file into the current directory.
