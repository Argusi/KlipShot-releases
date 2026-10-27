# Changelog

## [Unreleased]

## [0.9.4] - 2026-10-27

### Added
- **KlipShot can update itself.** When **Help → Check for updates** (or the startup notice) finds a newer version, KlipShot asks "Update now?". Nothing downloads without a yes. It then downloads the release from GitHub with a progress bar, checks it against GitHub's SHA-256 checksum and refuses anything that doesn't match, swaps `KlipShot.exe` for the new one and restarts. Your clips (`KlipShot.db`) aren't touched.
  - If KlipShot's folder isn't writable (for example under `Program Files`), it offers the download page instead, as before.
  - KlipShot isn't code-signed, so SmartScreen or antivirus may now and then be wary of a freshly downloaded exe. That's no different from downloading it by hand.
  - This version is the first with the updater, so the first update it can install by itself is the one after it. To get this version, update by hand.

## [0.9.3] - 2026-10-27

### Added
- **Check for updates when KlipShot starts** (Tools → Settings, off unless you turn it on). At most once a day, KlipShot quietly asks GitHub for the latest version, and a notice by the clock opens the download page if there is a newer one.

## [0.9.2] - 2026-10-27

### Changed
- The theme picker is gone from **Tools → Settings**. Pick themes in **View → Theme**, which stays open while you try them.

## [0.9.1] - 2026-10-26

