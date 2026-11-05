# Spec: nav · Menú principal y footer

Módulo `nav` · Release R2 · Épica BenkaDevelop/benka-group#164 · Historias #165, #166, #167, #168
Depende de: `ui-base` (en producción desde R1)
Estado: **aprobada por Jhohan Axelrod el 5 nov 2026** · PR BenkaDevelop/benka-group#220

## Objetivo

Dejar el menú de benkagroup.co listo para crecer con el sitio v2 sin publicar enlaces a páginas que aún no existen. El menú sale de una sola configuración, los desplegables usan el efecto glass con luz aprobado, el menú no choca con el logo en pantallas medianas y el footer queda corregido.

Quién lo usa: visitantes de benkagroup.co en escritorio y móvil.

Éxito: en producción el menú se ve y funciona como el prototipo aprobado en lo que hoy existe; las opciones nuevas (Holding, Capabilities, Noticias) quedan listas pero apagadas hasta su release.

## Estado actual en producción

- Escritorio: Nosotros · Trayectoria · Industrias · Careers (baja a la sección del home) · Reportes (desplegable blanco con el reporte BIC 2025) · Contacto.
- Móvil (≤ 768 px): hamburguesa con las mismas opciones.
- Footer: hueco de 120 px entre el titular y los logos; el LinkedIn de Social Venture apunta a `benká-social-ventur` (URL truncada).

## Alcance

| Historia | Qué cambia en producción |
|---|---|
| #165 Configuración única (`navigation.ts`) | El menú de escritorio y móvil se arma desde un solo archivo. Cada opción tiene un interruptor `enabled`; Holding, Capabilities y Noticias quedan con `enabled: false` hasta R3/R4. Industrias sigue llevando a /industries (sin desplegable de industrias hasta que existan sus páginas, R6). Careers sigue bajando a la sección del home hasta que exista /careers |
| #166 Desplegable glass con luz | Reportes (único desplegable vigente) pasa del panel blanco al vidrio oscuro con brillo que sigue el cursor, con la flecha estándar de R1. Funciona con teclado (Tab, Enter, Esc) |
| #167 Hamburguesa por debajo de 1160 px | Entre 768 y 1160 px el menú pasa a hamburguesa para no chocar con el logo. Probado en 1440, 1280, 1100 y 390 px |
| #168 Footer | Hueco entre titular y logos de 120 px a 48 px; LinkedIn de Social Venture corregido |

Fuera de alcance: páginas nuevas (Holding, Capabilities, Noticias, industrias, Careers); desplegables de Industrias, Capabilities y Careers (se encienden con su release).

## Supuestos

1. Se conserva el componente `Header` actual y su comportamiento al hacer scroll (se oculta al bajar y aparece al subir); solo cambia cómo se arman las opciones y el estilo del desplegable.
2. La URL correcta de LinkedIn de Social Venture es `https://www.linkedin.com/company/benká-social-venture`. **Hay que confirmarla.**
3. El efecto glass usa `backdrop-filter`; en navegadores sin soporte se ve como panel oscuro sólido (legible igual).
4. Sin pruebas automáticas en el repo: verificación con build, lint y revisión visual.

→ Corrígeme cualquiera de estos supuestos al aprobar.

## Estructura

```
src/data/navigation.ts            → NavSection[] con label, to, items, enabled
src/components/header/Header.tsx  → arma escritorio y móvil desde navigation.ts
src/components/header/Header.scss → .capabilities-menu--glass, breakpoint 1160 px
src/components/footer/Footer.tsx  → URL de Social Venture
src/components/footer/Footer.scss → .brands-container margin-top 48 px
```

## Estilo de código

```ts
export interface NavSection {
  label: string;
  to?: string;
  /** Vacío = enlace directo, sin desplegable. */
  items: NavLink[];
  /** false = aún no se publica (su página llega en un release posterior). */
  enabled: boolean;
}
```

## Verificación

- `npm run build` y `npm run lint` sin errores nuevos.
- Antes del PR: el cambio se muestra en el preview HTML para aprobación de diseño (decisión de Jhohan).
- Revisión en 1440, 1280, 1100 y 390 px: sin choque con el logo; desplegable de Reportes abre con cursor y con teclado; el PDF abre en pestaña nueva.
- Regresión: Nosotros, Trayectoria, Industrias, Careers y Contacto llevan al mismo destino que hoy.

## Límites

- **Siempre:** rama desde `main`; conventional commits; foco visible; respetar "reducir movimiento".
- **Preguntar antes:** cambiar destinos actuales del menú; tocar el comportamiento de scroll del header.
- **Nunca:** publicar enlaces a páginas que no existen en producción.

## Criterios de éxito

1. El menú sale de `navigation.ts` y las opciones apagadas no aparecen en producción.
2. Reportes muestra el desplegable glass con luz y se usa con teclado.
3. Sin choque con el logo en ninguno de los cuatro anchos.
4. Footer con hueco de 48 px y LinkedIn de Social Venture funcionando.

## Nota de despliegue

Por decisión de Jhohan se mantiene el flujo actual: **abrir el PR publica en benkagroup.co** (no hay QA separado). Por eso cada PR se abre solo cuando el diseño ya está aprobado en el preview.

## Preguntas abiertas

1. ¿Confirmas la URL de LinkedIn de Social Venture?
2. Careers: mientras no exista /careers, ¿sigue bajando a la sección del home? Recomendación: sí.
