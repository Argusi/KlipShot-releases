# KlipShot

Clipboard history and screen clips for Windows, in the system tray. Everything you copy is saved, and you can paste it back into whatever app you were using. Press F9 to clip part of the screen, mark it up, and it's saved with the rest of your clips.

KlipShot used to be called Clippy.

![KlipShot window showing the InBox, its folders and a letter to a noisy neighbour in the preview pane](docs/screenshot.png)

- Keeps text (with its formatting), images and copied files, and finds any of them with search.
- Paste any clip back with Enter or a double-click, or paste text with a change such as Plain text, UPPERCASE or Single line.
- Quick paste: press Ctrl+Alt+V while typing anywhere to pick a clip from a small list at the text cursor.
- PowerPaste: paste a run of clips one after another with Ctrl+V.
- Rename clips, pin them to the top, and file them into folders, which can hold folders of their own. Lock a folder to keep it as it is.
- Screen clips: F9 for a region, Print Screen for the whole screen, a delayed clip for menus and tooltips, and a scrolling clip for whole web pages. Mark them up with arrows, boxes, a pen, a highlighter, text and blur, and crop them.
- Copy the words out of any image clip; search finds images by the text in them.
- Automatic backups, ten themes (or follow Windows light and dark), optional sounds, and updates from inside the app.
- A setup, or one portable `KlipShot.exe` you unzip anywhere. Neither needs admin rights, and everything stays on your PC.

## Install

Each release on [Releases](https://github.com/Argusi/KlipShot-releases/releases) comes two ways. Both are the same KlipShot; pick one.

- **Setup:** download `KlipShot-<version>-win-x64-setup.exe` and run it. It installs KlipShot just for you into `%LocalAppData%\Programs\KlipShot` and adds it to the Start menu.
- **Portable:** download `KlipShot-<version>-win-x64.zip`, unzip it into any folder (or a USB stick) and run `KlipShot.exe`. Your clips are kept in that folder.

KlipShot isn't code-signed, so the first time you run it, Windows SmartScreen may say "Windows protected your PC". Click **More info**, then **Run anyway**. No .NET install is needed.

KlipShot starts in the tray: look under the **^** by the clock. Drag the paperclip icon onto the taskbar to keep it in view.

## Using KlipShot

1. Copy something as usual (Ctrl+C in any app). KlipShot saves it.
2. Click the tray icon to open KlipShot.
3. Select a clip and press **Enter**. KlipShot hides and pastes it into the app you were using.

Or, while typing anywhere, press **Ctrl+Alt+V** to pick a clip without opening the window, and press **F9** to clip part of the screen.

![Quick paste in Notepad: Ctrl+Alt+V opens the list at the text cursor, typing "order" narrows it, and Enter pastes the tracking link](docs/quickpaste.gif)

**The [KlipShot guide](GUIDE.md) explains everything else:** pasting, quick paste, PowerPaste, folders, screen clips and the markup editor, keys, settings, backups, updates, and moving from the portable copy to the setup. In KlipShot, **Help → How to use KlipShot** opens it.

See [CHANGELOG.md](CHANGELOG.md) for what's new.

## Licence

KlipShot is © 2026 Bruce Maloney. All rights reserved. You may use it free of charge, but not copy, share or change it; see [LICENSE](LICENSE). KlipShot comes with no warranty. Downloads and updates: [github.com/Argusi/KlipShot-releases](https://github.com/Argusi/KlipShot-releases).
