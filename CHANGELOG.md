# Changelog

## [Unreleased]

## [0.9.24] - 2026-10-30

### Added
- **Start PowerPaste from quick paste.** Right-click a clip in the list and choose to go down or up from it, without opening KlipShot's window. If you've typed a search, it pastes only the matching clips.

### Changed
- **PowerPaste's choices now say down or up the list**, not older or newer clips, because clips can be rearranged.

## [0.9.23] - 2026-10-30

### Added
- **Copies that apps mark as private aren't saved.** Password managers usually mark what they copy so clipboard tools leave it out, and KlipShot now does. To save those copies too, untick **Don't save copies that apps mark as private** in Tools → Settings → History. They'd then be kept unencrypted like every other clip.

### Changed
- **KlipShot starts faster and uses less memory.** `KlipShot.exe` is no longer compressed, so it takes more disk space (about 200 MB), but the setup download is smaller.
- **A copy over 50 MB isn't saved.** It stays on the clipboard to paste, and a notice says why. Everything about a clip that size is slow, and it would stay in the database.
- **KlipShot does less while it's hidden.** A copied image is only decoded and checked for QR codes when you open the window, and clips only keep their picture in memory while they're on screen.
- **Faster with many clips or folders.** Typing in the search box and most copies no longer rebuild the folder list, and deleting or moving many clips at once is much quicker.
- **KlipShot keeps pointing "start when I sign in" at the copy that set it.** Running another copy, such as a portable one, used to take the entry over. It's now only updated if the exe it points to has gone.

### Fixed
- **Deleting a folder no longer loses its clips.** They went to the bottom of the InBox, where the next copies trimmed them away. They now go to the top, the InBox list shows them straight away, and if that takes the InBox over its limit, the question says how many of the oldest clips will go.
- **Copying the same text again with different formatting keeps the new formatting.** The newest copy's formatting replaces the old, so what you paste matches what you copied last.
- **A damaged database no longer leaves KlipShot running with no window or tray icon.** Starting it again only said it was already running. It now says what's wrong, offers to restore a backup, and quits.
- **Restoring a backup or importing a portable copy can't trip over the old copy still closing.** The clips KlipShot had are kept with any changes not yet written into the main file.
- **Quitting, updating, restoring or importing asks first about unsaved screen clip markup.** Before, No still threw the clip away when quitting. During an update, a question left unanswered could leave KlipShot closed and not updated.
- **Ctrl+V is no longer sent to the wrong window.** If Windows won't switch back to your app, the clip stays on the clipboard and a notice says so. KlipShot also waits a moment for Shift, Ctrl or Alt to be let go before pasting.
- **A folder that's just been deleted can't reopen.** A click still being handled could open it, and new copies then went where they couldn't be seen.
- **The uninstaller's "delete my clips" leaves nothing behind.** The copies KlipShot keeps before a restore, an import or a database upgrade are deleted too.
- **An edited image is no longer lost if its folder is deleted while the editor is open.** It's saved in the InBox instead.
- **Changing the InBox size no longer overstates how many clips will go.** Pinned clips were counted, but they're never removed.
- **Clean up links removes HubSpot tracking too**, such as `_hsenc` and `_hsmi`.
- **Folder paths with a `;` in them work** for backups, restoring and importing.
- **The screen clip editor shows the tool you picked in the Classic theme**, which could keep the colour of the theme before it.
- **The check for a repeated copy works when the clocks go back** or when you change time zone.

## [0.9.22] - 2026-10-30

### Added
- **Recipes.** Put blanks in a text clip, such as `Hi {{name}}, your order {{clipboard}} ships {{date+3}}`. When you paste it, a small window asks for the blanks, and `{{clipboard}}`, `{{date}}`, `{{date+3}}` and `{{time}}` fill themselves in, in the format you pick in Tools → Settings → Pasting. The clip itself isn't changed.
- **Show links.** When a clip has web links, email addresses, US street addresses or phone numbers in it, a **Show links** button appears above the preview. Click it and they become clickable: links open in your browser, email addresses in your mail app, street addresses in Google Maps and phone numbers in your calling app. It works on image clips too, with each one marked on the picture, and QR codes in images are read as well. Right-click one to copy just that link or address to a new clip. In quick paste, right-click a clip to see them. Nothing pops up, and clips still paste exactly as copied. Turn it off, all or by type, in Tools → Settings → Smart actions.

## [0.9.21] - 2026-10-29

### Added
- **Move to top or bottom.** Right-click a clip and choose **Move to → Top** or **Bottom** (also in the Edit menu, or press Alt+Home or Alt+End) to send it to the top of the list, just below any pinned clips, or to the bottom. Works on several clips at once and keeps their order. Pinned clips move within the pinned ones.

