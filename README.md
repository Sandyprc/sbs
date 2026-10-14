<p align="center">
  <img src="assets/icon.png" width="128" height="128" alt="Service Bus Studio icon">
</p>

<h1 align="center">Service Bus Studio</h1>

<p align="center">A calm, native Mac app for Azure Service Bus.<br>Browse queues, topics and subscriptions, inspect messages safely, and fix dead letters without leaving your Mac.</p>

<p align="center">
  <img src="assets/overview.png" alt="Service Bus Studio showing a namespace overview on a MacBook">
</p>

## What it does

- **Browse everything:** queues, topics and subscriptions with active, dead-letter and scheduled counts.
- **Peek safely:** peeking never locks or removes a message. Inspect the JSON body, broker metadata and application properties.
- **Receive on purpose:** peek-lock with a live lock countdown, then complete, abandon, defer or dead-letter. Receive-and-delete is a separate, clearly marked mode.
- **Repair dead letters:** see why a message failed, edit it and resend it as a new message.
- **Manage entities:** create, edit and delete queues, topics and subscriptions. Deleting asks you to type the exact name.
- **Sessions, scheduled and deferred messages**, a command palette (⌘K), and warm light and dark themes.

<p align="center">
  <img src="assets/inspector.png" alt="The message inspector showing a message body">
</p>

## Install

### With Homebrew (recommended)

```sh
brew install --cask sandyprc/tap/service-bus-studio
```

This adds the tap and installs **Service Bus Studio** into your Applications folder.

### Or download it

1. Open the [latest release](https://github.com/Sandyprc/sbs/releases/latest).
2. Download `ServiceBusStudio-<version>.dmg`.
3. Open the DMG and drag **Service Bus Studio** into **Applications**.

### First launch

Service Bus Studio is not notarized by Apple yet, so macOS asks you to confirm the first time you open it:

1. Open **Service Bus Studio** from Applications. macOS says it cannot verify the app. Click **Done**.
2. Open **System Settings › Privacy & Security**, scroll to **Security**, and click **Open Anyway** next to Service Bus Studio.
3. Confirm with Touch ID or your password. From now on the app opens normally.

Prefer the terminal? This removes the download flag so the app opens straight away:

```sh
xattr -dr com.apple.quarantine "/Applications/Service Bus Studio.app"
```

## Update

```sh
brew upgrade --cask service-bus-studio
```

If you installed from the DMG, download the new release and replace the app in Applications.

## Uninstall

```sh
brew uninstall --cask service-bus-studio
```

To also remove its settings and saved connection list: `brew uninstall --zap --cask service-bus-studio`. Saved connection strings live in your login Keychain under **com.sandyprc.servicebusstudio.connection**; delete them in Keychain Access if you no longer need them.

## Getting started

- **Try it offline:** choose **Explore sample namespace** on the welcome screen. Everything works on demo data and nothing is sent anywhere.
- **Connect with a connection string:** choose **Add a connection**, pick **SAS connection string** and paste it. It is stored only in your Keychain.
- **Local emulator:** the [Azure Service Bus emulator](https://learn.microsoft.com/azure/service-bus-messaging/overview-emulator) works too; add its connection string (with `UseDevelopmentEmulator=true`) as a connection.
- **Microsoft Entra ID:** sign-in uses your own app registration (a public client with redirect URI `servicebusstudio://auth`). Entra ID is also what unlocks Azure Monitor metrics history. This option is new and still being verified.

## Requirements

- macOS 15 Sequoia or later
- A Mac with Apple silicon

## Privacy

- No telemetry and no accounts.
- Connection strings and sign-in tokens are kept in the macOS Keychain, never in files.
- Message bodies are only saved when you export one.

## Feedback

Found a bug or want a feature? [Open an issue](https://github.com/Sandyprc/sbs/issues).

This repository hosts the downloads. The Homebrew cask lives in [Sandyprc/homebrew-tap](https://github.com/Sandyprc/homebrew-tap). The app's source code is not public.

<p align="center">
  <img src="assets/dark.png" alt="Service Bus Studio in the dark theme">
</p>
