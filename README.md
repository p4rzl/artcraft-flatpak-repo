# ArtCraft Suite — Custom Flatpak Repository

> [!NOTE]
> **Disclaimer:** This repository is an unofficial, community-maintained project and is **not affiliated with, endorsed by, or connected to** the upstream ArtCraft team or Storytold. It was created solely to simplify installation and provide automatic system updates for Linux users via Flatpak. All upstream rights and trademarks belong to their respective creators.

This repository hosts an automated OSTree mirror for the [ArtCraft suite](https://github.com/storytold) applications on Linux.

### Available Applications
* **LightCraft:** `ai.storyteller.lightcraft`
* **PhotoCraft:** `ai.storyteller.photocraft`
* **VectorCraft:** `ai.storyteller.vectorcraft`
* **FilmCraft:** `ai.storyteller.filmcraft`
* **PdfCraft:** `ai.storyteller.pdfcraft`
* **EffectCraft:** `ai.storyteller.effectcraft`
* **DesignCraft:** `ai.storyteller.designcraft`

---

## Prerequisites

ArtCraft applications require the FreeDesktop runtime (`org.freedesktop.Platform`). Make sure the Flathub remote is configured for your user:

```bash
flatpak remote-add --user --if-not-exists flathub [https://dl.flathub.org/repo/flathub.flatpakrepo](https://dl.flathub.org/repo/flathub.flatpakrepo)