### Changed
- **Move to folder is now Move to**, with Top and Bottom at the start of it, then your folders.

## [0.9.20] - 2026-10-29

### Added
- **Folders inside folders.** Right-click a folder and choose **New folder inside**, or drag a folder onto another one. Click the arrow beside a folder to show or hide what's inside; KlipShot remembers which ones are open. Move to folder lists them indented under their parent. Deleting a folder moves the folders inside it up a level. The InBox still can't hold folders. (An older KlipShot shows them all at the top level.)
- **You can see where a drag will drop.** A line shows where a clip will land between two others, or where a folder will go; a box shows the folder it will go into. The clip or folder you're dragging fades, and its name follows the mouse. The list scrolls when you hold a clip near its top or bottom.

### Changed
- **Dropping a clip on the bottom half of a row now puts it below that clip**, and the top half above it, as the line shows. Before, it always took that clip's place.

## [0.9.19] - 2026-10-29

### Changed
- **Saving an edited text clip makes a new clip and keeps the original.** The new clip goes just above the original, in the same folder (pinned too, if the original is), and is selected, so the list doesn't jump. Saving again while you're still on the new clip updates it instead of making another. A formatted original keeps its formatting; the new clip is plain text.
- **Edited images go just above the original too.** Copy in the markup editor, after Edit image, used to save the result at the top of the list as if copied from KlipShot. It now goes just above the original, keeps the original's app, is selected, and is on the clipboard ready to paste. New screen clips still go to the top.

### Fixed
- **Ctrl+Z while editing a clip's text stops at the clip as it was.** Pressing it again used to bring back the text of the clip you looked at before. That text was then saved over the clip you were editing as soon as you clicked away.
- **Copies aren't lost when another app keeps the clipboard busy.** Some apps, such as Excel, Remote Desktop and some password managers, hold the clipboard for a moment after you copy. KlipShot could then show a "KlipShot error" message, or quietly not save the copy. It now waits and tries again a few times. If the clipboard is still locked after that, a notice says the copy wasn't saved, instead of an error message.
- **Pasting or copying a clip from KlipShot no longer saves it again as a new copy.** With a big picture, or a busy clipboard, the clip could jump to the top of the list with the other app's name and play the copy sound. And a copy you made right after pasting from KlipShot is now always saved; before, a copy within less than half a second could be missed.
- **Copying a big picture no longer makes KlipShot stutter.** Turning it into PNG and making its thumbnail now happen in the background.

## [0.9.18] - 2026-10-29

### Added
- **Quick paste.** Press **Ctrl+Alt+V** while you're typing in any app, and a small list of your InBox clips opens right at the text cursor, so you don't have to switch to the KlipShot window. Type to search, use the arrow keys or the mouse wheel to pick a clip and press Enter to paste it. Right-click a clip to paste it as plain text or with another Paste as text change. Esc or clicking away closes it. In apps that draw their own text cursor, such as many browsers, the list opens at the mouse instead. Ctrl+Alt+V is Paste Special in Word and Excel; pick a different key (or none) in Tools → Settings → Keys.
- **One page for all of KlipShot's keys.** Tools → Settings → Keys lists quick paste and the four screen clip keys, each with a picker and whether it's working. If another program has one of them, it says so; close that program and click **Try again**. When KlipShot starts, one notice now names every key that's in use elsewhere.

### Changed
- **The README is short now, and the full instructions moved to a new [KlipShot guide](GUIDE.md)**, arranged by task. Help → How to use KlipShot opens the guide. It also covers things the README had missed, such as all four screen clips in the tray menu and the keys that work in any app.
- **The screen clip keys moved** from Tools → Settings → Screen clips to the new Keys page. How long a delayed clip waits is still under Screen clips.
- **The "From app" name is right for Store apps.** Clips copied from apps such as Calculator or Settings were saved as coming from "Application Frame Host", the Windows process that holds those apps' windows; they now show the app's own name. Apps whose name was their file name, such as the new Notepad ("Notepad.exe"), now show just "Notepad".
- **KlipShot now marks your clips' database with a version number**, so later versions can upgrade it safely. If you go back to an older KlipShot after using a newer one, it warns you that some newer things may be missing, and it won't restore a backup made by a newer version. When a future version changes the database, KlipShot first saves a copy of it as it was (KlipShot.before-v2.db and so on, next to KlipShot.db; only the latest is kept), and the change is all or nothing, so a failed upgrade leaves your clips as they were.
- **Copying something again moves its clip to the top** instead of saving it a second time. The clip gets the new copy's time and app. This works in the InBox and in the folder that's open; a clip in another folder stays where it is, and a new one is saved.
- **When the InBox is full, the clips at the bottom of the list go first.** Before, the clips that were copied longest ago went first, even if you had dragged them up the list or moved them back from a folder. Pinned clips and clips in folders are still kept for good.

