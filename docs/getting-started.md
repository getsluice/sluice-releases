# Getting started

[User guide](README.md) › Getting started

## Install Sluice

1. Download [Sluice.dmg](https://github.com/getsluice/sluice-releases/releases/latest/download/Sluice.dmg). One installer works on Macs with Apple Silicon and with Intel.
2. Open `Sluice.dmg` and drag Sluice to the Applications folder.

## Open it the first time

Sluice isn't notarised by Apple yet, so the first time you open a new version, macOS asks you to confirm it.

1. Open Sluice from the Applications folder.
2. If macOS says it can't check the app, open System Settings and go to Privacy & Security.
3. Choose **Open Anyway** next to Sluice.
4. Confirm with your password or Touch ID if macOS asks.

You do this once for each new version of Sluice.

## Allow the keychain

Sluice encrypts saved passwords and key passphrases with your computer's keychain. If macOS asks whether Sluice may use your keychain, choose **Always Allow**.

## The Sites tab

Sluice opens on the **Sites** tab. On the left is the list of your saved sites, in folders if you like. On the right are the selected site's settings.

Until you have a saved site, the right side says "Add a server to get started", with a **New site** button.

You can come back to the Sites tab at any time:

- choose **＋** at the end of the tab strip;
- choose **Sites…** on the toolbar;
- or press ⌘T (File › New Tab).

## Make your first site

1. Choose **New site**.
2. Leave **Protocol** on **SFTP**, unless your server needs SCP, FTP or WebDAV. [Sites](sites.md) explains each choice.
3. In **Host**, type the server's address, such as `example.com`. **Port** is already 22, the usual port for SFTP.
4. In **Username**, type the name you log in with.
5. Leave **Log in with** on **Password**, and type your password. Leave **Save password** ticked to have Sluice remember it.
6. If you like, give the site a **Name**. If you leave it empty, the site is called `user@host`.
7. Choose **Connect**, or press Return.

Connect saves the site, then connects. The form says "Connecting…" while it waits for the server.

## Trust the server

The first time you connect to an SFTP or SCP server, Sluice asks **Trust this server?** and shows the server's key fingerprint. Check that it matches the one your server shows, then choose **Trust and connect**. [Security and privacy](security-and-privacy.md) explains how to check it.

FTPS and HTTPS servers whose certificate can't be verified, and FTP and WebDAV sites with no encryption, ask a question of their own the first time. Both are explained in [Security and privacy](security-and-privacy.md).

## Find your way around

Once the server answers, the Sites tab turns into the server's tab. It shows the site's **Folder to open after connecting**, or your home folder on the server if the site doesn't name one.

- Double-click a folder to open it.
- Double-click a file to edit it. Every save uploads it straight back.
- Drag files in from Finder to upload them.

[Browsing](browsing.md) and [Editing files](editing.md) go into more detail.

## When a new version comes out

Sluice checks for a new version when it starts and once a day after that. When there is one, the Sites tab shows a banner such as "Sluice 1.4.0 is available." **Download** opens the release page in your browser, and **Not now** hides the banner until you next open Sluice. **About Sluice**, in the Sluice menu, shows your version and says when a newer one is available.

To update, download the new `Sluice.dmg` and drag Sluice to the Applications folder, replacing the old one. Your sites, settings and saved passwords are kept, because Sluice stores them outside the app. Then confirm the new version with **Open Anyway**, as above, and choose **Always Allow** if macOS asks about the keychain again.

To stop the check, turn off **Tell me when a new version is available** in Settings › General.
