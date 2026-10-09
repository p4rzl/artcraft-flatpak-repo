# ArtCraft Suite — Unofficial Flatpak Repository

**An unofficial, community-maintained Flatpak repository for the ArtCraft suite on Linux.**

Install and update your favorite ArtCraft applications through Flatpak, directly from your terminal or graphical software center, including KDE Discover.

[![GitHub Actions](https://github.com/p4rzl/artcraft-flatpak-repo/actions/workflows/update-repo.yml/badge.svg)](https://github.com/p4rzl/artcraft-flatpak-repo/actions/workflows/update-repo.yml)
![Platform](https://img.shields.io/badge/Platform-Linux-blue?logo=linux)
![Package Format](https://img.shields.io/badge/Package-Flatpak-purple)
![Architecture](https://img.shields.io/badge/Architecture-x86__64-orange)

> [!IMPORTANT]
> **Disclaimer**
>
> This repository is an unofficial, community-maintained project and is **not affiliated with, endorsed by, or officially connected to the ArtCraft development team or Storytold**.
>
> Its sole purpose is to simplify installation and provide automated updates for ArtCraft applications on Linux.
>
> All trademarks, application names, logos, and upstream software rights belong to their respective owners.

---

## Overview

The [ArtCraft suite](https://github.com/storytold) provides creative applications for Linux and other platforms.

Although the upstream developers distribute Flatpak bundles through GitHub Releases, manually downloading and installing new versions can be inconvenient.

**ArtCraft Flatpak Repository solves this problem** by providing a centralized Flatpak remote that can be added to your system once and used for future updates.

### Features

- **Centralized repository** — Install all supported ArtCraft applications from one source.
- **Automated synchronization** — GitHub Actions checks upstream releases daily.
- **Automatic updates** — Receive new versions through your Flatpak package manager.
- **KDE Discover integration** — Manage available applications through KDE's graphical software center.
- **No manual bundle downloads** — Install applications using familiar Flatpak commands.
- **Community-maintained** — Independent of the upstream ArtCraft development team.

## Available Applications

| Application | Flatpak Application ID |
|---|---|
| LightCraft | `ai.storyteller.lightcraft` |
| PhotoCraft | `ai.storyteller.photocraft` |
| VectorCraft | `ai.storyteller.vectorcraft` |
| FilmCraft | `ai.storyteller.filmcraft` |
| PdfCraft | `ai.storyteller.pdfcraft` |
| EffectCraft | `ai.storyteller.effectcraft` |
| DesignCraft | `ai.storyteller.designcraft` |

Application availability depends on successful upstream releases and repository synchronization.

Currently, the repository is configured for **Linux x86_64** systems.

---

## Prerequisites

Before proceeding, make sure:

1. You are running a Linux distribution that supports Flatpak.
2. Flatpak is installed and configured.
3. Your system has access to the required application runtimes.
4. The ArtCraft repository has been successfully published and is reachable.

### Install Flatpak

On Fedora:

```bash
sudo dnf install flatpak
```

On Arch Linux:

```bash
sudo pacman -S flatpak
```

On Ubuntu or Debian:

```bash
sudo apt install flatpak
```

### Add Flathub

**Flathub is required:** ArtCraft distributes applications; their runtimes are supplied by Flathub. Adding ArtCraft alone does not add Flathub automatically.

Add Flathub to your user configuration:

```bash
flatpak remote-add --user --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

Use the same installation scope for both sources: `--user` in this guide. If you install ArtCraft system-wide, configure Flathub with `--system` too. Do not skip this step just because Discover shows Flathub under a different installation.

Flatpak downloads the required runtime when you install an application. You do not need to install the SDK or select a different runtime version manually.

---

## Installation — Terminal

The recommended installation method is to add the ArtCraft repository as a Flatpak remote.

### Step 1 — Add the repository

Run:

```bash
flatpak remote-add --user --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak remote-add --user --if-not-exists artcraft https://artcraft.p4rzl.it/artcraft.flatpakrepo
```

This registers ArtCraft as a Flatpak software source for your current user.

> [!NOTE]
> The repository currently does not use GPG signing. Only add it if you trust this community-maintained source. The repository must be online for installation to succeed.

### Step 2 — Verify the repository

List your configured Flatpak remotes:

```bash
flatpak remotes --user
```

You should see an entry named `artcraft`.

To inspect available applications:

```bash
flatpak remote-ls --user artcraft
```

### Step 3 — Install applications

Install individual applications using their application IDs.

**LightCraft**

```bash
flatpak install --user artcraft ai.storyteller.lightcraft
```

**PhotoCraft**

```bash
flatpak install --user artcraft ai.storyteller.photocraft
```

**VectorCraft**

```bash
flatpak install --user artcraft ai.storyteller.vectorcraft
```

**FilmCraft**

```bash
flatpak install --user artcraft ai.storyteller.filmcraft
```

**PdfCraft**

```bash
flatpak install --user artcraft ai.storyteller.pdfcraft
```

**EffectCraft**

```bash
flatpak install --user artcraft ai.storyteller.effectcraft
```

**DesignCraft**

```bash
flatpak install --user artcraft ai.storyteller.designcraft
```

You can also install all applications together:

```bash
flatpak install --user artcraft \
  ai.storyteller.lightcraft \
  ai.storyteller.photocraft \
  ai.storyteller.vectorcraft \
  ai.storyteller.filmcraft \
  ai.storyteller.pdfcraft \
  ai.storyteller.effectcraft \
  ai.storyteller.designcraft
```

---

## Installation — KDE Discover

KDE Discover is the graphical software center included with the KDE Plasma desktop environment.

It supports installing and updating software from multiple sources, including Flatpak repositories.

ArtCraft can be integrated with Discover so that users can manage its applications without relying on terminal commands.

### Required first step — Enable Flathub

In **Discover → Settings → Flatpak**, check that **Flathub is enabled in the same installation as ArtCraft** (user or system).

If it is missing, choose **Add Source** in that installation and enter:

```text
https://dl.flathub.org/repo/flathub.flatpakrepo
```

Accept the prompts, then add ArtCraft below. A Flathub entry that is disabled, filtered to exclude the runtime, or configured only in a different installation may not provide the required dependency.

### Method 1 — Add ArtCraft directly in Discover

**Step 1 — Open KDE Discover**

Launch **Discover** from the KDE Plasma application launcher.

**Step 2 — Open Settings**

Navigate to the **Settings** section, usually accessible from the sidebar.

Depending on your KDE Plasma version and language, this section may also be called *Preferences* or *Software Sources*.

**Step 3 — Find Flatpak sources**

Locate the section dedicated to Flatpak repositories.

If Flatpak integration is available, Discover will display your configured Flatpak sources.

**Step 4 — Add a new source**

Select **Add Source** or the corresponding option for adding a Flatpak repository.

Paste the following URL:

```text
https://artcraft.p4rzl.it/artcraft.flatpakrepo
```

Confirm the operation.

**Step 5 — Verify the source**

After adding the repository, check that ArtCraft appears in the list of available Flatpak sources.

**Step 6 — Find and install applications**

Search for an ArtCraft application, such as **PhotoCraft**, **VectorCraft**, or **LightCraft**.

If the repository provides the necessary AppStream metadata, the applications should appear in Discover's catalog.

Select the application and click **Install**.

> [!TIP]
> If Discover offers multiple sources for the same application, select the ArtCraft repository as the installation source.

### Method 2 — Open the repository file with Discover

Some desktop environments and KDE installations support opening `.flatpakrepo` files directly through a graphical software manager.

1. Open the repository link:
   
   https://artcraft.p4rzl.it/artcraft.flatpakrepo

2. Save the `.flatpakrepo` file to your computer.
3. Open the downloaded file using KDE Discover.
4. Follow the prompts to add the repository.
5. Return to Discover and search for the available ArtCraft applications.

> [!NOTE]
> If your system does not associate `.flatpakrepo` files with Discover, use Method 1 or the terminal installation instructions instead.

### Method 3 — Install using an application link

After the updated workflow has deployed successfully, these `.flatpakref` files are available. Download one and open it with Discover:

| Application | Installation file |
|---|---|
| LightCraft | [Install LightCraft](https://artcraft.p4rzl.it/ai.storyteller.lightcraft.flatpakref) |
| PhotoCraft | [Install PhotoCraft](https://artcraft.p4rzl.it/ai.storyteller.photocraft.flatpakref) |
| VectorCraft | [Install VectorCraft](https://artcraft.p4rzl.it/ai.storyteller.vectorcraft.flatpakref) |
| FilmCraft | [Install FilmCraft](https://artcraft.p4rzl.it/ai.storyteller.filmcraft.flatpakref) |
| PdfCraft | [Install PdfCraft](https://artcraft.p4rzl.it/ai.storyteller.pdfcraft.flatpakref) |
| EffectCraft | [Install EffectCraft](https://artcraft.p4rzl.it/ai.storyteller.effectcraft.flatpakref) |
| DesignCraft | [Install DesignCraft](https://artcraft.p4rzl.it/ai.storyteller.designcraft.flatpakref) |

These files include `RuntimeRepo`, pointing to Flathub, so a supporting installer can offer to add the runtime source. Accept that prompt. If Discover does not offer it, add Flathub using the required first step above. This field belongs to `.flatpakref`; adding it to `artcraft.flatpakrepo` would not configure dependencies.

Terminal equivalent for PhotoCraft:

```bash
flatpak install --user --from https://artcraft.p4rzl.it/ai.storyteller.photocraft.flatpakref
```

### Troubleshooting KDE Discover integration

If ArtCraft does not appear in Discover after adding the repository:

- Verify that Flatpak support is installed for Discover.
- Check that the repository appears in Discover's software sources.
- Make sure the repository is reachable.
- Verify that the applications have valid AppStream metadata.
- Restart Discover after updating the repository configuration.

On Fedora-based systems, the Flatpak backend can typically be installed with:

```bash
sudo dnf install plasma-discover-flatpak
```

On Ubuntu or Debian-based distributions, the corresponding package is commonly:

```bash
sudo apt install plasma-discover-backend-flatpak
```

Package names may vary depending on your distribution.

You can also refresh repository metadata:

```bash
flatpak update --user --appstream
```

> [!IMPORTANT]
> A working Flatpak repository does not automatically guarantee that its applications will appear in Discover's search results. Discover depends on valid AppStream metadata for application listings.

---

## Updating Applications

Once ArtCraft has been added as a Flatpak remote, you no longer need to manually download a new `.flatpak` bundle whenever an application is updated.

### Update through the terminal

To update all user-installed Flatpak applications:

```bash
flatpak update --user
```

To update a specific ArtCraft application:

```bash
flatpak update --user ai.storyteller.photocraft
```

### Update through KDE Discover

1. Open KDE Discover.
2. Navigate to **Updates**.
3. Check for available updates.
4. Install the available ArtCraft updates.

Discover can manage updates from configured Flatpak repositories alongside supported software sources.

> [!NOTE]
> New application versions become available after a successful repository synchronization. Update availability depends on the source repository and the user's local Flatpak configuration.

---

## Repository Synchronization

This repository is built and published through **GitHub Actions**.

The automation is configured to:

1. Check the latest GitHub Releases for supported ArtCraft projects.
2. Locate compatible Linux x86_64 Flatpak bundles.
3. Download the upstream bundles.
4. Import them into an OSTree repository.
5. Generate Flatpak repository metadata.
6. Read each imported application's runtime requirement and verify its exact ID, architecture and branch on stable Flathub using a clean Flatpak configuration.
7. Generate application `.flatpakref` installation files with a Flathub runtime-source hint.
8. Publish the resulting repository through GitHub Pages only if every check succeeds.

If any required runtime is unavailable or Flathub cannot be reached, publication stops and the previous deployment remains online. The workflow records verified runtime requirements in its run summary. It does not rewrite dependencies in prebuilt bundles or prove that applications launch correctly. Users still need Flathub enabled locally; changing the workflow does not alter existing client configurations.

### Update Schedule

The workflow is scheduled to run daily at **06:00 UTC**.

It can also be triggered manually through the GitHub Actions interface or when its workflow file is updated on the main branch.

[View GitHub Actions](https://github.com/p4rzl/artcraft-flatpak-repo/actions)

> [!WARNING]
> Scheduled runs are not guaranteed to execute at an exact time. Repository updates depend on the successful completion of the workflow and deployment.

---

## Repository Information

| Property | Value |
|---|---|
| Name | ArtCraft |
| Type | Flatpak / OSTree |
| Maintainer | Community-maintained |
| Source | Official Storytold GitHub releases |
| Architecture | x86_64 |
| Update method | GitHub Actions |
| Update frequency | Daily |
| Hosting | GitHub Pages |
| GPG verification | Disabled |
| Repository URL | `https://artcraft.p4rzl.it/` |
| Repository descriptor | `https://artcraft.p4rzl.it/artcraft.flatpakrepo` |

### Security Notice

This repository currently distributes upstream Flatpak bundles without its own GPG signing.

Disabling GPG verification means Flatpak does not cryptographically verify repository updates using a trusted repository signing key.

Users should understand this limitation before installing applications from this source.

The repository should be considered an unofficial community mirror, not an authenticated distribution channel operated by Storytold.

---

## Uninstalling Applications

To uninstall an individual application:

```bash
flatpak uninstall --user ai.storyteller.photocraft
```

Replace the application ID with the one you want to remove.

### Removing the Repository

To remove the ArtCraft source:

```bash
flatpak remote-delete --user artcraft
```

Flatpak may warn you if applications installed from this repository are still present.

If necessary, uninstall the affected applications before removing the remote.

You can also manage configured software sources through KDE Discover.

---

## Troubleshooting

### Repository cannot be added

Check whether the repository is reachable:

```bash
curl -I https://artcraft.p4rzl.it/artcraft.flatpakrepo
```

If the server returns an error, the repository may not have been deployed yet or the custom domain may be incorrectly configured.

### Application not found

Refresh repository metadata:

```bash
flatpak update --user --appstream
```

Then list the available applications:

```bash
flatpak remote-ls --user artcraft
```

If the application is missing, it may not have been imported successfully during the latest synchronization.

### Dependencies cannot be resolved

An error such as `requires the runtime org.freedesktop.Platform/x86_64/26.08 which was not found` means Flatpak could not resolve that exact dependency from the available sources. It does not by itself mean the runtime version is invalid.

For the user installation used throughout this guide:

```bash
flatpak remote-add --user --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
flatpak remote-modify --user --enable flathub
flatpak remote-info --user flathub runtime/org.freedesktop.Platform/x86_64/26.08
flatpak install --user artcraft ai.storyteller.photocraft
```

The runtime check above matches the reported PhotoCraft dependency; if an error names another runtime, check that exact reference instead. Close and reopen Discover after adding the source.

If ArtCraft is installed system-wide, use `--system` consistently instead of `--user`. Check both scopes with `flatpak remotes --show-details`. If `remote-info` still fails, inspect its error and the Flathub URL, network access and any repository filter before retrying. `--if-not-exists` does not repair an existing remote with an incorrect URL or filter. Do not replace `26.08` with an older version or edit the imported app metadata to bypass the requirement.

Refreshing AppStream only refreshes the catalog; it does not add a missing runtime source. Existing users must add or enable Flathub once even after the updated ArtCraft workflow is deployed.

### Applications do not appear in KDE Discover

Confirm that the Flatpak backend is installed and enabled.

Check whether the repository contains valid AppStream metadata.

Applications without usable AppStream metadata may still be installable through the terminal even when they are not listed in Discover's graphical catalog.

### Updates are not appearing

Check the latest GitHub Actions runs:

https://github.com/p4rzl/artcraft-flatpak-repo/actions

If the latest synchronization failed, new upstream releases may not yet be available through the ArtCraft repository.

---

## Upstream Projects

All ArtCraft applications are developed and distributed by their respective upstream maintainers.

Visit the official upstream GitHub organization:

**[Storytold on GitHub](https://github.com/storytold)**

This repository downloads publicly available release artifacts and redistributes them through an independent Flatpak repository.

For issues related to the applications themselves, refer to their official upstream repositories.

For issues related to repository synchronization, Flatpak distribution, or GitHub Pages deployment, open an issue in this repository.

[Report a Repository Issue](https://github.com/p4rzl/artcraft-flatpak-repo/issues)

---

## Credits

**ArtCraft applications:** Storytold and their respective contributors.

**Flatpak:** The Flatpak project and contributors.

**Repository maintenance:** Independent community project.

This repository is intended to improve accessibility and convenience for Linux users while respecting the work and rights of the original developers.

---

*ArtCraft Flatpak Repository — Simplifying ArtCraft installation and updates on Linux.*

