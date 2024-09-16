---
category: "[[Clippings]]"
author: "[[Scientific Computing]]"
title: Install ImageJ for Linux
source: https://www.scivision.dev/install-imagej-linux/
clipped: 2024-09-16
published: 2018-05-01
tags:
  - clippings
  - imagej
  - image-processing
---

May 1, 2018

In general for Linux it’s better to install ImageJ directly *instead of* `apt install imagej`. This also works for Pi and other ARM systems.

Install Java Environment (also works with `openjdk-jre`)

[Download](https://imagej.nih.gov/ij/download.html) latest **independent** ImageJ Unzip to `~/ImageJ` recursively

Add to `~/.bash_aliases`

```
alias imagej="$HOME/ImageJ/ImageJ"
```

Close and reopen Terminal, then start ImageJ by:

Create Imagej by creating file `~/.local/share/applications/imagej.desktop` with contents:

```
[Desktop Entry]
Type=Application
Exec=~/ImageJ/ImageJ
Name=ImageJ
Icon=~/ImageJ/images/icon.png
Categories=AudioVideo;Video;Science;
```

If can’t open ImageJ via the menu/icon,

should open ImageJ .