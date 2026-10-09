# ArtCraft Suite — Flatpak Repository

> [!NOTE]
> **Disclaimer:** This repository is an unofficial, community-maintained project and is **not affiliated with, endorsed by, or connected to** the upstream ArtCraft team or Storytold. It was created solely to simplify installation and provide automatic system updates for Linux users via Flatpak. All upstream rights and trademarks belong to their respective creators.

This repository hosts an automated OSTree mirror for the [ArtCraft suite](https://github.com/storytold) applications on Linux.

Available applications:
* **PhotoCraft**
* **VectorCraft**
* **FilmCraft**
* **LightCraft**
* **PdfCraft**
* **EffectCraft**
* **DesignCraft**

---

## Method 1: Command Line (CLI)

This is the fastest and most reliable setup method.

### 1. Add the Repository
Run the following command to add the repository for your current user:

```bash
flatpak remote-add --user --if-not-exists --no-gpg-verify artcraft-repo [https://artcraft.p4rzl.it/](https://artcraft.p4rzl.it/)