## [0.9.17] - 2026-10-28

### Added
- **Keep the sound ready so no beep is missed.** A new setting in Tools → Settings → Sounds and look, off at first. Turn it on if copy beeps are sometimes missing, as can happen when KlipShot runs on a remote desktop or VDI: their sound often drops short beeps that come after a quiet spell. KlipShot then plays silence all the time, so each beep goes straight through. Windows sees sound playing, so the PC may not go to sleep by itself, and Bluetooth headphones stay connected and use battery.

## [0.9.16] - 2026-10-28

### Fixed
- **Copy beeps are easier to hear.** On some PCs the beep was sometimes silent, because the speakers or headphones were still waking up when it played and it was over before they did. KlipShot now gives them longer to wake up and makes the beeps a little longer, so they can be heard even if the start is cut off. The beep comes about a fifth of a second later than before.

## [0.9.15] - 2026-10-27

### Fixed
- **Scrolling clips work in Plex** and other web apps whose background stays put while the page scrolls over it. Plex shades its background a little darker towards the bottom of the window, so nothing lined up exactly and the clip stopped after the first screen. Scrolling clips also cope better with pages that rearrange themselves on the first scroll, such as a top bar that hides as soon as you scroll: KlipShot scrolls back and starts again instead of stopping.

## [0.9.14] - 2026-10-27

### Added
- **Scrolling clips.** **Clip a scrolling region** in the tray icon's menu (and a key in Tools → Settings → Screen clips, none at first) lets you pick the part of a window that scrolls, then scrolls it down and joins it all into one tall clip: a whole web page, document or chat. Headers and toolbars that stay put are kept once. Side menus and columns that stay put (YouTube's menu, Facebook's shortcuts and contacts, Craigslist's filters) and the page's scrollbar are left off, so clicking a whole web page works as well as dragging inside the part that scrolls. It waits for posts and videos that load as you scroll, and keeps the mouse over the scrollbar so videos don't start playing under it. It stops at the end of the page, or when you press Esc or the key again. A tall clip opens in the editor at a readable size and scrolls there.
- **Delayed screen clips.** **Clip a region in 5 seconds** in the tray icon's menu counts down in a corner of the screen, then freezes it as F9 does, so you have time to open a menu or bring up a tooltip first. The countdown doesn't take the focus, so menus stay open. In Tools → Settings → Screen clips you can give it a key (none at first) and choose 3, 5 or 10 seconds. Pressing the key again during the countdown stops it.
- **Copy text from image.** Select an image clip and press Ctrl+T (or right-click it → Copy text from image) to copy the words in it. They're saved as a text clip too, and the image clip stays as it was. The text is read by Windows on your PC, in the languages set up in Windows.
- **Search finds image clips by the words in them.** KlipShot reads the text in each image clip a moment after it's copied, and in the image clips you already have the first time this version starts.
- **Restore a backup from Settings.** **Restore a backup...** under Backups in Tools → Settings lets you pick a backup, asks first, then restarts KlipShot with that backup's clips, folders and settings. Before, this meant quitting KlipShot and copying files by hand. Your backup settings stay as they are, and what was there before is kept as `KlipShot.before-restore.db`, so you can restore that to undo it.

## [0.9.13] - 2026-10-27

### Fixed
- **Panes in Windows Terminal.** After F9, pointing inside Windows Terminal outlined the whole window, as if it were all title bar. Now its contents are outlined, and only the tab bar's empty space and buttons take the whole window. Other apps that draw their own title bar the same way benefit too.

### Changed
- **The pane outline keeps up with the mouse in slow apps.** After F9, KlipShot remembers what each app has told it about its layout while the picker is open, instead of asking again at every move. In Electron apps (LM Studio, Discord, VS Code…) and Word, where asking takes up to half a second, the outline now follows the mouse many times faster. The panes picked are the same. Finding panes in the picture is also much faster, most of all in apps full of photos or thumbnails (ON1 Photo RAW, model and photo libraries), where it took up to 0.4 seconds a move. And in every app, the outline now keeps moving with the mouse instead of waiting for it to stop (this was most noticeable in Excel).

## [0.9.12] - 2026-10-27

