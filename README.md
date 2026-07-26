# Omni — release binaries

This repository holds **no source code**. It only hosts the artifacts published by Omni's CI:
the `Omni-<version>-setup.exe` installer, its `.blockmap`, and `latest.yml` — the manifest
`electron-updater` reads.

## Why it is separate, and public

The installed app has to read its own releases to update itself. Reading them from a private
repository would require an access token on every user's machine — and GitHub offers **no**
Releases-only permission: releases live under `Contents`, the same permission that grants read
access to the source code.

Such a token, if stolen, would have exposed the source; and it would have had to be handed to
every user by out-of-band means. Keeping the binaries here solves both problems at once: this
repository can be public without revealing any code, the app reads it anonymously, and there is
no secret left to store or distribute.

Omni's source code remains in a private repository.

## What writes here

Only the release workflow of the main repository, through a GitHub Actions secret
(`RELEASES_TOKEN`) that never leaves GitHub.
