---
tags:
  - linux
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
