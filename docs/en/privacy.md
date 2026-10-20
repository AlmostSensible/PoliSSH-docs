# Privacy

Last updated: 20 October 2026. Applies to the PoliSSH public beta. Optional services are described separately below.

Publisher and privacy contact: **AlmostSensible**, [hello@almostsensible.com](mailto:hello@almostsensible.com).

## Data on your Mac

Host addresses, usernames, groups, tags, snippets, tunnels and authentication-profile metadata are kept in a local SQLite database. Passwords, private keys and key passphrases are stored in macOS Keychain. Application preferences are stored locally. Server fingerprints are retained to check subsequent connections.

Terminal scrollback and command history are held in the session. If you enable session recording, output is written to the selected local log location; logs and exported files can contain sensitive information. Administrator passwords saved for sudo/su use device-local protected Keychain items and are excluded from iCloud sync.

## Connections and permissions

SSH/SFTP connect to the servers you choose. Those servers and your network operators can observe connection metadata; servers process commands and files you send. A local terminal runs with your Mac account's permissions. The app is distributed outside the App Store without App Sandbox. macOS may ask for file, notification or authentication access. Declining permissions can limit the corresponding function.

## Optional iCloud — experimental

If you enable synchronization in a provisioned build, configuration is sent to your private Apple CloudKit database and eligible credentials use iCloud Keychain. Apple operates these services under its own [privacy policy](https://www.apple.com/legal/privacy/). Cross-device operation has not yet been verified. Sync is optional; turning it off retains local data and does not automatically erase cloud data. Do not treat sync as a backup.

## Optional AI

Apple on-device models and supported local Ollama/LM Studio configurations run on your Mac; installing or authenticating external tools is a separate step. With external CLI providers, the text you submit may be sent to the selected provider using your existing account. Their privacy terms, retention, subscription and usage limits apply. PoliSSH does not automatically attach Keychain secrets or the whole terminal history to inline command requests. Text or context that you submit yourself can still contain sensitive data. Review prompts and generated commands before use.

## Updates and the website

Sparkle checks the public update feed on GitHub Pages and downloads signed updates from GitHub Releases. Automatic checks are enabled by default and can be disabled in Settings → General → Updates. Automatic installation and Sparkle system-profile submission are disabled. An update check necessarily exposes ordinary request metadata, such as your IP address, to the hosting service. The website and download hosting are operated by GitHub under its [privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

## Support, backups and deletion

GitHub issues are public. Remove passwords, private keys, tokens, private hostnames and personal data before posting logs or screenshots. [Support and recovery](support.md) explains local data locations and backup limitations. Uninstalling the app does not erase its local database, Keychain entries, recordings or cloud data. Remove these separately only after retaining any needed backup. For privacy questions or requests, contact [hello@almostsensible.com](mailto:hello@almostsensible.com). Do not send passwords or private keys.
