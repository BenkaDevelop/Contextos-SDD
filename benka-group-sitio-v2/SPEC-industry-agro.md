# SPEC · industry-agro (R7) · Agroindustria y sus 5 eslabones

Estado: **R7a en producción** (5 nov 2026 · PR BenkaDevelop/benka-group#244 → qa, release #245) · **R7b (5 eslabones) en producción el 6 nov 2026** (#262 → qa, #263 → main) · Release R7 · Referencia de diseño: prototipo v3.7 (rama `feature/site-v2-industrias-careers-ecosistema`, `src/pages/industry-detail/*`, `src/data/agro.ts`)

## 1. Objetivo
Publicar la primera página de industria al estilo McKinsey/BCG. Debe servir de modelo para las otras 8 industrias (R8–R15):
- La página /industries/agro-industry.
- 5 páginas, una por eslabón de la cadena de valor: Cultivo, Cosecha y acopio, Transporte, Planta y Mercado.
- La fila "Agro-industry" del hub /industries se vuelve clicable (`live: true`).

## 2. Punto de partida
- **Producción hoy:** el hub /industries muestra la fila de Agro-industry sin clic. No existe ninguna página de industria.
- **Prototipo:** ya tiene la página completa y los eslabones. Sus contenidos todavía no están validados:
  - Imágenes generadas con IA.
  - Cifras tomadas de prensa económica (P-09 a P-13).
  - KPIs ilustrativos (P-08).
  - Caso sin cifras (P-04).

## 3. Momentos de la página Agroindustria (se aprueban uno por uno)

| # | Momento | Qué se ve en el prototipo | Pendiente para aprobar |
|---|---|---|---|
| A1 | Hero | Foto a pantalla completa (camiones entre cañaduzales al atardecer) · migas · "AGROINDUSTRIA" · "Del campo a la mesa." · "Del campo a la mesa, con productividad, trazabilidad y valor compartido." · "Hablemos de tu reto" y "Ver casos de éxito" | Imagen IA o foto real · el subtítulo repite el título |
| A2 | Cadena de valor | Fondo tierra · "Acompañamos cada eslabón de la cadena" · texto de intro · 5 tarjetas con foto, número, nombre, frase y "Ver más" hacia cada eslabón | 5 imágenes IA |
| A3 | Retos | "Los retos de agroindustria" · 4 retos con 3 cifras cada uno; la fuente aparece al pasar el cursor · foto de silos a la derecha | 12 cifras de prensa (P-13) · imagen IA |
| A4 | Cómo te acompañamos | 5 capacidades en filas con la unidad líder (Consulting, Digital LAB, Media, Social Venture) | Textos de capacidades |
| A5 | Panel del sector | Panel oscuro "Agro Colombia 2025-2026" con 4 pestañas y gráfica (PIB, exportaciones, pérdidas y costo logístico) · fila "Lo que movemos con nuestros clientes" (+18% / −12% / −28% / 100%) marcada "Por validar" | P-09, P-11 · KPIs ilustrativos P-08 |
| A6 | Caso destacado | Banner a pantalla completa (ingenio del Valle) · "Cómo una agroindustria familiar del Valle del Cauca se preparó para su segunda generación" · reto, enfoque y resultados sin cifras | P-04: sin cifras ni permiso · imagen IA |
| A7 | Expertos | Jhohan Axelrod (Managing Partner), Helena Valencia (Partner · Región Andina) y José Martínez (Partner · Región Caribe) con "Ver perfil" | Confirmar cargos y si José tiene perfil publicado (P-28) |
| A8 | Otras industrias | "Otras industrias, otros mundos" · 8 tarjetas con foto y "Explorar" | Esas páginas no existen aún |
| A9 | Cierre | Banda azul con pattern y contacto | — |

## 4. Momentos de cada eslabón (misma plantilla × 5)

| # | Momento | Qué se ve |
|---|---|---|
| E1 | Hero | Foto del eslabón · migas · "CADENA DE VALOR · 01 DE 5" · nombre · frase · "Hablemos de tu reto" y "Siguiente: {eslabón}" |
| E2 | Navegación entre eslabones | Barra fija con los 5 eslabones y el activo en azul |
| E3 | El eslabón en cifras | Título, intro y 4 cifras con su fuente |
| E4 | Tendencias 2025-2026 | 3 tarjetas "Lo que está cambiando" |
| E5 | Mejores prácticas y digitalización | "Lo que hacen los líderes" (4 prácticas) · "Herramientas que ya funcionan" (4 etiquetas) |
| E6 | El ecosistema Benká en el eslabón | 2–3 filas con la unidad líder |
| E7 | Volver / siguiente y fuentes | Tarjeta "← Volver Agroindustria" y "Siguiente eslabón →" · "Fuentes (n)" desplegable · cierre azul |

## 5. Decisiones (5 nov 2026, Jhohan Axelrod) · R7a aprobado momento por momento
- Imágenes: IA para paisajes y operación, combinadas con fotos reales del equipo (sesión RDM del Kit de Marca de Comunicaciones). En A3 solo fotos grupales y del equipo trabajando, sin repetir.
- Cifras de mercado: todas con fuente visible.
- A1 hero con panel de vidrio oscuro y tarjeta del equipo de Consultoría.
- A2 fondo blanco; eslabones con «Pronto» hasta R7b.
- A3 tarjetas tipo client impact; una se abre cada 6 s en su lugar (no es carrusel).
- A4 en glass sobre foto del equipo, con unidad líder.
- A5 panel del sector en glass sobre azul Benká (sin foto); KPIs «Referencia sectorial».
- A6 caso en glass, cualitativo (sin cifras hasta validarlas).
- A7 expertos con cargos de la página de socios.
- A8 carrusel tipo Apple sobre azul noche Benká; industrias con «Pronto».
- A9 cierre con banda azul. Fila Agro-industry del hub clicable.
- Regla de color permanente: #8AB7F9 sobre fondos oscuros, #1E41FF sobre claros (SPEC-ui-base).

## 6. Criterios de aceptación
- Ninguna cifra sin fuente y sin aprobación de Jhohan. Las cifras sin validar (P-08 a P-13) no salen, o salen solo si Jhohan las aprueba con su fuente visible.
- Ninguna imagen IA sin aprobación explícita.
- Sin enlaces a páginas que no existen.
- Se cumple la regla de los glass del menú.
- Sin desborde a 390 px. Respeta `prefers-reduced-motion`.
- La fila Agro-industry del hub queda clicable.
