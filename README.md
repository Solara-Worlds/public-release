# Solara Worlds launcher releases

This repository hosts Windows builds of the Solara Worlds launcher. It does not contain the launcher source, game clients, or any secret.

The files on a release come from the tag workflow in [Solara-Worlds/game-launcher](https://github.com/Solara-Worlds/game-launcher):

| File | Role |
| --- | --- |
| `SolaraWorldsLauncher-Setup-<version>.exe` | NSIS installer. This is the build that can update itself. |
| `SolaraWorldsLauncher-Setup-<version>.exe.blockmap` | Block map used for a differential update. |
| `latest.yml` | Version, file name, and `sha512` that the installed app checks. |
| `SolaraWorldsLauncher-Portable-<version>.exe` | One-file build. It is attached for download. It is not the file `latest.yml` points at. |

The installed app reads `latest.yml` from this public repository with no token. Drafts and prereleases are not "latest". The `sha512` check works without an Authenticode signature. Windows SmartScreen can still warn, because these builds are not code-signed.

Do not commit tokens, source, or player data here. Publishing is done by the game-launcher workflow with a token that can write only to this repository.
