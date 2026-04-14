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

```bash
# Windows PowerShell
cd widgets/my-widget
Compress-Archive -Path * -DestinationPath widget.zip

# or with 7-Zip
7z a widget.zip ./my-widget/*
```

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
