# PBJ Browser — releases

Public distribution point for **PBJ Browser** installers and the update manifests
the browser reads to know when a newer version exists.

This repository holds **no source code**. It contains only:

- `*/‹platform›.json` — small manifests the browser polls (version + download URL)
- GitHub **Releases** — the actual installer files, attached as release assets

## Channels

| Channel     | Manifest                       | Build                                   |
|-------------|--------------------------------|-----------------------------------------|
| `no-login`  | `no-login/win-x64.json`        | Tester build; skips the login screen    |

Each installed browser is built for exactly one channel and reads only that
channel's manifest. The channel is compiled into the binary and never changes for
that install.

## How an update ships

1. Bump the version in the source repo and build the installer.
2. Create a GitHub Release here and attach the installer.
3. Update the channel's `‹platform›.json` to point at the new version.

Every running browser notices within a few hours (or immediately via
**Settings → About → Check for updates**).