### Changed
- **Releases have moved** to [github.com/Argusi/KlipShot-releases](https://github.com/Argusi/KlipShot-releases/releases). **Help → Check for updates** and **Help → How to use KlipShot** now look there, so update checks work again.
- **KlipShot is no longer under the GPL.** It is free to use, with all rights reserved; see `LICENSE`.

## [0.9.0] - 2026-10-26

### Added
- **Six new themes** (View → Theme): Latte (soft pastel with purple), Solarized Light (warm cream with orange), Dracula (purple and pink), Gruvbox (warm retro amber), Everforest (muted green) and Rosé Pine (deep plum with rose).

### Changed
- **New app icon**: the paperclip over a screen-capture frame, on a blue gradient tile. `KlipShot.exe` now carries the icon itself, so Explorer, Start and pinned taskbar shortcuts show it, with a separate design that stays sharp at 16 px in the tray.
- **View → Theme** stays open when you pick a theme, so you can click through them and see each one at once.

## [0.8.1] - 2026-10-26

### Added
- KlipShot is now free software under the **GNU General Public License v3**. The licence is in `LICENSE` (also in the release zip), and the About box and README say so.

### Changed
- **Help → About KlipShot** is now short: the version, who made it, the GitHub page and where your clips are stored. The how-to notes it used to have are in **Help → How to use KlipShot**.

## [0.8.0] - 2026-10-26

### Added
- **Screen clips.** Press **F9** to clip a region of the screen, or **Print Screen** to clip the whole screen. The screen freezes so menus and tooltips are kept, and the clip opens in an editor with arrow, rectangle, pen, highlighter, text, blur and crop tools, colours, line widths and undo. **Copy** saves it as an image clip; **Save** writes a PNG file. Both keys can be changed in **Tools → Settings → Screen clips**, and both captures are in the tray icon's menu.
- **Edit image** (Ctrl+E, right-click or the Edit menu) opens any image clip in the same editor. Copy saves the marked-up version as a new clip and keeps the original.

### Changed
- **Clippy is now KlipShot.** The first run takes over Clippy's clips, folders and settings, and its "start when I sign in" entry. Quit Clippy before starting KlipShot.
- **Paste as text → Without formatting** is now called **Plain text**.
- Sharper on high-DPI and mixed-DPI monitors: KlipShot now handles each monitor's scale itself.

### Fixed
- KlipShot now remembers the width of the folder list, the split between the clip list and the preview, and the width of each clip list column, not just the window's size and position.

## [0.7.0] - 2026-10-25

### Added
- **Select several clips** with Ctrl+click, Shift+click or Ctrl+A, then delete, pin or move them all at once (Del, right-click, or drag them onto a folder). Clippy asks before deleting more than one clip.
- **View → Button labels** (also in Settings) turns the names on the toolbar buttons off for an even smaller, icons-only toolbar. Point at a button to see what it does.
- **Search** box at the right of the toolbar (Ctrl+F) shows only the clips in the open folder whose text, title, file names or source app contain what you type. Esc or ✕ clears it. Down arrow moves to the results and Enter pastes the selected one. PowerPaste started during a search walks only the matching clips.

### Changed
- The Settings button is gone from the toolbar; open Settings from **Tools → Settings**.
- **Pin**, **Move to** and **Delete** are no longer on the toolbar. Right-click a clip to pin, move or delete it (also in the Edit menu, Ctrl+P to pin, Del to delete, or drag a clip onto a folder). The welcome message mentions right-click.
- Smaller toolbar: shorter button names (**Paste**, **Copy**, **Paste as**) and tighter spacing, so the whole toolbar and the search box fit on one row at the default window size. Each button's tooltip starts with its full name.

## [0.6.0] - 2026-10-23

### Added
- **Settings window** (Tools → Settings, or Settings on the toolbar) gathers every option in one place, with a line under each saying what it does. It replaces the on/off items in the Tools menu and the InBox history size submenu, and includes Start Clippy when I sign in.
- **Right-click menu on clips:** Paste into app, Copy to clipboard, Paste as text, Pin to top, Move to folder and Delete clip.
- **Move to folder** (toolbar, Edit menu and right-click) moves a clip without dragging it.
- **New folder** button under the folder list.
- A welcome note the first time the window opens, explaining how to paste a clip back.
- Hints in an empty InBox or folder, and a note above the clip list when the open folder is locked.
- The first time you start PowerPaste, Clippy explains how it works before it hides.
- **Help → How to use Clippy** opens the guide, and **Help → Keyboard shortcuts** lists the keys.

### Changed
- Clearer names: **Paste into app** and **Copy to clipboard** on the toolbar, **Paste as text** (Without formatting, Remove extra spaces, Clean up links), **Save changes** and **Undo changes** in the preview pane, **Close window (Clippy keeps running)** and **Quit Clippy (stop saving copies)** in the File menu, **Quit Clippy** in the tray menu.
- The window title shows the open folder, for example "Clippy – InBox" or "Clippy – Work".
- PowerPaste is one **PowerPaste** drop-down: Start here, then older clips, or Start here, then newer clips. **Stop PowerPaste** only appears on the toolbar while PowerPaste is on.
- The toolbar is grouped into using, organizing and PowerPaste, with Delete and Settings kept apart at the end. The Pin button reads **Unpin** on a pinned clip.
- **Save changes** and **Undo changes** only appear once you edit a text clip, and the preview header says when saving will remove formatting.
- **New folder** moved from the Tools menu to the File menu. The folder list root is now called **Folders**, and the lock options say where new copies go.
- List columns are now Clip, Copied, From app and Size. New clips record the app's own name ("Microsoft Word" instead of "WINWORD"), and older clips show it in normal case.
- In a narrow window the toolbar wraps onto a second row instead of hiding buttons. **Move to** also offers **Move to a new folder...**.

### Fixed
- Pressing Esc to close a menu no longer hides the whole window.
- The toolbar's drop-down menus (Paste as text, Move to, PowerPaste) now use the theme's colours instead of a light system look in dark themes.

## [0.5.1] - 2026-10-22

### Changed
- **Faster image copies:** images copied as PNG are saved as they are instead of being re-encoded.
- **Faster history trimming:** lowering the history size removes old clips in one step.
- The "on the clipboard" icon now sits in its own column at the left of the clip list, so titles and thumbnails stay aligned.
- The database now compacts itself at startup when more than a quarter of it is unused space, so it shrinks after the history size is lowered or large images are trimmed.

## [0.5.0] - 2026-10-22

### Added
- **Pin to top** (toolbar, Edit menu or Ctrl+P): pinned clips stay at the top of their folder or the InBox, show a pin, and are never trimmed by the history size limit.
- **Always on top** (View menu) keeps the Clippy window above other windows.
- **What's on the clipboard** is now shown: the matching clip gets a clipboard icon, and the status bar and the tray tooltip name it. It follows copies made in Clippy and in other apps.
- **Keep window open after paste** (Tools menu): Clippy comes back in front after pasting, ready for the next clip.
- **Double-click copies instead of pasting** (Tools menu): a double-click only puts the clip on the clipboard; Enter still pastes.
- **Check for updates** (Help menu) asks GitHub for the latest version and offers to open its download page. Clippy only connects when you click it.

## [0.4.0] - 2026-10-22

### Added
- **Open window at startup** (Tools menu): open the Clippy window when it starts, instead of starting hidden in the tray.

### Changed
- Clearer Help → About text, grouped by task, including the copy sounds and a link to the full guide.

## [0.3.0] - 2026-10-22

### Added
- **Copy sounds.** A short beep when a copy is saved, and a double beep when you copy the same thing twice in a row (that copy isn't saved). Turn them off with Tools → Play sounds on copy.
- **Themes** (View → Theme): Follow Windows, Fluent, Midnight, Nord and Classic. Dark themes get a dark title bar.

### Changed
- Vector icons replace the emoji glyphs, and the tray and window icon is now a paperclip.

### Fixed
- Crash when dragging a folder over the clip list.

## [0.2.0] - 2026-10-22

### Added
- **Folders** under My Clips to organize clips. Right-click My Clips (or use Tools → New folder) to create one; right-click a folder to rename, lock or delete it.
- **Locked folders.** A locked folder (🔒) never receives new copies. Copies made while it is open go to the InBox instead, the InBox turns bold, and a tray notice appears once per folder per session.
- **Return to InBox after paste** (Tools menu), so the next copy lands in the InBox.
- **Drag and drop:** reorder clips within a folder, drop clips onto a folder (or the InBox) to move them, and drag folders to reorder them.
- **Start at login** option in the tray menu.
- Single-file release build: one `Clippy.exe`, no .NET install needed.

### Changed
- New copies go into the folder you have open (unless it is locked).
- The history size limit applies only to the InBox; clips filed in folders are never trimmed.
- If the folder holding `Clippy.exe` isn't writable (for example under Program Files), the database is kept in `%LocalAppData%\Clippy` instead.
- The About box shows the real version number.

## [0.1.0]

### Added
- Clipboard history in the system tray, with an Explorer-style window.
- Keeps text, RTF, HTML, images and file lists.
- Paste into the previous app (Enter or double-click), Copy, and Paste as with text transforms.
- PowerPaste: each Ctrl+V pastes the next clip, going down or up the list.
- Edit text clips in the preview pane.
- Adjustable history size.
