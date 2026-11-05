# Spec: ui-base · Componentes base del sitio v2

Módulo `ui-base` · Release R1 · Épica BenkaDevelop/benka-group#160 · Historias #161, #162, #163
Estado: **aprobada por Jhohan Axelrod el 5 nov 2026** · Implementación: BenkaDevelop/benka-group#218

## Objetivo

Llevar a producción, sin cambiar nada visible todavía, los componentes que usarán todos los módulos siguientes (menú, holding, capabilities, noticias, industrias). Así cada release posterior solo compone piezas ya probadas y el sitio mantiene un lenguaje único.

Quién lo usa: el equipo de desarrollo (directamente) y los visitantes de benkagroup.co (a partir de R2, cuando los módulos los adopten).

Éxito: los componentes existen en `main`, compilan, pasan lint y se ven idénticos al prototipo aprobado en una página de muestra oculta; ninguna página actual de producción cambia.

## Alcance

| Historia | Componente | Comportamiento aprobado (prototipo v3.7) |
|---|---|---|
| #161 | `Arw` + variantes `bk-btn` | Flecha del botón "Ver más" del carrusel. Al pasar el cursor el texto se desplaza ~22 px y entra una flecha nueva por la izquierda. Variantes: primario (azul), glass (blanco 30 % + desenfoque 12 px), contorno, blanco con texto azul; tamaño normal y `--sm` |
| #162 | Fila C2 + `UnitLogo` | Fila seleccionable: la fila completa se llena de azul Benká de izquierda a derecha (0,45 s), texto blanco, botón "Ver más" en glass. UnitLogo: logo de la unidad en su color oficial (máscara SVG) sobre su fondo, clicable hacia el sitio de la unidad |
| #163 | `useScrollReveal` + barra de avance | Bloques que entran en pantalla suben 36 px y aparecen (0,8 s, escalonado 70 ms). Lo visible al cargar no se anima. Barra azul de 3 px arriba marca el avance de lectura |

Fuera de alcance: adoptar estos componentes en páginas existentes (eso es R2 en adelante), el desplegable glass (módulo `nav`).

## Supuestos

1. Los componentes viven en `src/components/sections/` (como en el prototipo) y los estilos en SCSS con los colores de `general-styles/_colors.module.scss`.
2. `UnitLogo` necesita `src/data/sites.ts` (nombre, dominio y logo de cada unidad). Se sube solo con lo que el componente usa; los dominios siguen pendientes (backlog P-25), así que el enlace apunta por ahora a la red social que ya usa el home de producción para cada unidad.
3. No hay framework de pruebas en el repo; la verificación es build + lint + revisión visual en el preview del PR.
4. La página de muestra `/_ui` está en producción, visible, sin enlace en el menú.

→ Corrígeme cualquiera de estos supuestos al aprobar.

## Tech stack

React 18.3 · TypeScript 5.6 · Vite 6 · SCSS (sass 1.83) · react-router 7 · despliegue en Hostinger por FTP al hacer merge a `main`.

## Comandos

```bash
npm ci
npm run dev          # http://localhost:5173
npm run build        # tsc -b && vite build
npm run lint         # eslint .
npm run commit       # commitizen (conventional commits)
```

## Estructura

```
src/components/sections/
  Sections.tsx      → Arw, UnitLogo, useScrollReveal (y luego PageShell, CtaBand…)
  Sections.scss     → .bk-btn y variantes, .bk-arw, .bk-row C2, .bk-unitlogo, .bk-rv, .bk-progress
src/data/sites.ts   → datos mínimos de las 4 unidades para UnitLogo
src/pages/ui/UiKit.tsx → página de muestra /_ui (producción, visible)
```

## Estilo de código

```tsx
/** Flecha estándar del sitio (la del botón "Ver más" del carrusel). */
export function Arw({ children }: { children?: ReactNode }) {
  return (
    <span className={`bk-arw ${children ? "" : "bk-arw--icon"}`}>
      <span className="bk-arw__i1" aria-hidden><IconArrow /></span>
      {children && <span className="bk-arw__t">{children}</span>}
      <span className="bk-arw__i2" aria-hidden><IconArrow /></span>
    </span>
  );
}
```

- Componentes en PascalCase, hooks `useX`, clases BEM con prefijo `bk-`.
- Textos visibles en español; comentarios cortos en español.
- Sin dependencias nuevas.
- Animaciones con `prefers-reduced-motion: reduce` respetado siempre.

## Pruebas y verificación

- `npm run build` y `npm run lint` sin errores ni warnings nuevos.
- Revisión visual en el preview del PR, página `/_ui`, en 1440, 1100 y 390 px: cada variante en reposo y al pasar el cursor, y con foco de teclado.
- Comparación con el prototipo v3.7 (rama `feature/site-v2-industrias-careers-ecosistema`): misma apariencia.
- Regresión: home, trayectoria, nosotros e industrias de producción se ven igual que antes (captura antes/después).

## Límites

- **Siempre:** ramas desde `main`; PR a `qa`; conventional commits; respetar "reducir movimiento"; foco visible.
- **Preguntar antes:** agregar dependencias; tocar el workflow de despliegue; cambiar estilos globales existentes.
- **Nunca:** cambiar páginas de producción en este release; subir imágenes pesadas; enlazar `/_ui` desde el menú.

## Criterios de éxito

1. `Arw`, variantes de botón, fila C2, `UnitLogo` y `useScrollReveal` están en `main`.
2. `/_ui` muestra cada pieza y se comporta igual que el prototipo aprobado.
3. Ninguna página existente cambia (capturas antes/después idénticas).
4. Build y lint en verde; deploy a Hostinger exitoso.

## Decisiones

1. La página de muestra `/_ui` va a producción y es visible (decisión de Jhohan). No se enlaza desde el menú.
2. Mientras no haya dominios propios, UnitLogo enlaza a las redes de cada unidad (LinkedIn de Consulting, Media y Digital LAB; Instagram de Social Venture). Cuando se activen los sitios de unidad, avisar a Jhohan para comprar los dominios y activarlos en producción (backlog P-25).
