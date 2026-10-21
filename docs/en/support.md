# Support and recovery

## Report a problem

[Open a bug report](https://github.com/AlmostSensible/PoliSSH-docs/issues/new/choose). Include the app version/build from About PoliSSH, macOS version, Apple Silicon model, selected language/theme, steps, expected result and the exact relevant error. For transfers, give direction, approximate size, file/folder shape and conflict/cancel/retry choices. First check [troubleshooting](troubleshooting.md).

Reports and attachments are public. Redact credentials, tokens, private addresses, terminal contents and personal information. Use synthetic data when possible. Do not upload the app database or private keys.

## Installation and updates

Download from the [official release page](https://github.com/AlmostSensible/PoliSSH-docs/releases), extract the ZIP and copy PoliSSH.app to Applications. Quit an older copy before replacing it. Open the copy in Applications. You do not need Xcode, Rust or Homebrew. Use PoliSSH → Check for Updates… for later versions. Do not turn off Gatekeeper or re-sign a downloaded release; report an unexpected security error instead.

Before installing an update, finish transfers and shell work, save remote-editor changes and quit other copies. Updates retain the existing application identity and local data locations. If an update check fails, keep using the installed app and retry later or download the official release manually. Do not downgrade a database unless compatibility has been confirmed.

## Backup and recovery

In 0.19.1, export also preserves saved hosts with incomplete connection details. Success or failure appears beside Export, with the saved path and Show in Finder after a successful save. Correct incomplete host details before connecting.

In 0.19.0, an accessibility crash in the export/restore status message is fixed. File export, restore into an empty library, duplicate skipping and persistence after restart were verified.

Since 0.18.0, Settings → Backup can export configuration and preview an add-only restore. It includes hosts, groups, credential profile metadata, snippets and tunnels, but not passwords, private keys, recordings or preferences. Existing IDs are not overwritten. Protect the JSON file: addresses and commands may be sensitive. This export complements the complete backup below.

Quit PoliSSH before copying local data. In Finder → Go → Go to Folder, open `~/Library/Application Support/PoliSSH` and copy the **entire folder** to a protected backup location. Include the application preferences at `~/Library/Preferences/com.polissh.app.plist` if present and separately back up any recordings and exported files wherever you saved them. Prefer an encrypted Time Machine or whole-Mac backup.

The database copy does **not** contain Keychain passwords, private keys or protected administrator credentials. Preserve your original key files securely and verify your Mac/Keychain backup separately. Protected device-local credentials may need to be entered again on a different Mac. iCloud synchronization is experimental and is not a backup.

For local recovery, quit all app copies, retain a copy of the current folder first and restore the saved folder to the same location using the same app version or a confirmed compatible newer version. Launch the official signed app and verify hosts and credentials before connecting. Do not delete a working database or reset Keychain to troubleshoot an empty library.

## Known beta limits

See [availability](../status.md). Minimum macOS 14 and cross-device iCloud still need external validation. Interrupted writes can leave partial remote files; save a local copy of important edits before retrying. Optional AI tools require separate setup and their own provider terms.


Publisher: **AlmostSensible**. For private support or security reports: [hello@almostsensible.com](mailto:hello@almostsensible.com).
