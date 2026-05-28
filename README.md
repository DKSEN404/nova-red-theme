```text
╔══════════════════════════════════════════════════════════╗
║        █▄▄▄ █ █ ▄▀▄ ▄▀▄   █▀▄▄▀█ ██ █ █▀▄             ║
║        █▄▄  █▄█ ▀▄▀ ▀▄▀   █ ▀▀ █ █▄█ █ █▀              ║
║                                                          ║
║    █▀▄▀█ █▀▀█ █▀▀  █ █   █▀▀ █▀▀█ █▀▀  █▀▀█            ║
║    █ ▀ █ █▄▄█ ▀▀█  █▄█   █   █▄▄█ ▀▀█  █▄▄█            ║
║    ▀   ▀ ▀  ▀ ▀▀▀  ▄▀▄   ▀▀▀ ▀  ▀ ▀▀▀  ▀  ▀            ║
╚══════════════════════════════════════════════════════════╝
```

![Foundry VTT v12](https://img.shields.io/badge/Foundry_VTT-v12-amber?style=flat-square&logo=foundryvirtualtabletop&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Cyberpunk RED](https://img.shields.io/badge/Cyberpunk_RED-ff0000?style=flat-square)
![3 Themes](https://img.shields.io/badge/Themes-3-00bbee?style=flat-square)
![MIT](https://img.shields.io/badge/License-MIT-313131?style=flat-square)

> **🌐 English** · [Español](README.es.md)

# Nova Red Theme

> **3 additional visual themes for Cyberpunk RED Core on Foundry VTT.**  
> Nova Red (Amber) · Bluewire (Electric) · Afterlife (CP2077)

When activated, this module adds three new themes to the system settings dropdown, replacing the default look with a dark, immersive cyberpunk aesthetic. Players can choose their preferred theme independently.

---

## Themes

| Theme | Hex | Description |
|-------|-----|-------------|
| **Nova Red (Amber)** | `#ffb000` | Dark backgrounds with warm amber/gold accents. The signature Nova-Red look. |
| **Bluewire (Electric)** | `#00bbee` | Deep navy backgrounds with cyan/electric blue accents and hot pink highlights. |
| **Afterlife (CP2077)** | `#da291c` | Near-black backgrounds with red/gold accents inspired by the Afterlife bar. |

All themes use the **Tektur** monospace font for a tech-noir feel. Compatible with the system's built-in **Dark Mode**.

---

## Installation

```
https://github.com/DKSEN404/nova-red-theme/releases/latest/download/module.json
```

**Foundry VTT → Add-on Modules → Install Module → Paste manifest URL**

---

## Usage

1. Go to **Settings → Game Settings → Configure Settings**.
2. Find the **Cyberpunk RED Core** section.
3. Look for the **Theme** dropdown.
4. Select your preferred theme.
5. The UI updates instantly — no reload required.

---

## Compatibility

| | |
|---|---|
| **System** | Cyberpunk RED Core v0.92.0+ |
| **Foundry VTT** | v12 |
| **Conflicts** | None known. |

Compatible with [Nova-Red UI](https://github.com/DKSEN404/nova-red-ui).

---

## Changelog

### v1.0.0 — Initial Release *(2026-05-28)*
- **Nova Red (Amber)** — full `:root` CSS variable override with amber-on-black palette
- **Bluewire (Electric)** — cyan/electric blue theme with hot pink accents
- **Afterlife (CP2077)** — red/gold theme inspired by the Afterlife bar
- Theme registration via system's `cprcThemes` API — no system files modified
- Bilingual: English + Spanish (LA)

---

## Development

```
nova-red-theme/
├── module.json                  # Foundry VTT manifest
├── scripts/
│   └── main.mjs                 # Theme registration via cprcThemes API
├── styles/
│   └── nova-red-theme.css       # All 3 theme declarations (~16 KB)
├── lang/
│   ├── en.json                  # English labels
│   └── es.json                  # Spanish labels
├── README.md                    # English documentation
├── README.es.md                 # Spanish documentation
└── AGENTS.md                    # AI assistant context
```

### How it works

The Cyberpunk RED Core system exposes a `cprcThemes` API on module objects. This module registers its themes through that API, making them appear automatically in the system's Theme dropdown. The module's CSS is loaded after the system's, so `:root` overrides take precedence without modifying any system files.

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
