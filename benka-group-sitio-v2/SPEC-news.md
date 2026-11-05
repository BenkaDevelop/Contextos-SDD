# SPEC · news (R4) · Noticias

Estado: **aprobada por Jhohan Axelrod el 5 nov 2026** · **en producción** (PR BenkaDevelop/benka-group#226 → qa, release #227 → main) · carrusel, Medios en red y Diversity Win en producción (PR BenkaDevelop/benka-group#242 → qa, release #243) · Release R4 · Épica BenkaDevelop/benka-group#177 (historias #178–#181)

## 1. Objetivo
Darle a benkagroup.co una sala de prensa al estilo BCG/McKinsey. Debe mostrar lo que pasa en el holding (personas, proyectos, impacto) y darle alta visibilidad a Helena Valencia y a Black Women Shaping Afrofutures.

## 2. Fuente de los contenidos (sin inventar textos)
- **Notas de prensa reales**: las 4 que hoy viven en las páginas de los socios (Firestore `aboutUs`). Cada una abre su fuente original:

| # | Título | Medio | Persona | Enlace |
|---|---|---|---|---|
| 1 | Robótica en Quibdó: la chocoana que escogió la Fundación Ford como becaria | Forbes Women | Helena Valencia | forbes.co |
| 2 | Helena Valencia: una voz que inspira transformación social | Mujer CAFAM | Helena Valencia | librosdeoro.cafam.com.co |
| 3 | #SoyEgresadoSoyUnivalle | Univalle | Jhohan Axelrod | YouTube |
| 4 | Becario Sueños de Paz: Fundación Bancolombia y Lumni | Fundación Lumni | Jhohan Axelrod | sin enlace (P-39) |

- **Black Women Shaping Afrofutures Forum (3.ª edición)**: 11 y 12 de marzo de 2026, Teachers College, Columbia University, Nueva York. Organizadores: AGBARA, CEERT, KILOMBA y Benká Social Venture; con el apoyo de Ford Foundation y BSA. Fuente: nota de Columbia ISHR "HRAP Advocates Champion Black Women's Futures at Columbia Forum" (19 mar 2026). La nota **no trae citas de Helena** (las citas son de Júlia Mota y Nyawira Wahito), así que la página no le atribuye palabras. Fotos: 8 fotos reales del foro en la rama `fotos-bws-ny2026` (crédito de la nota: Jeison Riascos).
- **Reporte de gestión BIC 2025**: el PDF que ya está en el menú Reportes.

## 3. Momentos (se aprueban uno por uno)

| # | Momento | Qué se ve | Estado |
|---|---|---|---|
| N1 | Menú | Opción "Noticias" **junto a Reportes** (… Careers · Noticias · Reportes) · sin desplegable, va directo a /news | Aprobado |
| N2 | Hero y mosaico de /news | Migas · eyebrow "NOTICIAS" · "Lo más reciente de Benká" · mosaico: **grande = Black Women Shaping Afrofutures con Helena sentada**, Reporte BIC 2025 en azul con pattern, #SoyEgresadoSoyUnivalle con la foto de su nota a tamaño real sobre azul | Aprobado |
| N3 | Archivo | Eyebrow "ARCHIVO" · "Todas las noticias" · filtros Todas · Eventos · Prensa · Reportes · **misma tarjeta de las noticias de las páginas de socios** (foto 273×292 a tamaño real, tiempo de lectura, título, resumen, medio y "Ver más"), en 2 columnas | Aprobado |
| N4 | Black Women Shaping Afrofutures | Página /news/black-women-shaping-afrofutures · hero con Helena frente al backdrop del foro · "Sobre el foro" con retrato de Helena, resumen de la nota de Columbia, organizadores, apoyo, lugar y fecha, edición y fuente · hero con Helena hablando en negro con panel de vidrio · galería tipo Apple "Así vivimos el foro" (9 fotos, foto grande, miniaturas glass, flechas y teclado; filtro Todo / Con Helena) · cierre "¿Quieres sumarte?" | Aprobado |
| N5 | Cierre de /news | Banda azul con pattern: "¿Quieres contar una historia con nosotros?" · "Escríbenos para alianzas, prensa y eventos." · "Hablemos" y "Ver capabilities" | Aprobado |
| N6 | Mosaico en el home | "Lo más reciente de Benká": 1 destacada + 3 tarjetas al estilo BCG · "Ver todas las noticias" · **después de Nosotros**, donde estaba el Ecosistema, antes de Nuestro Impacto | Aprobado |
| N8 | Carrusel destacado | El espacio grande del mosaico (home y /news) rota cada 7 s entre Black Women Shaping, el documental Medios en red y Diversity Win · flechas ‹ › y barras de avance en glass · pausa con el cursor o el foco · cada tarjeta abre su página arriba · el documental usa la miniatura del video | Aprobado |
| N9 | Medios en red | Página /news/medios-en-red · documental de Benká Group **creado con el acompañamiento de Canal Trece y MinTIC** (formación y clases; Canal Trece no lo emite) · hero azul con los dos afiches · video de YouTube `zrW4PpDge2M` con la miniatura como portada · historia con Jhohan Axelrod y Eliana Segura (directora) · "Lo que respalda la historia": Forbes, robótica con la Fundación Sociedad Portuaria, Univalle Sede Pacífico, Black Women Shaping. **No se publican** el código de la postulación ni los puntajes | Aprobado |
| N10 | Diversity Win | Página /news/diversity-win-buenaventura · 28 de abril de 2026 · panel en la Universidad del Valle, Sede Pacífico (panelistas Jhohan Axelrod y Valeria Mosquera, Directora Contable y Financiera; moderación Eliana Segura), radio entrevista Diversity Win (2:00 a 3:00 pm, Radio Nacional de Colombia · Emisoras de Paz) y Momentos de Paz (Emisora de Paz Buenaventura 104.9 FM, RTVC) · galería tipo Apple de 16 fotos con filtros Panel en Univalle / Radio Nacional | Aprobado |
| N7 | Páginas de socios | Las notas siguen apareciendo en Helena y Jhohan como hoy (sin cambios) | Aprobado |

## 4. Decisiones (5 nov 2026, Jhohan Axelrod)
- Las notas de prensa externas **abren su fuente** en pestaña nueva ("Leer en {medio}").
- Jhohan adjunta en el chat las fotos y videos de BWS, la cita de Helena y la fecha y el lugar (P-16, P-17, P-24). Mientras tanto se construye el resto de R4.
- Mosaico del home después de Nosotros; "Noticias" en el menú junto a Reportes.

## 5. Fuera de alcance
- Detalle interno /news/:slug para notas externas: abren su fuente original.
- Publicaciones de Benká Media (artículos de Jhohan sin enlace) hasta que exista el enlace.
- CMS: las noticias viven en `src/data/news.ts`. Pasarlas a Firestore queda en el módulo `platform`.

## 6. Criterios de aceptación
- Ninguna noticia con texto inventado: todo sale de Firestore, de Comunicaciones o del reporte.
- Las notas externas abren en pestaña nueva con `rel="noopener"`.
- /news sin desborde a 390 px; Lighthouse de accesibilidad ≥ 90.
- El home no pierde ninguna sección aprobada.
