# Icon Files Required

Before building the desktop app, you need to add icon files to this directory:

Required files:
- 32x32.png
- 128x128.png
- 128x128@2x.png
- icon.icns (macOS)
- icon.ico (Windows)

You can generate these icons using the Tauri CLI:

```bash
# If you have a source icon (e.g., icon.png, 1024x1024 recommended)
npm run tauri icon /path/to/your/icon.png
```

Or you can create placeholder icons manually for testing.

For production, it's recommended to use a professional icon that represents your application.
