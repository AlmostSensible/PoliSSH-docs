# User guide

For public beta 0.17.0 and later, macOS 14+ on Apple Silicon. See [availability](../status.md).

## Updates outside the App Store

Starting with 0.17.0, the native app includes **PoliSSH → Check for Updates…**. Enable or disable automatic checks in **Settings → General → Updates**. Installation requires confirmation and restarts the app; finish sessions and transfers first.

Versions 0.16.1 and earlier do not include an updater. Install the first version with updates manually: extract the official ZIP and copy `PoliSSH.app` to Applications, replacing the previous app after quitting it. Later releases can be installed through the updater. See [availability](../status.md) for published downloads. The SwiftPM development build has no updater.

## First connection

1. Open PoliSSH and select **New host**.
2. Give the host a recognizable name. Enter its address, SSH port (normally `22`) and username.
3. Choose an authentication profile, or create one under **Authentication**.
4. Save and open the host.
5. For a new server, compare its SSH fingerprint with a trusted value from the server administrator before accepting it.
6. Complete any password, key-passphrase or keyboard-interactive challenge.

When connected, use the connection tab's **Terminal**, **Files** or **Terminal + files** switch. Switching views keeps the connection and the file-pane state.

For a quick connection, press `⌘K` and enter:

```text
ssh user@example.com -p 2222
```

You can also enter `user@example.com` or search for a saved host or open session. A saved host uses its configured profile. **Connect without saving** uses ssh-agent; it does not create a saved host.

## Hosts and authentication

Use groups, tags, favorites and search to organize hosts. Switch the library between list and tiles. Opening a host that already has a session selects that session.

Under **Authentication**, create a profile to reuse across hosts:

| Method | What you need |
| --- | --- |
| Password | The SSH account's password. |
| OpenSSH key | A private key and, if encrypted, its passphrase. PoliSSH can generate an Ed25519 key and export its public key. |
| ssh-agent | A running agent with the appropriate key loaded. |
| Keyboard-interactive | Answers to the server's prompts, including supported 2FA challenges. |

Passwords and private keys are stored in macOS Keychain. Deleting a profile identifies dependent hosts and asks for confirmation. Those hosts remain in the library, but need another authentication method before their next connection. Existing sessions stay open.

**Known hosts** lists saved server fingerprints. Forgetting a fingerprint asks for confirmation and causes another trust decision on the next connection. A changed fingerprint is not automatically accepted.

### Import an OpenSSH configuration

In the host library's **…** menu, choose **Import SSH config…**. Select a UTF-8 configuration file or paste its contents, review the preview and warnings, then choose **Import selected**. Existing hosts are retained and duplicates are skipped.

The importer reads explicit `Host` entries with `HostName`, `User` and `Port`. Patterns, inherited settings, keys and other directives are not applied. Imported hosts use ssh-agent; check each connection and assign an authentication profile before connecting if needed.

## Terminal workspace

Open multiple connection tabs, or press `⌘T` for a local shell. The split control creates panes side by side or above and below. Click a pane to make it the target for terminal actions and snippets.

Press `⌘F` to search output. Terminal appearance, cursor, scrollback and mouse behavior are configured under **Settings → Terminal**. Disable **Use Option as Meta** if you need Option-based characters, such as Polish letters.

Use **… → Record session** to select a log destination. Recording captures terminal output and can be stopped from the same menu. Log files can contain application output and command text.

### Reconnecting

Automatic SSH reconnect is enabled by default. After transport loss, the session shows a countdown and allows cancellation. It makes up to five attempts with delays of 2, 4, 8, 16 and 30 seconds. **Reconnect** starts an immediate attempt.

Reconnect opens a new shell in the same tab, retaining displayed history. It does not replay startup commands or automatically resume transfers, tunnels or logging. Initial authentication and server-identity failures are not automatically retried. A remote process survives transport loss only if the server-side environment keeps it running, for example through a separately configured tmux session.

## New terminal tools

These controls may be absent from older builds. They apply to local and SSH terminals unless stated otherwise.

### Highlight patterns

Open **Settings → Terminal → Pattern highlighting**. Each rule has an enable switch, pattern, color and two options:

- **Regex** interprets the pattern as a regular expression; otherwise it matches literal text.
- **Aa** enables case-sensitive matching.

Examples:

| Pattern | Regex | Result |
| --- | --- | --- |
| `ERROR` | Off | Matches the text inside longer words too. |
| `\bERROR\b` | On | Matches `ERROR` as a whole word. |
| `\b(ERROR|WARNING)\b` | On | Matches either severity. |
| `\b(?:\d{1,3}\.){3}\d{1,3}\b` | On | Highlights IPv4-shaped text; does not validate IP address ranges. |
| `\bsuccess\b` | On | Matches `success`, while excluding the substring in `.sudo_as_admin_successful`. |

