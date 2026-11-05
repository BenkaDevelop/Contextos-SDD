# Spec: Sitio Benká Group v2

Estado: **borrador para aprobación** · 4 nov 2026 · Responsable: Jhohan Axelrod

## Mapa de capacidades (Fase 0)

| Módulo | Responsabilidad | Depende de |
|---|---|---|
| content-model | Contenido editable en `src/data/*` (industrias, unidades, careers, personas, fotos) | — |
| ui-sections | Bloques reutilizables (`src/components/sections`) con tema por unidad | — |
| photography | Curaduría, calificación y retoque de fotos del Kit de Marca | — |
| industries | Landing de industrias ampliada + 9 páginas de industria | content-model, ui-sections, photography |
| ecosystem | Hub del ecosistema + 4 páginas de unidad con su paleta | content-model, ui-sections, photography |
| careers | Página de Careers | content-model, ui-sections, photography |
| navigation | Header, rutas, enlaces desde el home | industries, ecosystem, careers |
| platform | Hosting, reescritura SPA, analítica, formularios, CMS, SEO | navigation |

Orden: content-model, ui-sections, photography → industries, ecosystem, careers → navigation → platform.

## Objetivo
Que el sitio explique con claridad que Benká Group es una firma de consultoría estratégica que implementa, con la profundidad de McKinsey/BCG: qué hacemos por industria, casos con cifras, expertos, el ecosistema de unidades y una propuesta de carrera robusta. Sin cambiar lo existente: solo se agrega sobre la línea gráfica actual.

**Usuarios:** directivos de empresas (clientes), candidatos (talento), aliados e inversionistas.

## Stack
React 18 + TypeScript + Vite 6 + SCSS + react-router 7 + Firebase (Firestore). Hosting actual: Hostinger por FTP al hacer merge a `main`.

## Comandos
- Instalar: `yarn install --frozen-lockfile`
- Desarrollo: `yarn dev`
- Build: `yarn build`
- Lint: `yarn lint`
- Vista de revisión (artifact): build con HashRouter y assets comprimidos desde una copia en el scratchpad.

## Estructura
```
src/data/               contenido editable (fuente única de textos y cifras)
src/components/sections bloques v2 compartidos
src/pages/industry-detail, unit, ecosystem, careers   páginas nuevas
src/assets/images/people  fotografía retocada (webp)
docs/                   este spec
```

## Estilo de código
Componentes funcionales en TSX, SCSS con BEM corto (`bk-*`), tokens de color de `_colors.module.scss`, tema por unidad vía variables CSS (`--bk-accent`, `--bk-soft`, `--bk-deep`).

## Estrategia de pruebas
`tsc -b` + `vite build` sin errores; revisión visual con Playwright en 1440px y 390px sin desborde horizontal ni errores de consola; revisión humana en el HTML de revisión.

## Límites
- **Siempre:** agregar sin romper lo existente; cifras solo de fuentes oficiales; casos sin validar marcados "Por validar"; clientes anónimos.
- **Preguntar antes:** cualquier push, PR o merge a los repos; cambios de hosting o DNS; nuevas dependencias; publicar fotos de personas con nombre.
- **Nunca:** subir a `main` ni desplegar a producción sin aprobación explícita; inventar cifras; usar imágenes de McKinsey/BCG (solo como referencia de estructura).

## Criterios de éxito
1. Las 9 industrias de `/industries` son cliqueables y cada una muestra retos, capacidades, casos, unidades y expertos.
2. Existe `/careers` con caminos, proceso, gente, oficinas y FAQ.
3. Existen `/ecosystem` y 4 páginas de unidad con la paleta de su manual de marca.
4. Fotos reales del equipo, calificadas (sin bocas abiertas) y retocadas con la línea Benká.
5. Build sin errores, sin desborde en móvil, y ninguna cifra no validada sin la etiqueta "Por validar".
6. Nada llega a los repos ni a producción sin aprobación.

## Preguntas abiertas
Ver la pestaña "Decisiones" del HTML de arquitectura.
