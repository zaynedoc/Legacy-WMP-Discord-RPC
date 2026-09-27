# Legacy WMP Discord RPC

An independent derivative of [Windows Media Player Discord RPC](https://github.com/T0biasCZe/Windows-Media-Player-Discord-RPC) by T0biasCZe.

This project reads the currently playing track from **Windows Media Player Legacy** and displays it as a Discord Rich Presence. It is maintained as a personal standalone version and keeps the original project's MPL-2.0 license.

## What it does

- Displays the current track, artist, album, and elapsed time in Discord.
- Offers a **Google This Song** Rich Presence button.
- Uses Discord Rich Presence art assets for per-album cover art.
- Can optionally publish WMP media information to Windows' system media controls.
- Runs from the notification area after it starts.

`WebStream` has intentionally been removed. This repository contains no standalone streaming or LAN web-server component.

## Requirements

- Windows Media Player Legacy.
- The Discord desktop application, running and signed in.
- .NET Framework 4.8 or later.

## Run it

1. Start Windows Media Player Legacy and play a tagged music file.
2. Run `Discord WMP.exe` from `Discord WMP/bin/Release`, or use the desktop shortcut created after a Release build.
3. In the RPC app's top text box, enter the **Application ID** for your own Discord Developer Portal application.
4. Exit the app from its notification-area menu and open it again after changing the Application ID.

## Per-album Discord cover art

1. Create a Discord application in the [Discord Developer Portal](https://discord.com/developers/applications) and copy its **Application ID**.
2. Enter that ID in the RPC app, then restart the app.
3. In **Rich Presence -> Art Assets**, upload square cover images. Use simple unique keys such as `official_number`.
4. Also upload fallback assets named `wmp_icon` and `wmp_empty`.
5. In the RPC app, click the small `;;;` button to open the Album Art Manager.
6. Under **Finding art based on specific album name**, enter the WMP Album tag, the Discord asset key, and priority `0`; then select **Add pair**.
7. Close the Album Art Manager to save the mapping.

Mappings are stored in `albumsarts.csv` next to the running executable. The album name comes from the music file's metadata, not its folder name.

## Build

Build the `Discord WMP.sln` solution in the `Release | Any CPU` configuration. A successful build refreshes the desktop shortcut named **Legacy WMP Discord RPC (Fork)**.

## Attribution and license

Original project: [T0biasCZe/Windows-Media-Player-Discord-RPC](https://github.com/T0biasCZe/Windows-Media-Player-Discord-RPC)

This derivative is distributed under the included [Mozilla Public License 2.0](LICENSE.txt).
