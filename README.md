# zinzza Note Sync for Obsidian

Keep a folder of your Obsidian vault in sync with a note in [zinzza Note](https://note.zinzza.org), a collaborative Markdown memo app. Files you have open are co-edited with the web in real time (with remote cursors); everything else in the linked folder is synced in the background, including attachments. Works on desktop and mobile.

This repository only hosts the plugin releases. The source lives in the private zinzza Note monorepo.

## Install with BRAT (recommended — gets updates automatically)

1. In Obsidian, open **Settings → Community plugins → Browse**, install **BRAT** (Beta Reviewers Auto-update Tool) and enable it.
2. Open the BRAT settings, choose **Add Beta plugin**, and enter:

   ```
   zinzza/zinzza_note_plugin
   ```

3. Turn on **Auto-update plugins at startup** in the BRAT settings. New releases are then installed the next time Obsidian starts.
4. Enable **zinzza Note Sync** in **Settings → Community plugins**.

## Install manually

1. Download `notebooks-sync.zip` from the [latest release](https://github.com/zinzza/zinzza_note_plugin/releases/latest/download/notebooks-sync.zip).
2. Unzip it into your vault's `.obsidian/plugins/` folder so that a `notebooks-sync` folder appears (containing `manifest.json`, `main.js`, `styles.css`).
3. In **Settings → Community plugins**, turn off Restricted mode, refresh the list, and enable **zinzza Note Sync**.

Manual installs do not update themselves; download a new zip when a new version is released.

## Set up

1. In zinzza Note, open **Account settings → API tokens** and create a token. It is shown only once and grants access to your notes — do not share it.
2. In Obsidian, open **Settings → zinzza Note Sync**, enter the server address (for example `https://note.zinzza.org`) and the token, then press **Test connection**.
3. Choose **Link a note** and pick a note and a vault folder. To upload a whole vault as a new note, choose **(Create a new note)** and leave the folder empty.
4. If the folder already has files, decide which side wins: **Upload vault content** replaces web memos with the same name with your files (the previous server text stays in the memo's version history), and **Overwrite with server content** replaces the files in the folder with the web content. Keep a separate copy of anything important first.

How files map: folder = category, `name.md` = memo, `assets/` = attachments. Images, audio, video and PDFs anywhere in the linked folder are synced as attachments and land in the same place on other devices. `.obsidian/`, `.git/`, `.trash/` and other file types (`.canvas`, `.svg`, …) are not synced. The plugin never writes sync metadata into your files.

## Network use

The plugin sends and receives the content of the linked folder (Markdown text, attachments, file names and paths) to and from the zinzza Note server you configure, and nothing else. It does not contact any other server. The server address and API token are stored in the plugin's data file (`.obsidian/plugins/notebooks-sync/data.json`).

## Versions

Release tags follow the plugin version (`0.2.0`, `0.2.1`, …). Each release carries `manifest.json`, `main.js`, `styles.css` and `notebooks-sync.zip`.

## License

© zinzza Note. All rights reserved. The plugin is distributed for use with zinzza Note; redistribution of the code requires permission.