New default rules match whole words. Previously saved literal rules remain literal. There are at most 12 rules, each up to 128 characters. Matching uses individual displayed rows; patterns cannot join text across wrapped rows. Empty matches are ignored. Invalid regexes show a diagnostic. A regex exceeding the matching time limit is paused with a warning until you edit the rules.

Highlights do not modify output, copied text or ANSI attributes. Bidirectional rows are excluded from the overlay.

### Paste review

**Review multiline paste** is enabled by default. Pasting line breaks or control characters opens a preview through the keyboard, context menu or configured right-click paste action.

**Cancel** sends nothing. **Paste** sends the reviewed clipboard snapshot. Depending on the shell's bracketed-paste support, line breaks can execute commands. Disconnecting invalidates a pending review.

### File references

Hold `⌘` and click a detected reference such as:

```text
/var/log/nginx/error.log
config.php:42
config.php:42:7
```

Remote UTF-8 files open in the SFTP editor; line references place the cursor at that line and optional column. Absolute paths work directly. Relative paths require a reported current directory, supplied by shell integration or OSC 7. PoliSSH does not infer it from the prompt. Links keep a subtle underline and a pointing-hand cursor. Local files open in their default macOS application.

### Shell integration and command history

At an **idle zsh or Bash 4.4+ prompt**, choose **… → Enable shell integration…** and review the explanation. Do not activate it inside an editor or another running program.

Integration adds temporary hooks to the current shell, without modifying startup files. **… → Command blocks** opens a panel with the last 100 commands, their working directories, durations and exit codes. Select an entry to copy the command or find it in terminal output. Output itself stays in the terminal; select it there for copying or AI explanation.

Use `⌘⌥↑` / `⌘⌥↓` to navigate between shell prompt marks in scrollback. **Clear** removes completed or interrupted history while retaining a running command. **Disable shell integration** removes added zsh hooks or restores prior Bash prompt settings.

History stays in session memory and is not synced with iCloud. Enable integration again after reconnecting. Nested shells and tmux/screen passthrough are not initialized automatically. If the shell provides no end marker, PoliSSH does not invent an exit code; disconnection marks unfinished commands as interrupted.

### Completion notifications

In **Settings → Terminal**, enable **Notify when a long command finishes** and allow macOS notifications. Commands lasting at least 10 seconds can notify while the session is in the background. The message includes host/session, duration and exit code without command text. Clicking it selects the session if it is still open. macOS Focus settings can defer delivery.

## Files and transfers

Choose **Files** or **Terminal + files**. Local and remote panes show their respective current folders. Use the breadcrumbs and back/forward controls to navigate. The pane's **…** menu provides refresh, sorting, view options, hidden files, new file/folder and **Go to folder…**. Folder favorites are available from the breadcrumb menu.

Choose list, icons or columns. Double-click a folder to open it. Select multiple items using `⌘` or `⇧`. **Return/Enter** renames the selected item; another Enter commits and Escape cancels. **Delete** opens a permanent-delete confirmation.

Upload by dragging from local to remote, or download in the opposite direction. Dropping onto a folder selects that destination. Dragging within one pane moves the items to the chosen folder. You can also use item context menus.

Open **Transfer activity** using the up/down-arrow control in the application bar. It shows transfers across connections with progress, status, cancellation and retry. Queue pause stops pending work; active transfers finish normally. **Settings → SFTP** controls the global concurrency limit. Failed or cancelled transfers may leave partial destination files; temporary failures retry automatically up to twice by default (Settings → SFTP). Completed files are retained; known partial files restart from the beginning. Cancelled transfers require an explicit retry.

### Name conflicts

| Choice | Effect |
| --- | --- |
| Merge | For folder-to-folder conflicts: keeps destination-only contents and asks about conflicting children. |
| Replace | Replaces the existing item. For folders, this can replace the whole destination folder. |
| Keep Both | Creates an available numbered name for the incoming item. |
| Skip | Leaves that destination item unchanged. |
| Stop | Stops the remaining items in this batch; already-started transfers continue. |

**Apply to all** applies to the current batch, with separate decisions for files and folders. Upload/download preserve source files. If recovery after a failed replacement cannot restore the previous destination, the error includes its recovery path.

## Remote file editor

Double-click a remote UTF-8 text file or choose **Edit file**. Files up to 2 MB are supported. The editor has syntax selection, logical line numbers, cursor position, wrapping and automatic indentation, including tabs and CRLF endings.

Edit, then use **Save to server** (`⌘S`). Unsaved changes stay local to the editor until saved. The app checks for remote-content changes before upload and asks before closing unsaved edits. You can export edited or original text as a local copy. Failed uploads retain both versions for recovery. The conflict check does not prevent another application from modifying the remote file concurrently.

**Compact editor:** the header contains **Save**, with reload and local-copy export under **…**; the footer contains syntax, wrapping, encoding and cursor position. The current line is highlighted across its width.

