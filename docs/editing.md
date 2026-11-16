# Editing files

[User guide](README.md) › Editing files

## Open a file for editing

Double-click a file in the file list. You can also select one or more files and press F4, choose **Edit** on the toolbar, or right-click and choose **Edit**. With one file selected, Return opens it too.

Sluice downloads a private copy of the file to your computer and opens it in your editor. While it downloads, the **Editing** tab of the bottom panel says "Opening…" with how far it has got. Once it's open, the file is tagged in the file list with its editor, such as "Editing in VS Code".

## Which app opens it

Sluice picks the app by the first rule that applies:

1. **Open with built-in editor** or **Open with…**, if you chose one from the right-click menu.
2. The app you've set for the file's type in Settings › Editing › **Open these file types with**.
3. For a file that isn't text, such as an image or an archive, the app your computer uses for that kind of file.
4. For a text file, the **Open text files in** setting.

### Open text files in

Set it in Settings › Editing.

- **Built-in editor**: Sluice's own editor. This is the default.
- **Default text editor**: the text editor your computer uses for text files.
- **VS Code**: Sluice finds VS Code by itself, so you don't need to install its `code` command. If VS Code isn't installed, Settings says "VS Code isn't installed, so text files open in the built-in editor."
- **Other App…**: choose any app. Once chosen, it's listed by name in the menu.

### Open these file types with

This table, in Settings › Editing, sends files that end in a particular way to a particular app, whatever the setting above says. Choose **+**, type the ending, such as `.png`, choose **Choose App…** and pick the app. Select a row and choose **−** to remove it.

## Every save uploads

Save the file in your editor as usual. Sluice sees the save and uploads the file straight back. Each save shows as a row in the **Transfers** tab, which says "Saved to server ✓" when it's done, and the file list refreshes.

- Saves go ahead of every other transfer, so a big upload never holds up a save.
- Saves of one file go one after another, so the server always ends up with your newest version.
- If the connection is down, the save waits and goes once Sluice has reconnected.

## The built-in editor

The built-in editor opens each file in its own window, titled with the file's name and the site's.

- Text is coloured for the language the file's extension names.
- ⌘S saves the file, and the save uploads it.
- ⌘F finds text, and ⌥⌘F finds and replaces. In an editor window, File › Find Files… is the editor's own find too.
- It follows Sluice's Light or Dark appearance.
- It opens UTF-8 text only. For other files it says "Sluice's editor only opens UTF-8 text. Open the file in another app instead."
- If a file mixes line endings, or ends its lines with CR alone, a note says which line ending saving will use.

If you close the window with changes you haven't saved, Sluice asks "Do you want to save the changes you made to …?", with **Save**, **Don't Save** and **Cancel**.

If the file's copy changes while you have unsaved changes, such as after **Keep server version**, a bar says the file changed. **Reload** takes the new copy, and **Keep mine** saves your text over it.

## When the server's copy has changed

Before each upload, Sluice checks the file on the server. If someone has changed it since you opened it, or since your last upload, Sluice stops before overwriting it, and asks.

> **“index.php” changed on the server**
>
> Someone changed it on My shop since you opened it (now 4 KB, modified 16 Nov 10:42). Your latest save hasn't been uploaded. If you keep the server version, your version goes to the Trash.

- **Compare** shows the server's version and yours side by side. It's the default when the two can be compared.
- **Overwrite server** uploads your version over the server's.
- **Keep server version** puts the server's version in place of your copy, and moves your version to the Trash.
- **Cancel** leaves your save on your computer, not uploaded. The save's row then says "Failed · The file changed on the server, so your save wasn't uploaded." Its **Retry** asks again.

### Compare

If you're editing the file in VS Code, Compare opens VS Code's side-by-side view, and Sluice asks its question again once it's shown.

Otherwise, Compare opens Sluice's Compare window, with **Server's version** on the left and **Your version** on the right. Its buttons are **Overwrite server**, **Keep server version** and **Cancel**. If you close the window without choosing, Sluice asks its question again.

Compare is offered when the server still has the file, and either the file is open in VS Code or your version is text.

### When the file has gone from the server

If the file was deleted or renamed on the server after you opened it, Sluice says "… is no longer on the server". **Overwrite server** puts your copy back, and **Cancel**, the default, leaves the server as it is.

## When you're done

How editing ends depends on the editor.

- **Built-in editor**: close its window. Editing ends once the last save has been uploaded, unless the file is open in another app too.
- **VS Code**: close the file's tab, or quit VS Code. Sluice sees VS Code close the file, and editing ends once the last save has been uploaded. For 24 hours afterwards, or until Sluice quits, Sluice keeps the copy and still watches it. If VS Code opens the file again and you save it, editing picks up where it left off.
- **Any other app**: Sluice can't tell when another app closes a file. Choose **Stop** in the Editing tab when you're done.

You can choose **Stop** in the Editing tab for any file. When nothing is left to upload, Sluice removes its copy.

### The Editing tab

The Editing tab of the bottom panel lists every file you're editing, with its site, its editor and its status:

| Status | What it means |
| --- | --- |
| Opening… | The file is downloading. |
| Editing | The file is open, and the server has your latest save. |
| Uploading… | A save is on its way. |
| Not uploaded | Your copy has changes the server doesn't. |
| Not uploaded · tries again when you next use this site | The save couldn't reach the server. It goes once you next use the site. |
| Stopping after upload… | You chose Stop, and the last save is still on its way. |

### Closing a tab

Closing a server's tab doesn't stop editing: your saves keep uploading. If you close the last tab on a site while some of its files are open for editing, Sluice asks whether to keep uploading their saves. **Keep uploading** is the default. **Stop editing** stops editing them first.

## Edits that haven't reached the server

Sometimes a save can't be uploaded: the server is out of reach, or you chose Cancel when the server's copy had changed.

- If you choose **Stop** on a file whose changes haven't reached the server, it stays in the Editing tab with **Upload** and **Discard**. **Discard** asks first, then moves your version to the Trash.
- If you quit Sluice while files are open for editing, Sluice warns that saves made after it quits won't reach the server, and says how many files have changes that haven't been uploaded. **Cancel** is the default.
- The next time Sluice opens, the Sites tab shows a banner, such as "1 edit hasn't reached the server: index.php (My shop)." **Upload** sends them. If a file's site has been deleted, **Show in Finder** shows its copy so you can keep it. **Not now** hides the banner until you next open Sluice.
