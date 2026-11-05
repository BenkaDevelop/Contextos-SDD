# Spec: holding · Página /holding

Módulo `holding` · Release R3 (junto con `capabilities`) · Épica BenkaDevelop/benka-group#169 · Historias #170, #171, #172
Depende de: `ui-base` (R1), `nav` (R2)
Estado: **borrador para aprobación**

## Objetivo

Que un visitante entienda en una sola página que Benká Group es un holding de cuatro compañías (Consulting, Media, Digital LAB y Social Venture), qué hace cada una y dónde opera, y pueda saltar al canal de cada una. Reemplaza el concepto "Ecosistema" y se enciende en el menú como **Holding**.

Éxito: /holding en producción igual al prototipo aprobado (v3.7, página "Holding"), la opción Holding visible en el menú con el desplegable de las 4 compañías, y ningún dato sin validar publicado sin decisión.

## Alcance

| Historia | Qué se publica |
|---|---|
| #170 Página /holding | Hero "más allá del asesoramiento" (en azul), una tarjeta por compañía con foto (sin cortar caras), territorio, propósito, 4 servicios y botón "Ir a {canal}" con la flecha estándar |
| #171 Presencia regional | Bloque "Por qué somos el catalizador": Colombia con foto real; Ecuador, Perú, Chile y Argentina según decisión P-14 |
| #172 Menú y redirección | Holding se enciende en el menú con desplegable glass de las 4 compañías; /ecosystem y /ecosystem/:unit redirigen a /holding |

Fuera de alcance: sitios propios de cada unidad (módulo `unit-sites`, requiere dominios P-25).

## Supuestos

1. Los textos de cada compañía (territorio, propósito, servicios) vienen de `units.ts` del prototipo, tomados de los brand books y el brochure. Ya fueron revisados en las rondas de diseño.
2. Los botones de cada compañía llevan a su red (LinkedIn/Instagram), como `UnitLogo`, hasta tener dominios.
3. Fotos: las del equipo retocadas (sin líneas de marca) para las tarjetas; para los países, las imágenes generadas con IA quedan sujetas a P-23.
4. CTA final con el pattern de marca hacia Contacto.

## Estructura

```
src/data/units.ts            → compañías: nombre, territorio, propósito, servicios, foto, tema
src/pages/holding/Holding.tsx + .scss
src/assets/images/people/*   → fotos retocadas (webp)
src/router/routes.tsx        → /holding, redirecciones /ecosystem
src/data/navigation.ts       → Holding enabled + items
```

## Verificación

- Build y lint en verde; revisión en 1440, 1100 y 390 px.
- Preview HTML aprobado por Jhohan antes de abrir el PR (abrir el PR publica en producción).
- Peso: imágenes nuevas en WebP, total de la página < 1,5 MB.

## Límites

- **Siempre:** rama desde `main`; flecha y botones de R1; textos en español.
- **Preguntar antes:** publicar países sin validar; usar imágenes IA en producción.
- **Nunca:** enlazar a dominios que aún no existen.

## Criterios de éxito

1. /holding en producción con las 4 compañías y su canal.
2. Holding en el menú con desplegable; /ecosystem redirige.
3. Presencia regional publicada según la decisión P-14.

## Preguntas abiertas (para decidir con opción múltiple)

1. **P-14 Países:** ¿publicamos Ecuador, Perú, Chile y Argentina, solo Colombia, o los demás como "Próximamente"?
2. **P-23 Imágenes IA de países:** ¿se aprueban para producción o usamos fotos de stock con licencia?
