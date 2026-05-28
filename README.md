# Nova Red Theme

**3 additional visual themes for the Cyberpunk RED Core system on Foundry VTT.**

When activated, this module adds three new themes to the system settings dropdown, replacing the default look with a dark, immersive cyberpunk aesthetic. Players can choose their preferred theme independently.

[Leer en Español](README.es.md)

---

## Themes

| Theme | Preview | Description |
|---|---|---|
| **Nova Red (Amber)** | – | Dark backgrounds with warm amber/gold accents. The signature Nova-Red look. |
| **Bluewire (Electric)** | – | Deep navy backgrounds with cyan/electric blue accents and hot pink highlights. |
| **Afterlife (CP2077)** | – | Near-black backgrounds with red/gold accents inspired by the Afterlife bar. |

All themes use the **Tektur** monospace font for a tech-noir feel.

---

## Installation

### Method 1: Manifest URL (Recommended)

1. Open Foundry VTT and navigate to the **Add-on Modules** tab.
2. Click **Install Module**.
3. Paste the following URL:
   ```
   https://github.com/DKSEN404/nova-red-theme/releases/latest/download/module.json
   ```
4. Click **Install**.

### Method 2: Manual

1. Download the latest [module.zip](https://github.com/DKSEN404/nova-red-theme/releases/latest/download/module.zip) from the Releases page.
2. Extract the contents into `{userData}/Data/modules/nova-red-theme/`.
3. Restart Foundry VTT.

---

## Usage

1. Go to **Settings → Game Settings → Configure Settings**.
2. Find the **Cyberpunk RED Core** system settings.
3. Look for the **Theme** dropdown.
4. Select your preferred theme: **Nova Red (Amber)**, **Bluewire (Electric)**, or **Afterlife (CP2077)**.
5. The UI updates instantly — no reload required.

> The **Dark Mode** theme from the base system is also available in the same dropdown.

---

## Compatibility

- **System:** Cyberpunk RED Core (v0.92.0+)
- **Foundry VTT:** v12

No known conflicts with other modules. Compatible with [Nova-Red UI](https://github.com/DKSEN404/nova-red-ui).

---

## Development

```
nova-red-theme/
├── module.json                  # Foundry VTT manifest
├── scripts/
│   └── main.mjs                 # Theme registration via cprcThemes API
├── styles/
│   └── nova-red-theme.css       # All 3 theme declarations
├── lang/
│   ├── en.json                  # English labels
│   └── es.json                  # Spanish labels
├── README.md                    # English documentation
├── README.es.md                 # Spanish documentation
└── AGENTS.md                    # AI assistant context
```

### How it works

The Cyberpunk RED Core system exposes a `cprcThemes` API on module objects. This module registers its themes through that API, which makes them appear automatically in the system's Theme dropdown. No patching or overriding of system files is needed.

### Build and Release

```powershell
# Create zip for distribution
7z a -tzip module.zip scripts styles lang module.json "-x!Thumbs.db" -r

# Create GitHub Release
gh release create v1.0.0 --title "v1.0.0 — Initial Release" --notes "..." module.json module.zip
```

---

## License

MIT © DKSEN404