### Changed
- **Clicking to clip a pane picks better panes.** A list, table or tree (such as KlipShot's own clip list, or a file list) is now outlined whole, rather than a row, a cell or a few rows of it. A picture is outlined whole too. Web pages in Chrome, Edge and Vivaldi are now seen inside, down to their tables and sidebars, where before only the whole page was found. A pane is no longer outlined across two parts of an app (a toolbar and the table under it, say). And the outline no longer flickers between two panes while the mouse moves inside one: it changes only once it's sure. In web pages, hidden layers (such as YouTube's video previews) are no longer outlined in place of what you see. The outline also shows as soon as F9 is pressed, without moving the mouse.

### Added
- **Drags snap to edges.** When you drag out a region after F9, its sides snap to a nearby edge, such as a pane's border or the edge of a picture, so the clip lines up with what's there. Hold Alt while dragging to place the sides freely.

## [0.9.11] - 2026-10-27

### Changed
- **Clicking to clip a pane works in many more apps.** After F9, KlipShot now also looks for panes in the picture itself: areas with a border or their own background, such as a sidebar, a toolbar, a list or a chat. So panes are outlined in apps that don't describe their layout to Windows, like Qt apps, games, video and remote desktops. Chrome, Edge, Firefox and apps built on them (Discord, VS Code, Slack…) are also asked to describe their pages as soon as F9 is pressed, so panes inside web pages are found sooner. Pointing at the bare desktop no longer outlines the gaps between windows.

## [0.9.10] - 2026-10-27

### Added
- **Click to clip a window or pane.** After pressing F9, the window or pane under the mouse (such as a sidebar or a dialog's panel) is outlined. Click without dragging to clip just that; drag as before to pick any region. Point at the title bar or the window's edge to take the whole window. This works inside most apps, including browsers and Office.

## [0.9.9] - 2026-10-27

### Added
- **A setup, as well as the portable zip.** Each release now also has `KlipShot-<version>-win-x64-setup.exe`. It installs KlipShot just for you, with no admin rights needed, into `%LocalAppData%\Programs\KlipShot`, and keeps your clips in that same folder. It adds KlipShot to the Start menu, and can add a desktop shortcut and start KlipShot when you sign in. Uninstalling asks whether to delete your clips too, and keeps them unless you say yes. The portable zip works as before.
- **Installed copies update with the setup.** Help → Check for updates downloads the new setup, checks it, runs it without any questions and restarts KlipShot. The downloaded setup is then deleted.
- **Import from a portable copy.** The first time an installed KlipShot starts, it offers to bring in the clips, folders, settings and backups of a portable copy. **Import from a portable copy...** in Tools → Settings → Starting up does the same at any time. The portable copy isn't changed.

## [0.9.8] - 2026-10-27

### Added
- **Pick where backups go.** **Change folder...** under Backups in Tools → Settings sends backups to any folder you choose, such as another drive or a synced folder. **Use default folder** goes back to the `Backups` folder next to `KlipShot.db`. Backups already made stay where they are, and only the newest 10 in the chosen folder are kept.

### Changed
- **Settings fits on the screen.** Tools → Settings now lists its sections on the left (Pasting, Starting up, History, Backups, Screen clips, Sounds and look, Updates) and shows one at a time on the right, instead of one long page that could run off the bottom of the screen. While KlipShot runs, it opens on the section you last looked at.

## [0.9.7] - 2026-10-27

### Added
- **Rename clips in the list.** Right-click a clip and choose **Rename...** (or select it and press F2, or use Edit → Rename). The new name is only what the list shows: the clip's text, image or files stay exactly as copied, and pasting it pastes the original. Search finds clips by their new name too. Leave the name empty to show the clip's own text again.
- **Automatic backups of your clips** (Tools → Settings, off unless you turn it on). Pick every hour, every 6 hours, every day or every week, and KlipShot saves a copy of its database, with all your clips, folders and settings, into a `Backups` folder next to `KlipShot.db` while it runs. The newest 10 copies are kept. **Back up now** makes one at any time, and **Open backups folder** shows them. The README explains how to restore one.

## [0.9.6] - 2026-10-27

### Fixed
- **Screen clips no longer zoom in on scaled displays.** On a monitor set to 125% (or any scale other than 100%), pressing F9 could make the frozen screen jump larger. The clip overlay now sizes itself from the window it's actually drawn in rather than the scale Windows reports, and puts itself back over the screen if Windows resizes it for a scale change.

## [0.9.5] - 2026-10-27

### Changed
- Nothing new to use. This release lets 0.9.4 try updating itself (Help → Check for updates).

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
