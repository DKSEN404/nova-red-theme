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
![3 Temas](https://img.shields.io/badge/Temas-3-00bbee?style=flat-square)
![MIT](https://img.shields.io/badge/Licencia-MIT-313131?style=flat-square)

> **🌐 Español** · [English](README.md)

# Nova Red Theme

> **3 temas visuales adicionales para Cyberpunk RED Core en Foundry VTT.**  
> Nova Red (Ámbar) · Bluewire (Eléctrico) · Afterlife (CP2077)

Al activarse, este módulo agrega tres nuevos temas al menú desplegable de configuración del sistema, reemplazando la apariencia predeterminada con una estética cyberpunk oscura e inmersiva. Cada jugador puede elegir su tema preferido de forma independiente.

---

## Temas

| Tema | Hex | Descripción |
|------|-----|-------------|
| **Nova Red (Ámbar)** | `#ffb000` | Fondos oscuros con acentos ámbar/dorados. La apariencia distintiva de Nova-Red. |
| **Bluewire (Eléctrico)** | `#00bbee` | Fondos azul marino profundo con acentos cian/azul eléctrico y reflejos rosa neón. |
| **Afterlife (CP2077)** | `#da291c` | Fondos casi negros con acentos rojos/dorados inspirados en el bar Afterlife. |

Todos los temas usan la fuente monoespaciada **Tektur** para una estética tech-noir. Compatibles con el **Modo Oscuro** incluido del sistema.

---

## Instalación

```
https://github.com/DKSEN404/nova-red-theme/releases/latest/download/module.json
```

**Foundry VTT → Add-on Modules → Install Module → Pegar URL del manifiesto**

---

## Uso

1. Ve a **Settings → Game Settings → Configure Settings**.
2. Busca la sección **Cyberpunk RED Core**.
3. Busca el menú desplegable **Theme**.
4. Selecciona tu tema preferido.
5. La interfaz se actualiza al instante — no necesita recargar.

---

## Compatibilidad

| | |
|---|---|
| **Sistema** | Cyberpunk RED Core v0.92.0+ |
| **Foundry VTT** | v12 |
| **Conflictos** | Ninguno conocido. |

Compatible con [Nova-Red UI](https://github.com/DKSEN404/nova-red-ui).

---

## Historial de cambios

### v1.0.0 — Lanzamiento Inicial *(2026-05-28)*
- **Nova Red (Ámbar)** — sobreescritura completa de variables `:root` con paleta ámbar-sobre-negro
- **Bluewire (Eléctrico)** — tema cian/azul eléctrico con acentos rosa neón
- **Afterlife (CP2077)** — tema rojo/dorado inspirado en el bar Afterlife
- Registro de temas vía API `cprcThemes` del sistema — sin modificar archivos del sistema
- Bilingüe: inglés + español (LA)

---

## Desarrollo

```
nova-red-theme/
├── module.json                  # Manifiesto Foundry VTT
├── scripts/
│   └── main.mjs                 # Registro de temas vía API cprcThemes
├── styles/
│   └── nova-red-theme.css       # Declaraciones de los 3 temas (~16 KB)
├── lang/
│   ├── en.json                  # Etiquetas en inglés
│   └── es.json                  # Etiquetas en español
├── README.md                    # Documentación en inglés
├── README.es.md                 # Documentación en español
└── AGENTS.md                    # Contexto para asistentes IA
```

### Cómo funciona

El sistema Cyberpunk RED Core expone una API `cprcThemes` en los objetos de módulo. Este módulo registra sus temas a través de esa API, lo que hace que aparezcan automáticamente en el menú desplegable de Temas del sistema. El CSS del módulo se carga después del sistema, por lo que las sobreescrituras de `:root` tienen prioridad sin modificar ningún archivo del sistema.

### Compilación y lanzamiento

```powershell
# Crear zip para distribución
7z a -tzip module.zip scripts styles lang module.json "-x!Thumbs.db" -r

# Crear GitHub Release
gh release create v1.0.0 --title "v1.0.0 — Lanzamiento Inicial" --notes "..." module.json module.zip
```

---

## Licencia

MIT © DKSEN404
