# Ruta de trabajo · Benká Group sitio v2

Estado: **aprobada por Jhohan Axelrod el 5 nov 2026** (fase 0 de SDD: mapa de capacidades). Siguiente paso: spec por módulo, en orden de construcción.

## Principios

- **Aprobación momento por momento (regla de Jhohan, 5 nov 2026).** El prototipo es guía, no aprobación. Cada spec lista sus **momentos** (cada sección de cada página: contenido, textos, imágenes, interacción y estado) y Jhohan aprueba cada uno a detalle antes de implementarlo. Nada se publica con un momento sin aprobar.

- **Punto de partida = producción.** Toda feature nace de `main` (hoy `68ae402`). El prototipo v3.7 (rama `feature/site-v2-industrias-careers-ecosistema` + cambios locales) es la **referencia de diseño**, no se mergea en bloque.
- **Flujo de ramas** (el que ya usa el repo): `feature/<modulo>-<historia>` → PR a `qa` → revisión en el preview del PR → PR `qa` → `main` → deploy automático a Hostinger.
- **Releases pequeños.** Cada historia es un PR de ≤ 5 archivos aprox., verificable en el preview, y deja producción funcionando. Lo que no está listo se oculta (no se publica a medias).
- **Specs en `BenkaDevelop/Contextos-SDD`**, una por módulo (`specs/SPEC-<modulo>.md`). Historias como issues en `BenkaDevelop/benka-group`, enlazadas a su spec. Tablero en el GitHub Project 3.
- **Cada sesión: un módulo, historia por historia.** Spec aprobada → plan → historias → implementación → PR.

## Mapa de módulos

| # | Módulo (id) | Qué incluye | Depende de | Tamaño |
|---|---|---|---|---|
| 1 | `ui-base` | Flecha estándar (Arw), botones glass, fila azul (C2), UnitLogo, PageShell/Sections, animación de scroll y barra de avance | — | S |
| 2 | `nav` | Menú: Nosotros, Trayectoria, Holding, Industrias, Capabilities, Noticias, Careers, Reportes; desplegable glass con luz; hamburguesa < 1160 px; ajuste del footer | ui-base | S |
| 3 | `holding` | Página /holding: 4 compañías con dominio, presencia regional (/ecosystem redirige) | ui-base | S |
| 4 | `capabilities` | Página /capabilities: 22 prácticas en orden alfabético, filtros, ancla desde el menú | ui-base | M |
| 5 | `news` | /news, detalle /news/:slug, mosaico en el home, Black Women Shaping Afro Future con Helena | ui-base | M |
| 6 | `home` | Ecosistema + oficinas, tarjetas "Únete al equipo" con Ver más hacia Careers, sección de noticias | news, careers (anclas) | S |
| 7 | `industries-hub` | /industries: lista con fila azul, Cómo trabajamos (WorkRoute), casos destacados simétricos, CTA | ui-base | M |
| 8 | `industry-agro` | Agroindustria completa (piloto): hero a pantalla completa, cadena de valor, retos con cifras, DataPanel, caso banner, expertos, otras industrias + 5 páginas por eslabón | industries-hub | L |
| 9 | `industries-rest` | Las otras 8 industrias con el modelo de agro, una por release | industry-agro | L (8 × M) |
| 10 | `careers` | Rediseño de Careers (hoy: secciones Tu carrera, Ser consultor, Proceso) | ui-base | M (pendiente de diseño) |
| 11 | `unit-sites` | Sitios de Consulting, Media, Digital LAB y Social Venture con dominio propio | nav, holding | L (pendiente dominios con Helena) |
| 12 | `platform` | SEO (sitemap, metas), GA4, optimización de imágenes, fuentes por dominio, 404 | — | M (transversal) |

**Orden de construcción:** ui-base → nav → holding, capabilities → news → home → industries-hub → industry-agro → industries-rest (×8) → careers → unit-sites. `platform` corre en paralelo, una historia por release.

## Releases propuestos (de lo más pequeño a lo más relevante)

