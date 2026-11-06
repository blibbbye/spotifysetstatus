# Spotify Status

A Windows Discord Rich Presence connector and a small GitHub Pages dashboard.

**Website:** https://blibbbye.github.io/spotifysetstatus/

## What it does

Enter a song title, artist(s), optional album, and a public artwork URL. The connector publishes a Discord Listening activity with:

- Activity line: **Listening to Spotify**
- Details: song title
- State: artist(s)
- Large image: the supplied public cover URL

This is a custom Discord Rich Presence activity. It is not the official Spotify account connection and it does not play audio or read a Spotify account.

## Setup

1. Download [Spotify Status Connector.exe](https://github.com/blibbbye/spotifysetstatus/raw/refs/heads/main/Spotify%20Status%20Connector.exe) and run it on Windows.
2. Open Discord Desktop and keep it running.
3. Create an application in the [Discord Developer Portal](https://discord.com/developers/applications).
4. Copy the application's **Application ID** from General Information.
5. In Spotify Status Connector, click **Settings**, paste the Application ID, and choose **Save & reconnect**.
6. Open the website, allow the browser's local-network permission if it asks, enter track details, then press **Set status**.

The connector stores the Application ID in a small INI file beside the executable. Keep the connector open while setting or showing your status.

## Artwork

Use a direct, publicly accessible HTTPS image URL, no longer than 300 characters. A normal album-image webpage is not the same as a direct image URL. The bundled green music icon is used when you leave the artwork field empty.

To make the small application icon in Discord match the site, you can upload the bundled site/spotify-status-fallback.png as the icon for your own Discord application in the Developer Portal. The large image in the activity remains the track cover.

## Troubleshooting

- **Connector not found:** Run the EXE and refresh the website. The local bridge uses 127.0.0.1:4229.
- **Discord setup needed:** Open Settings in the connector and check that the Application ID is numeric and copied from the right application.
- **Waiting for Discord:** Use Discord Desktop, not just the browser version, then press Reconnect.
- **Cover not shown:** Use a direct public HTTPS image address. Private links and local file paths cannot be loaded by Discord's image proxy.

## Build

The Build Spotify Status Connector workflow compiles the native Windows connector and publishes the EXE at the repository root. The Deploy Spotify Status website workflow publishes site/ to GitHub Pages.
