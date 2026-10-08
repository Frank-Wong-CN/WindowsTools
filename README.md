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
> More than 70% of the code is AI-generated. I created these tools for personal efficiency improvements and to quickly resolve my own needs, rather than for polished production use.
> 
>
> None of the tools make Internet connections to remote machines unless:
>
> 1. This repo explicitly stated the tool makes proactive Internet connections to any server.
> 2. The user actively operated the tool to make Internet connections to a designated target.

## Terminal Boss Key Utility (cmd-boss-key.exe)

Registers the global key combination <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>T</kbd>. Upon pressing this combination, a Windows terminal will spawn, similar to the behavior in Ubuntu systems. Additionally, if your currently focused window is Windows Explorer, the terminal will open with your current explorer path as the working directory.

## Screenshot Boss Key Utility (screenshot-boss-key.exe)

Registers the global key combination <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>S</kbd>. Upon pressing this combination, the current screen is captured and drawn onto a darkened overlay, where you may drag to select a region or snap to a window. Right-click the overlay to close it, or double-click (Left Mouse Button) to copy the selected region to the clipboard.

## Smart Paste (smart_paste.exe)

Monitors the key combination <kbd>Ctrl</kbd>+<kbd>V</kbd> via a low-level keyboard hook. If the clipboard contains text or image data and the currently focused window is Windows Explorer, pressing this key combination will paste that data as a file into the current directory.

## Encoding Converter (u8conv.exe)

A command-line tool for automatic text encoding detection and conversion between major file encodings. Uses [uchardet](https://github.com/BYVoid/uchardet) to detect source encoding. Simply run `u8conv input output` to convert files to UTF-8, or specify custom encodings as needed. Use `-h` for usage details and `-l` to list all supported encodings. Note that if your console did not display the filename properly, it's probably because your current code page does not support the characters, but the conversion will continue to work.

## Git Repo Clone & Archive (gitca.exe)

A command-line tool for cloning and archiving git repositories using [libgit2](https://github.com/libgit2/libgit2) and [libzip](https://github.com/nih-at/libzip). Submodules are recursively cloned with infinite retry (which is why this tool existed in the first place: git just quits after the second failed attempt). Provide one or more repository URLs to archive each as `<author_name>/<repo_name>-git-<default_branch>-<cur_commit_date>-<cur_commit_hash>.zip`. EXISTING `<author_name>/<repo_name>` DIRECTORIES ARE AUTOMATICALLY REMOVED before cloning to ensure clean archives. LFS support is limited. For private repositories, configure your username and personal access token in `gitca.env`.

## Goodnotes 5 Converter (gnparse.exe)

This is a CLI tool that converts Goodnotes 5 notebooks into open format (InkML) files, renders pages as PNG or SVG, and assembles PDFs. It preserves stroke geometry, colors, images, and page backgrounds, with support for text and erased strokes.

## DiskTree (DiskTree.zip)

DiskTree is a portable disk analyzer that scans local drives, folders, network shares, and SSH servers. Inspired by both WizTree and SquirrelDisk, it shows storage use through interactive sunburst charts, treemaps, directory trees, and file search. It imports and exports WizTree-compatible CSV files and compact WIDX snapshots through the interface or CLI. Backup comparison counts matching paths across snapshots and filters results by source or backup count.

# Credits

<a href="https://www.flaticon.com/free-icons/screenshot" title="screenshot icons">Screenshot icons created by Hilmy Abiyyu A. - Flaticon</a>

<a href="https://uxwing.com/file-icon">File</a> and <a href="https://uxwing.com/image-file-icon">image</a> icons are downloaded from <a href="https://uxwing.com">uxwing.com</a>.

<a href="https://www.freepik.com/free-vector/folders-set-multiple-styles_222524092.htm">Folder</a> icon is created by <a href="https://www.freepik.com/author/juicy-fish">juicy_fish</a> and downloaded from <a href="https://www.freepik.com">www.freepik.com</a>.

<a href=https://www.pngmart.com/image/292006/png/292005 target="_blank">Clipboard, Share, Copy, Paste, Organize PNG</a>
