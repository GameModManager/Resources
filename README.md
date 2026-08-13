# Resources

Static resources for GameModManager: icons, images, and vendor assets.

## Directory Structure

```
icons/
├── ACTIVE_ICONS.txt          # Registry of active icon keys
├── gmm-logo.{ico,png,svg}   # Application logo
├── plugin-*.png              # Plugin status icons
├── proton.png                # Proton/Wine icon
├── packs/                    # Icon packs
│   ├── Fugue/               # Fugue icon set
│   └── MO2/                 # MO2-style icons
└── vendor/                   # Vendor-specific icons
    ├── nexusmods.ico
    ├── loverslab.ico
    ├── steam.ico
    └── moddb.ico
```

## Icon Registry

`ACTIVE_ICONS.txt` lists all icon keys recognized by the application. Each line contains the key name passed to `IconManager::resolve_icon()`.

### Icon Keys

- **UI icons**: `dialog-ok`, `dialog-cancel`, `list-add`, `list-remove`, etc.
- **Plugin icons**: `plugin-dummy`, `plugin-light`, `plugin-medium`, `plugin-locked`, `plugin-warning`
- **Status icons**: `conflict-*`, `mod-invalid`
- **Navigation**: `go-up`, `go-down`, `go-top`, `go-bottom`
- **File operations**: `document-new`, `document-edit`, `document-open-folder`, `save`

### Vendor Icons

Vendor icons are resolved via `engine::vendor_icon_key()` and stored in the `vendor/` directory:

- `nexusmods` - NexusMods
- `loverslab` - LoversLab
- `steam` - Steam
- `moddb` - ModDB

## Icon Packs

Icon packs provide alternative icon sets. The application loads icons from packs in priority order:

1. Custom user icons (if present)
2. Selected icon pack
3. Default icons

## Adding Icons

1. Place the icon file in the appropriate directory
2. Add the key to `ACTIVE_ICONS.txt`
3. Ensure the icon is available in at least one pack or as a standalone file