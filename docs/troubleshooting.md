# Troubleshooting

[User guide](README.md) › Troubleshooting

## macOS says it can't check Sluice

Sluice isn't notarised by Apple yet, so the first time you open a new version, macOS asks you to confirm it.

1. Try to open Sluice from the Applications folder once, so macOS knows about it.
2. Open System Settings and go to Privacy & Security.
3. Choose **Open Anyway** next to Sluice.
4. Confirm with your password or Touch ID if macOS asks.

You do this once for each new version.

## "This server only offers encryption that's too old for Sluice to use."

Some older servers and devices offer only older encryption.

- If Sluice says "This server only offers older encryption. To connect, turn on Allow older encryption in this site's settings.", do that: tick **Allow older encryption** in the site's form, then connect again.
- If it says the encryption is too old for Sluice, even with **Allow older encryption** on, the server offers only methods so old that Sluice can't use them at all. Update the server's SSH or TLS settings, or the device's firmware, to offer something newer.

## "SCP (no SFTP here)" in the status bar

This isn't a problem. The site is an SFTP site, but its server has no SFTP, so Sluice carried on over SCP on the same connection. Everything works as it does over SFTP, except that a transfer cut off partway starts that file again from the beginning.

If you know a server has no SFTP, you can choose **SCP** in its site's **Protocol** menu.

Related messages:

- "This server doesn't offer SCP. Choose SFTP for this site instead." means an SCP site's server has no SCP. Choose **SFTP**.
- "This server has neither SFTP nor SCP, so Sluice can't open it." means the server lets you log in over SSH but offers no way to work with files. If it offers FTP, try an FTP site.

## "This server lets Sluice copy files but not list folders, so Sluice can't open it."

Some accounts may copy files but can't run commands on the server. Over SCP, Sluice needs to run commands to list folders, so it can't browse with an account like that. Ask the server's administrator to turn on SFTP for the account, or to let it run a shell.

## "The server has too many connections open. Try again later."

Many FTP servers limit how many connections one account can have at once. Sluice shares up to four connections for each FTP site: one for browsing, one kept for saves, and two for transfers. When a server allows fewer, Sluice uses fewer, and a save still goes first.

If you see this message, the server already has as many connections as it allows, and refused Sluice's. Other connections may be using up its limit, such as another FTP app, or another computer using the same account. Close them, wait a moment, and try again.

## FTP connections that won't encrypt

"This server doesn't offer encrypted FTP this way." means the server didn't accept the **Encryption** you chose. The message suggests the other TLS choice. Try it first. Choose **None (not encrypted)** only if the server offers nothing else and you trust the network, because your password and files can then be read on the way.

## Logging in

| Message | What to do |
| --- | --- |
| The server didn't accept the username, password or key. | Check the username, and the password or key. Sluice gives you three tries at a password. |
| This file isn't a private key Sluice can read. Use an OpenSSH, PEM or PuTTY .ppk private key. | Choose the private key, not the `.pub` file. |
| Sluice couldn't read the key file … | Check that the file is there and that your account can read it. |
| No SSH agent is running. Start one, or choose a key file instead. | Start your SSH agent, or enter its socket in **Agent socket**. |
| The SSH agent has no keys loaded. Add one, or choose a key file instead. | Add a key to the agent, for example with `ssh-add`. |
| Connection cancelled because the server's identity wasn't trusted. | You cancelled the server's key question. Connect again and check the fingerprint. See [Security and privacy](security-and-privacy.md). |
| Can't store passwords securely on this Mac. | Sluice couldn't use your keychain. Choose **Always Allow** if macOS asks about it. Until then, untick **Save password** and type the password when you connect. |

## Reaching the server

| Message | What to do |
| --- | --- |
| Can't reach (host):(port). Check the address and your network. | Check **Host** and **Port**, and that you're online. Some servers can only be reached from certain networks or over a VPN. |
| The connection to … was lost. | Sluice reconnects by itself. See [Transfers](transfers.md#when-the-connection-drops). |
| The connection to … dropped before the server answered. | The connection dropped mid-step. Sluice lists the folder again; check whether the change was made. |

## Files and folders

| Message | What it means |
| --- | --- |
| You don't have permission to do that here. | The server didn't allow it for your account. |
| You don't have permission to open this folder. | Your account can't list this folder. |
| That file or folder no longer exists. | It was moved or deleted, perhaps by someone else. Choose Refresh. |
| An item with that name already exists. | Choose another name. |
| There isn't enough space on this Mac's disk. | Free some space on your computer, then retry. |
| The server sent this name in a form Sluice can't send back, so Sluice can't open, rename or change it. | The name's characters can't be sent back to the server as they came. |
| This server doesn't allow changing permissions. | Properties can't change permissions here. Over FTP, the server needs `SITE CHMOD`. |

## Editing

| Message | What it means |
| --- | --- |
| Sluice's editor only opens UTF-8 text. Open the file in another app instead. | Use **Open with…** in the right-click menu. |
| No app on this Mac opens this kind of file. Use Open with… to choose one. | Use **Open with…**, or add the file type in Settings › Editing. |
| The file changed on the server, so your save wasn't uploaded. | You chose Cancel when the server's copy had changed. See [Editing files](editing.md#when-the-servers-copy-has-changed). |
| Another file open for editing would share this file's copy on this Mac … Stop editing it first. | Two files whose names differ only in capitals or accents can't be edited at once. Stop editing the other one. |
| Sluice couldn't move your version to the Trash, so it kept it and changed nothing. | Keep server version or Discard couldn't use the Trash. Nothing was changed. |

## Sluice's own files

- "Your saved sites file was damaged, so Sluice started a new one. The old file was kept at …" shows on the Sites tab. The message says where the old file is.
- "Your list of files open for editing was damaged" means Sluice kept the edits it could still read, and moved the old list aside.
- "Sluice couldn't start" with "Sluice couldn't read the file … Fix or move it, then open Sluice again." names the file it couldn't read. Fix that file, or move it somewhere else, then open Sluice again.

## Report a problem

[Open an issue](https://github.com/getsluice/sluice-releases/issues) on GitHub. Please include:

- your version of Sluice, from Sluice › About Sluice;
- your version of macOS;
- the site's protocol, and for FTP its encryption;
- the kind of server, if you know it, such as OpenSSH, vsftpd or a particular NAS;
- Sluice's message, word for word;
- what you did just before it happened.

Never include passwords, passphrases or private keys.

If you'd rather not post in public, email [meeeet.dev@gmail.com](mailto:meeeet.dev@gmail.com).
