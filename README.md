# ≋ Windy Hub — Widget Repository

This repository is the official widget repository for the Windy widget marketplace.

## Adding a Widget

1. Create your widget folder under `widgets/`
2. Add `widget.toml` + `index.html` (if applicable)
3. Create a `widget.zip` (zip the contents inside the folder, not the folder itself)
4. Add the widget details to `registry.json`
5. Open a Pull Request

## Folder Structure

```
windy-hub/
├── registry.json          ← Widget list (Windy fetches this file)
├── widgets/
│   ├── my-widget/
│   │   ├── widget.toml
│   │   ├── index.html     (Pro mode)
│   │   ├── preview.png    (512x320)
│   │   └── widget.zip     ← Users download this
│   └── ...
└── README.md
```

## Creating Widget.zip

### Required Files

**widget.zip must contain:**
- `widget.toml` — Required. Widget configuration file
- `index.html` — Required for Pro mode widgets only. Simple mode widgets don't need this

### Optional Files

- `preview.png` — Optional. Preview image shown in Widgets section (recommended: 512x320px)
- Asset files — Images, icons, fonts, CSS, JS files referenced by index.html

### Widget.zip Structure

```
widget.zip
├── widget.toml           ← Required (all widgets)
├── index.html            ← Required (Pro mode only)
├── preview.png           ← Optional (Widgets preview)
├── assets/               ← Optional (Pro mode assets)
│   ├── icon.png
│   └── style.css
└── ...
```

### Creating the zip

**Important:** Zip the contents inside the widget folder, NOT the folder itself.

```bash
# Windows PowerShell
cd widgets/my-widget
Compress-Archive -Path * -DestinationPath widget.zip

# or with 7-Zip
7z a widget.zip ./*

# or with standard zip
zip -r widget.zip *
```

### Mode Differences

**Simple Mode:**
- Only `widget.toml` required
- Windy renders HTML automatically from toml configuration
- No `index.html` needed

**Pro Mode:**
- `widget.toml` + `index.html` required
- Full HTML/CSS/JS control
- Can include external assets

## Registry.json Format

```json
{
  "id": "my-widget",
  "name": "My Widget",
  "author": "username",
  "description": "Widget description",
  "version": "1.0.0",
  "tags": ["system", "minimal"],
  "category": "system",
  "preview_url": "https://raw.githubusercontent.com/.../preview.png",
  "download_url": "https://raw.githubusercontent.com/.../widget.zip"
}
```

## Categories

- `system` — CPU, RAM, disk, network
- `clock` — Clock and date
- `weather` — Weather forecast
- `media` — Music and media
- `productivity` — Todo, pomodoro, calendar
- `custom` — Others