SFTP editing uses the original SSH account's permissions, including after terminal elevation to root.

## Reusable commands

Open **Snippets** in the sidebar. Select a saved command to inspect its full text. Search the library, copy a command, or edit/delete it from the actions menu. Deletion requires confirmation.

For the current connected terminal:

- **Insert** puts the command into the shell for editing without sending Enter.
- **Execute** sends the command and Enter.

**Run on hosts…** lets you select up to ten hosts, review the command and endpoints, then run it in separate new terminals. No target is preselected. Authentication and fingerprint checks still apply. A “Command sent” status reports delivery, not command success. It does not automatically retry or run the hosts' startup commands.

A host can explicitly enable an approved startup snippet. Changing that snippet requires renewed approval; automatic reconnect does not replay it.

## Tunnels and jump hosts

Create a forwarding profile under **Tunnels** and use it through an active SSH connection:

| Type | Typical use |
| --- | --- |
| Local forwarding | Reach a remote service through a port on your Mac. |
| Remote forwarding | Expose a locally reachable service through a server-side listener. |
| Dynamic SOCKS5 | Use the SSH connection as a SOCKS proxy for a configured client. |

Check the bind address, ports and destination before starting the tunnel. **Local** and **remote** describe the listener side; the remote SSH server may restrict forwarding.

For a bastion, configure a single **Jump host** in the destination host's settings. The jump connection has its own authentication and server-identity checks.

## Administrator access

Use **… → Switch to root…**, or explicitly enable automatic elevation in the host settings. Choose sudo or su. A saved administrator password uses a separate, local-only Keychain entry; retrieval requires Touch ID or the Mac login password. It is excluded from iCloud synchronization and export.

Recording stops before administrator-password exchange. Use `exit` to leave the elevated shell. Elevating the terminal does not elevate SFTP. Initial automatic elevation is not repeated by automatic reconnect.

## AI assistant

Choose **AI** to draft a command. To explain output, select it and choose **Explain** from the context menu. Review/edit the selected text before sending. The assistant returns text; it does not execute commands.

**Apple** is the default on-device provider, requiring macOS 26+, supported Apple Intelligence and a downloaded model. Availability is shown in the app; unsupported Polish input may require using English.

**Optional AI tools:** Codex, Claude Code, Gemini, GitHub Copilot, OpenCode, Ollama and LM Studio. Install and authenticate the chosen CLI or configure a local model separately; select its provider, executable and model in **Settings → AI**. Detection does not prove account entitlement. Not every integration has been tested on a real account. External providers may receive submitted text; their terms and limits apply. There is no automatic provider switch. Review commands before use.

**⌘I** opens a command suggestion at the terminal cursor. Review the result and insert it without automatic execution; Escape cancels. This mode does not automatically attach terminal history.

## Settings and data

| Settings tab | What it controls |
| --- | --- |
| General | English/Polish language and dark/light/system appearance. |
| SFTP | Local start folder and global transfer concurrency. New local panes use the configured start folder. |
| AI | Provider, executable path and model. |
| Terminal | Font, palette, cursor, input/mouse behavior, reconnect, scrollback and bell; newer builds add pattern/paste/notification settings. |
| iCloud | Optional configuration synchronization when the app is provisioned for it. |
| Shortcuts | Keyboard shortcut reference. |

Host configuration is stored in SQLite under `~/Library/Application Support/PoliSSH`; secrets use macOS Keychain. Optional iCloud requires separate developer provisioning and is disabled by default in the standard build. See [iCloud availability](../status.md#icloud). Do not infer that secrets were synchronized from configuration-sync status alone.

## Keyboard shortcuts

| Shortcut | Action |
| --- | --- |
| `⌘K` | Quick connect / find a host or session. |
| `⌘T` | New local terminal. |
| `⌘W` | Close the active connection tab. |
| `⌘F` | Search hosts or terminal output, according to the current view. |
| `⌃⌘S` | Show/hide sidebar. |
| `⌘N` | Add a host from the host library. |
| `⇧⌘N` | New window. |
| `⌘,` | Settings. |
| Return / Escape | Commit/cancel inline file rename. |
| `⌘S` | Save in the remote editor. |
| `⌘⌥↑` / `⌘⌥↓` | Previous/next shell prompt mark. |

## Current limits

The signed, notarized app is available as a public beta. Mosh, Telnet and serial connections are not implemented. OpenSSH import supports basic host fields rather than the full configuration language. Transfers do not automatically resume partial files; symbolic links and special files are rejected before writing. UTF-8 editing is limited to 2 MB. A terminal root shell does not change SFTP permissions. Shell integration is session-scoped and does not configure tmux persistence.

If something fails, start with [Troubleshooting](../en/troubleshooting.md). See [availability](../status.md) before relying on unreleased features.