| Release | Módulos | Qué ve el usuario en producción |
|---|---|---|
| R1 | ui-base | Nada visible cambia de golpe: base de botones, flecha y animación lista para usar |
| R2 | nav (sin Holding/Capabilities/Noticias aún) | Desplegable glass en Industrias, Careers y Reportes; hamburguesa en pantallas medianas; footer ajustado |
| R3 ✅ | holding + capabilities + nav | Aparecen Holding y Capabilities en el menú con sus páginas; el Ecosistema sale del home y vive en /holding · **en producción 5 nov 2026** |
| R4 ✅ | news + home (noticias) | Noticias en el menú y en el home; Black Women Shaping Afrofutures con fotos reales del foro en Columbia · **en producción 5 nov 2026** |
| R5 ✅ | home | Únete al equipo con Ver más (baja a Transforma tu carrera hasta R16); oficinas pasan de Trayectoria al home · **en producción 5 nov 2026** |
| R6 ✅ | industries-hub | Nueva página de Industrias · **en producción 5 nov 2026** |
| R6b ✅ | i18n (selector) | Selector de idioma junto a Contacto; EN y PT visibles con "Pronto" · **en producción 5 nov 2026** |
| R7 | industry-agro | Agroindustria y sus 5 eslabones |
| R8–R15 | industries-rest | Una industria por release (sugerido: Consumo masivo, Retail, Servicios financieros, Digital, Educación, Sector social, Medios y telecom, Oil & Gas) |
| R16b | i18n (traducciones EN · PT) | Al final, con todas las páginas montadas: IA + agente de idiomas + aprobación por página; rutas /en y /pt con hreflang |
| R16 | careers | Careers rediseñado |
| R17+ | unit-sites | Un sitio de unidad por release |

## Historias (issues) por módulo — borrador

**ui-base**
1. Componente Arw y variantes de botón (primario, glass, contorno, blanco).
2. Fila seleccionable C2 y UnitLogo.
3. Animación de entrada al hacer scroll y barra de avance (respeta "reducir movimiento").

**nav**
1. Menú desde configuración única (`navigation.ts`), sin desplegable en Nosotros/Trayectoria.
2. Desplegable glass con luz (Industrias, Careers, Reportes).
3. Hamburguesa por debajo de 1160 px y prueba en 1440/1280/1100/390.
4. Ajuste del hueco del footer.

**holding**
1. Página /holding con las 4 compañías y su dominio.
2. Presencia regional (Colombia validada; resto "Por validar" hasta confirmar).
3. Redirección /ecosystem → /holding y entrada Holding en el menú.

**capabilities**
1. Datos de 22 prácticas (orden alfabético, unidad líder, industrias).
2. Página /capabilities con filtros y tarjetas.
3. Desplegable de 3 columnas con ancla a cada práctica.

**news**
1. Datos y página /news con archivo filtrable.
2. Detalle /news/:slug.
3. Mosaico en el home.
4. Black Women Shaping Afro Future con fotos y videos reales, Helena protagonista.

**home**
1. Tarjetas "Únete al equipo" clicables con Ver más hacia Careers (#tu-carrera, #ser-consultor, #proceso).
2. Ecosistema Benká con Oficinas debajo.

**industries-hub**
1. Lista de industrias clicable con fila azul.
2. Cómo trabajamos (WorkRoute) con foto.
3. Casos destacados simétricos y CTA con pattern.

**industry-agro**
1. Hero a pantalla completa y cadena de valor con fotos y Ver más.
2. Retos con cifras y fuentes.
3. DataPanel (tablero del sector) + KPIs ilustrativos.
4. Caso destacado como banner.
5. Expertos y galería de otras industrias.
6. Páginas por eslabón (5) con anterior/siguiente.

**platform** (transversal)
1. Optimización de imágenes (hoy ~250 MB de assets).
2. Sitemap y metadatos de las rutas nuevas.
3. GA4 y eventos de CTA.
4. Página 404.

## Fuera de alcance por ahora

- Dominios propios de las unidades (revisar con Helena).
- Rediseño completo de Careers (pendiente de diseño).
- Cifras de casos sin validar: se publican solo con su marca "Por validar" o se ocultan, según decida Comunicaciones.

## Decisiones y pendientes

- Las cifras "Por validar" y demás temas abiertos viven en [BACKLOG-pendientes.md](BACKLOG-pendientes.md) y deben quedar definidos en el spec de cada módulo antes de pasar a producción.
- Tablero: GitHub Project 3 con el flujo "Auto-add to project" (filtro `repo:BenkaDevelop/benka-group is:issue`).
- Historias: issues en `BenkaDevelop/benka-group` con etiquetas `epic`/`story`, `mod:<modulo>` y milestone por release.
