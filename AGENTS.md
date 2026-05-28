# AGENTS.md — Nova Red Theme

## Descripción

Módulo Foundry VTT que agrega 3 temas visuales al sistema Cyberpunk RED Core. Usa la API `cprcThemes` expuesta por el sistema — no modifica ningún archivo del sistema.

## Estructura

```
nova-red-theme/
├── module.json              # Manifiesto Foundry VTT
├── scripts/
│   └── main.mjs             # Registro de temas vía cprcThemes
├── styles/
│   └── nova-red-theme.css   # 3 temas (nova-red, bluewire, afterlife)
├── lang/
│   ├── en.json              # Etiquetas en inglés
│   └── es.json              # Etiquetas en español
└── README.md / README.es.md / AGENTS.md
```

## Temas registrados

```js
module.cprcThemes = {
  'nova-red': 'Nova Red (Ámbar)',
  'bluewire': 'Bluewire (Eléctrico)',
  'afterlife': 'Afterlife (CP2077)',
};
```

## API del sistema

El `cprcThemes` se fusiona con `CPR.themes` en `SystemUtils.GetThemes()`. Cuando el usuario selecciona un tema, se establece `data-cpr-theme="<key>"` en `<html>`.

## Mecanismo CSS

- `:root` → siempre activo cuando el módulo está encendido (sobrescribe colores base del sistema)
- `[data-cpr-theme="nova-red"]` → cuando se selecciona Nova Red
- `[data-cpr-theme="bluewire"]` → cuando se selecciona Bluewire
- `[data-cpr-theme="afterlife"]` → cuando se selecciona Afterlife
- El CSS del módulo se carga DESPUÉS del sistema, por lo que `:root` tiene prioridad

El sistema controla la opción "darkmode" por su cuenta. Si el módulo está activo, `:root` siempre se aplica (Nova Red como base), y los temas alternativos (bluewire, afterlife) solo cambian las variables.

Para compatibilidad con tema oscuro del sistema: `[data-cpr-theme="darkmode"]` tiene mayor especificidad que `:root`, por lo que el darkmode del sistema sigue funcionando incluso con el módulo activo.

## Release

1. Actualizar `version` en `module.json`
2. `git tag vX.Y.Z && git push origin vX.Y.Z`
3. `7z a -tzip module.zip scripts styles lang module.json "-x!Thumbs.db" -r`
4. `gh release create vX.Y.Z --title "vX.Y.Z — ..." --notes "..." module.json module.zip`
