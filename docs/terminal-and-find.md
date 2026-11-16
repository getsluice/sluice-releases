# Terminal and Find

[User guide](README.md) › Terminal and Find

Terminals and searches are tools. Each one shows in the bottom panel, as a tab after **Transfers** and **Editing**, or in a tab of its own at the top of the window, filling the space under it. The button at the right of a tool's header moves it: **Open in a Tab** moves it to the top, and **Move to the Panel** moves it back. A terminal keeps its shell and everything it showed, and a search keeps its results.

## Terminal

A terminal opens on the server you're browsing, already logged in, in the folder you're looking at. It uses the same connection, so you don't log in a second time.

### Open a terminal

- Choose **Terminal** on the toolbar, or press ⌃\` (File › Open Terminal), to open one in the bottom panel.
- Choose File › Open Terminal in New Tab to open one in a tab of its own.
- Right-click a folder, or the empty space in the file list, and choose **Open terminal here**.

Terminals work on SFTP and SCP sites. FTP has no terminal, so on FTP sites the Terminal button is greyed out.

You can have up to four terminals on each server. The first is named after the site, and the next ones are numbered, such as "My shop 2". The terminal's header shows `user@host` and the folder it started in.

### Using it

- Every key goes to the shell, Tab and Escape included. To move out of a terminal from the keyboard, press ⇧⌘G (Go › Go to Folder…), which takes you to the path bar. Menu shortcuts with ⌘ still work.
- Right-click in the terminal for **Copy**, **Paste**, **Select All** and **Clear**.
- The terminal fits itself to its space when you resize the window or the panel.

### When the shell ends

When you leave the shell, for example with `exit`, the header says "The session has ended." If the connection is lost, it says "The connection was lost." **Start Again** opens a new shell in the same folder, and **Close** closes the terminal.

A terminal stays open when you close the server's tab it came from, and keeps its connection open until you close it.

### If a terminal won't open

| Message | What it means |
| --- | --- |
| Four terminals are already open on this server. Close one to open another. | Each server can have four at a time. |
| This server doesn't allow terminal sessions. | The account or the server doesn't allow a shell. |
| The server refused to open another session on this connection. Close a terminal, or wait for transfers to finish, and try again. | The server limits how much can happen at once on one connection. |

## Find

Find searches a folder, and every folder inside it, for files and folders by name, so you don't have to click through them one by one.

### Start a search

- Press ⌘F (File › Find Files…), or choose **Find** on the toolbar, to search the folder you're in.
- Right-click a folder, or the empty space in the file list, and choose **Find files here…**.

The **Find Files** sheet says which folder it searches. Type what to find in **Name**, such as `*.php; config*`.

- Use `*` for any number of characters, and `?` for one character.
- Separate several names with ";".
- A name without a wildcard finds every name that contains it. For example, `config` finds `wp-config.php`.
- A name with a wildcard must match the whole name. For example, `*.php` finds `index.php` but not `index.php.bak`.
- Capitals don't matter.

Tick **Include hidden files** to search hidden files and folders too. It starts ticked when hidden files are showing. Without it, Sluice doesn't look inside hidden folders.

Choose **Find**, or press Return, to show the results in the bottom panel. Choose **Find in New Tab** to show them in a tab of their own. The next search starts with the name you last searched for.

Find doesn't follow links into other folders, so a link that loops back can't keep a search going.

### Results

Results come in as Sluice finds them. The header says how far it has got, such as "Searching… 120 folders, 8 found", with **Stop**. When the search ends, it says what it found, such as "8 found in 340 folders", with **Find Again**, which opens the sheet with the same name and folder.

- A search stops at 10,000 results, and says "Stopped at 10,000 results. Try a narrower name."
- Folders Sluice couldn't read are counted, such as "2 folders couldn't be read". Hover over that note to see which.
- If nothing matches, the results say "No files found."

The results have **Name**, **Folder**, **Size** and **Modified** columns. Click a heading to sort by it.

- Double-click a result, or select it and press Return, to open it. A folder shows in the server's tab, and a file opens for editing.
- Right-click a result for **Edit**, **Open with built-in editor**, **Show in Folder** and **Copy path**. **Show in Folder** shows the folder the result is in, with the result selected.

The search's tab is named after what you searched for.
