# Troubleshooting

Start with the visible error and the operation that produced it. Note the app/build version, macOS version, authentication method and whether the connection is SSH + SFTP or SFTP-only. Controls labeled **Unreleased** in the guide may be absent from your build.

## Cannot connect

Check the host address, port, username and network/VPN access. A timeout and an authentication rejection are different problems. Confirm that the SSH service is available before changing saved credentials.

For ssh-agent, check loaded identities on your Mac:

```sh
ssh-add -l
```

An encrypted key may require its passphrase. Keyboard-interactive servers can require several answers or a 2FA code. Initial authentication failures are not automatically retried by reconnect.

## The server fingerprint changed

Compare the presented fingerprint with the server administrator's trusted value. A reinstall or key rotation can explain a change, but the app cannot establish that explanation for you. Forgetting the old fingerprint in **Known hosts** causes a fresh decision on the next connection; it does not verify the new identity.

## SFTP works but the terminal does not

Some servers provide an SFTP subsystem without an interactive shell. Use **Files**. This does not imply that the file connection failed.

## Access denied in the file pane or editor

Check the permissions of the original SSH account. Switching the terminal to root does not elevate its separate SFTP connection. The editor supports UTF-8 files up to 2 MB; binary, invalid-UTF-8 or oversized files are not ordinary editor inputs.

## Remote edits cannot be saved

For a remote-content conflict, first export a local copy of your edits. Reload the current remote text and compare before saving again. For an upload failure, keep the edited/original copies provided by the editor; do not close and discard them before recovery.

The editor's conflict check does not lock out other applications editing the remote file.

## A transfer failed or was cancelled

Inspect the reported source, destination and error. Partial destination files can remain. Retry is explicit and does not automatically continue from the last byte. On a name conflict, distinguish **Merge** from **Replace**: replacing a destination folder can replace all of it.

If recovery after failed replacement reports a recovery path, inspect that path before making another replacement attempt. Queue pause affects pending work; already-running transfers finish normally.

## Reconnect did not restore my process

Reconnect opens a new shell and keeps terminal display history. It does not restore remote processes, tunnels, transfers or logging. Configure a server-side persistent session such as tmux separately if needed. Closing/exiting a session intentionally stops automatic reconnect.

## Option does not type accented characters

Disable **Settings → Terminal → Use Option as Meta**. When enabled, Option is used for terminal Meta input rather than normal macOS character composition.

## Pattern highlighting is unexpected — Unreleased

Check the rule's enable switch, **Regex** and **Aa**. Literal `success` also matches text inside a filename; regex `\bsuccess\b` restricts it to whole words. Regular expressions match displayed rows, not text spanning wrapped rows. Empty matches and bidirectional rows are excluded.

Correct the validation error for an invalid expression. If a slow rule was paused, simplify it and edit the rules to retry. Highlighting affects display only; copied output remains unchanged.

## Command history is empty — Unreleased

Activate **… → Enable shell integration…** at an idle zsh or Bash 4.4+ prompt. macOS's older system Bash may not meet that requirement. Re-enable after reconnecting. Nested shells and tmux/screen are not automatically initialized.

A missing end marker is not a successful exit. The command stays without a fabricated code; disconnection marks unfinished work as interrupted. Closed sessions do not retain this in-memory history.

## No completion notification — Unreleased

Enable the option under **Settings → Terminal** and allow notifications in macOS System Settings. The command must run for at least 10 seconds with shell integration active, and the session must be in the background. macOS Focus modes may defer delivery. Notification content intentionally omits the command text.

## AI is unavailable

For Apple, check macOS 26+, eligible Apple Intelligence, the downloaded model and the app's reported language support. For Codex, check the configured executable and its existing CLI login. The app does not silently change providers. A compatible CLI must support the read-only/ephemeral options used by this integration; check the compatibility information included with your app build.

Review only the selection you intend to submit. A successful explanation or generated command is a suggestion, not proof that a server operation has succeeded.

## iCloud does not start

iCloud requires an app build with the appropriate signing and capabilities. See [iCloud availability](../status.md#icloud). Configuration synchronization and Keychain synchronization are distinct; configuration status alone does not prove secret synchronization.

## Reporting a reproducible issue

Use the repository's issue tracker if you have access. Include the app/build version, macOS version, steps, expected behavior, actual behavior and the exact relevant error. For transfers, include direction, file/folder shape, conflict choice and whether cancellation or retry was involved. For UI defects, include the selected language, theme and window size.

Use fictional hosts in screenshots. Remove passwords, private keys, tokens and private server details from logs before sharing them. State what you have verified separately from what you suspect.
