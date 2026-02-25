---
publish: true
created: 2025-07-04T18:52:18.210+02:00
modified: 2026-02-25T22:03:50.230+01:00
tags:
  - linux
cssclasses: ""
---

# Install AppImage like any other application
## Extract icon from AppImage
`./your.AppImage --appimage-extract`

CD into the created directory and move the icon file into `~/.local/share/applications/`

Create a `name.desktop` file in `~/.local/share/applications/`
```
[Desktop Entry]
Name=Application name
Exec=/home/username/.local/share/applications/Application.AppImage
Comment="Application description"
Icon/home/username/.local/share/applications/icon.png
Type=Application
Terminal=false
Encoding=UTF-8
Categories=Utility;
```
