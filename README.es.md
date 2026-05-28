# Nova Red Theme

**3 temas visuales adicionales para el sistema Cyberpunk RED Core en Foundry VTT.**

Al activarse, este módulo agrega tres nuevos temas al menú desplegable de configuración del sistema, reemplazando la apariencia predeterminada con una estética cyberpunk oscura e inmersiva. Cada jugador puede elegir su tema preferido de forma independiente.

[Read in English](README.md)

---

## Temas

| Tema | Vista previa | Descripción |
|---|---|---|
| **Nova Red (Ámbar)** | – | Fondos oscuros con acentos ámbar/dorados. La apariencia distintiva de Nova-Red. |
| **Bluewire (Eléctrico)** | – | Fondos azul marino profundo con acentos cian/azul eléctrico y reflejos rosa neón. |
| **Afterlife (CP2077)** | – | Fondos casi negros con acentos rojos/dorados inspirados en el bar Afterlife. |

Todos los temas usan la fuente monoespaciada **Tektur** para una estética tech-noir.

---

## Instalación

### Método 1: URL de Manifiesto (Recomendado)

1. Abre Foundry VTT y ve a la pestaña **Add-on Modules**.
2. Haz clic en **Install Module**.
3. Pega la siguiente URL:
   ```
   https://github.com/DKSEN404/nova-red-theme/releases/latest/download/module.json
   ```
4. Haz clic en **Install**.

### Método 2: Manual

1. Descarga el [module.zip](https://github.com/DKSEN404/nova-red-theme/releases/latest/download/module.zip) más reciente desde la página de Releases.
2. Extrae el contenido en `{userData}/Data/modules/nova-red-theme/`.
3. Reinicia Foundry VTT.

---

## Uso

1. Ve a **Settings → Game Settings → Configure Settings**.
2. Busca la configuración del sistema **Cyberpunk RED Core**.
3. Busca el menú desplegable **Theme**.
4. Selecciona tu tema preferido: **Nova Red (Ámbar)**, **Bluewire (Eléctrico)** o **Afterlife (CP2077)**.
5. La interfaz se actualiza al instante — no necesita recargar.

> El tema **Modo Oscuro** del sistema base también está disponible en el mismo menú.

---

## Compatibilidad

- **Sistema:** Cyberpunk RED Core (v0.92.0+)
- **Foundry VTT:** v12

Sin conflictos conocidos con otros módulos. Compatible con [Nova-Red UI](https://github.com/DKSEN404/nova-red-ui).

---

## Desarrollo

```
nova-red-theme/
├── module.json                  # Manifiesto Foundry VTT
├── scripts/
│   └── main.mjs                 # Registro de temas vía API cprcThemes
├── styles/
│   └── nova-red-theme.css       # Declaraciones de los 3 temas
├── lang/
│   ├── en.json                  # Etiquetas en inglés
│   └── es.json                  # Etiquetas en español
├── README.md                    # Documentación en inglés
├── README.es.md                 # Documentación en español
└── AGENTS.md                    # Contexto para asistentes IA
```

### Cómo funciona

El sistema Cyberpunk RED Core expone una API `cprcThemes` en los objetos de módulo. Este módulo registra sus temas a través de esa API, lo que hace que aparezcan automáticamente en el menú desplegable de Temas del sistema. No se necesita parchear ni sobrescribir archivos del sistema.

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
