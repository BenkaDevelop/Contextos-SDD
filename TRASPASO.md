# Traspaso · Benká Group sitio v2 y Nova

Actualizado el 6 nov 2026 (tarde) desde el proyecto «Proyecto NOVA», sesión `session_01WEQvrdBjk3Aa5sTUx3AkBe`. Léelo completo antes de tocar algo.

## 1. Quién y cómo se trabaja
- **Dueño:** Jhohan Axelrod, Presidente Ejecutivo de Benká Group (jaxelrod@benkagroup.co).
- **Método:** Spec-Driven Development. Primero el spec en este repositorio y después el código.
- **Repositorios:**
  - Specs: `BenkaDevelop/Contextos-SDD`.
  - Sitio: `BenkaDevelop/benka-group`.
  - Nova: `BenkaDevelop/benka-nova`.
- **Flujo de publicación:**
  1. Se trabaja en una rama `feature/…` o `release/…`.
  2. Se abre un PR a `qa`; esto ya publica en producción por FTP en Hostinger.
  3. Se abre un PR de `qa` a `main`.
  - Si el FTP falla, se relanza el run con `gh api -X POST repos/BenkaDevelop/benka-group/actions/runs/<id>/rerun`.

## 2. Reglas permanentes de Jhohan
- **Aprobación:**
  - No se sube nada a los repositorios sin su aprobación explícita. Subir una rama `feature` está bien una vez aprobado el cambio; los PR requieren su «publícalo».
  - Se aprueba **por página completa en la Mesa de aprobación de la consola** (vista en vivo de escritorio a 1440 px y de iPhone 13, momentos, cifras con fuente y pendientes). Nada sale a producción sin pasar por la mesa.
- **Preguntas:** siempre de selección múltiple con la herramienta de opciones, con la recomendación marcada.
- **Tipografía:** solo las de Benká (Atyp) en todos los textos.
- **Credenciales:** «McKinsey Alumni» y «Grupo Aval Alumni» solo para Jhohan, en la sección de socios, no en el hero.
- **Contenido:**
  - Nunca se inventan textos, cifras ni citas.
  - Las cifras de mercado llevan la fuente visible y enlazada.
  - Los casos de cliente van cualitativos, sin cifras, hasta que se validen.
- **Color:**
  - Sobre fondos oscuros, azul claro Benká `#8AB7F9`. Sobre fondos claros, azul catalyst `#1E41FF`. Ningún otro azul.
  - Azul noche: `radial-gradient(90% 120% at 85% 0%, #1E41FF 0%, #10228F 38%, #070D3A 100%)`.
- **Menú (glass):** los desplegables arrancan donde termina la barra (66 px en escritorio, 48 px por debajo de 1280 px), con una pestaña azul `rgba(30,65,255,.92)`. Se mide en escritorio y en celular antes de publicar.
- **Fotos:**
  - Imágenes IA para paisajes y operación; fotos reales del equipo (sesión RDM del Kit de Marca) para personas.
  - No se repiten fotos y se prefieren las grupales.
  - En Holding no se usan imágenes IA. La foto de Colombia no se cambia.
- **Idioma:** los nombres de industria van en inglés; los textos en español.
- **Tono:** firma de alta estrategia; nada asistencialista. Casos con Reto → Enfoque → Impacto.
- **Dominios:** avisar a Jhohan antes de activar los sitios de unidad, para que compre los dominios (P-25).

## 3. Estado al 6 nov 2026 (cierre de la tarde)
**En producción (hasta el PR #273):**
- Releases R1 a R7a, Oficinas por ciudad, R7b (5 eslabones de Agroindustria) y plataforma (#264, #265).
- **Las 9 industrias:** R8–R11 (#262, #263) y R12–R15 Education, Social Sector, Media & Telecommunications y Oil & Gas (#272, #273). Sitemap con 32 URL.
- **Industrias conectada con Capabilities (#266, #267):** menú de Industrias en dos niveles (sector primario, secundario y terciario a la izquierda; capabilities de la industria señalada a la derecha); Capabilities con etiquetas de industria enlazadas y filtro por industria; nuevas industrias Public Sector y Multilateral & International Cooperation con `live: false` («Pronto»); capabilities por industria validadas por Jhohan.
- **Home y Capabilities (#268, #269):** carrusel de We Make Growth Happen con 5 tarjetas a la vista (Talento Benká, Industrias, Capabilities, Careers, Trayectoria); franja «Se aplica en» con las industrias de cada capability en el menú.
- **Fase 0 · Posicionamiento (#270, #271):** hero «The Catalyst for the Future» con píldora glass del ancho de «Catalyst» («Rigor estratégico, resultados que se miden.»), párrafo y CTAs ejecutivos; bloque «Nuestro enfoque» (4 fases, luz que las recorre, mapa de LATAM con destellos) después del carrusel; Noticias → «Perspectivas» (misma ruta /news); insignias de Jhohan; textos de tono.

**Plan vigente (ver `PLAN-DE-TRABAJO.md` en el proyecto):**
- Fase 1 (montar el sitio como el prototipo) y Fase 0 (posicionamiento): hechas.
- **Fase 2:** refinar página por página, empezando por las industrias (fuentes primarias, fotos, casos validados, diseño). Lo publicado fuera de Industrias es versión final.
- Fase 3: Nova.

**Cómo se trabaja ahora:**
- **Consola única** «Proyecto Nova Benká Group»: https://claude.ai/artifact/PHU8Cjw4dTYnYDbV7N4y4U — Tablero · Arquitectura · Experiencia (Sitio en producción compilado de `main` + Mesa de aprobación). Reemplaza los HTML sueltos.
- **Compilar sin npm local:** la rama `feature/consola-build` de benka-group tiene un flujo de GitHub Actions que compila (con `tsc -b`) la rama escrita en el archivo `BUILD_REF` y la guarda en `consola-dist` (si es `main`) o en `consola-preview-<rama>`, sin tocar `qa`, `main` ni Hostinger. Se cambia `BUILD_REF`, se hace push y se clona la rama de salida.
- **Agentes en paralelo:** cada uno en su propia carpeta clonada y su rama desde `origin/main`; nunca en la carpeta compartida.
- Conflictos al integrar industrias: en `routes.tsx` se conservan las líneas de ambas ramas; en `industries-hub.ts`, una sola fila por industria.

**Specs:**
- Aprobados: `SPEC-nova` (D1 a D13).
- Borradores por aprobar: `SPEC-careers` y `SPEC-unit-sites`.
- `SPEC-industries-rest` y `SPEC-platform`: estado parcial, según lo que ya salió a producción.
- Están en producción sin spec: Oficinas, el botón Ingresar con la cápsula del menú y el Impacto glass del home. Hay que escribir `SPEC-offices`.
- `SPEC-nav`, `SPEC-home`, `SPEC-news`, `SPEC-capabilities` y `SPEC-industries-rest` tienen una sección «Cambios del 6 nov 2026» con lo publicado de #266 a #273.

## 4. Nova
- **Spec:** `benka-nova/SPEC-nova.md`. Las decisiones D12 (tres frentes en paralelo) y D13 (la intranet como canal) reemplazan a D10.
- **Código:** `BenkaDevelop/benka-nova`, con la base de conocimiento, el emparejamiento, el ruteo, la salud de la arquitectura y las rutinas.
- **Intranet (SharePoint):** `Comercial › Crecimiento › Nova`, con las subcarpetas `Bases` y `Reportes`.
  - URL: https://benkagroup.sharepoint.com/sites/Benka/Comercial/Crecimiento/Nova
  - driveId: `b!BA-tYjeNDkanGo_fpg9T7ssborIp49hAvygwpdjPHWs_7dY2_VjtSoBImFqmfIgT`
- **Tareas programadas:**
  - «Nova · Salud de la arquitectura (lunes)»: `trig_01G9u1Noo2EsXumEMX8uSUHc`, lunes 6:41 hora de Bogotá.
  - «Nova · Resumen diario a socios»: `trig_01GFGPeDTsEztszpDPNKr5gA`, de lunes a viernes a las 16:38.
  - **Conector:** las dos tienen Microsoft 365 desde el 6 nov 2026 (lo agregó Jhohan en claude.ai). Las sesiones no pueden agregar ni quitar conectores de una tarea: se hace en la tarea, en Edit › Advanced settings › Connectors.
  - Estas tareas se crearon desde una sesión y no aparecen en la lista «Tuyos» de claude.ai/code/routines; se abren con el enlace directo `claude.ai/code/routines/<id>`.
- **Red:** el entorno permite `benkagroup.co`. Los scripts de Node necesitan `NODE_USE_ENV_PROXY=1` (ya está en `npm run health`).
- **Tareas de Jhohan para destrabar:**
  - Comprar los 4 dominios de las unidades.
  - Crear la app en LinkedIn Developers (API de páginas).
  - Crear la app en Meta for Developers (Instagram para cuentas business).
  - Abrir la cuenta de HubSpot.
  - Confirmar los Instagram de Consulting, Media y Digital LAB.
  - Más adelante, entregar una cuenta de servicio de Firestore como secreto.

## 5. Enlaces
- **Consola del proyecto** (todo en uno): https://claude.ai/artifact/PHU8Cjw4dTYnYDbV7N4y4U
- Prototipo v3.7 (referencia histórica): https://claude.ai/artifact/HZfJpcmheqTCWVuEu19Vq4
- Figma con opciones de imagen IA para el home: «Benká · Imágenes IA para tarjetas del home».

## 6. Pendientes principales
1. **Fase 2 · Industrias:** cambiar 6 cifras de prensa por la fuente primaria (El Tiempo, Portafolio, Forbes, DPL News); fotos (las de R12–R15 son retratos repetidos; faltan fotos de operación); casos por validar (Univalle P-05, Robótica P-07, caso de Media); Oil & Gas sin caso; expertos de Media y Oil & Gas (solo Jhohan y José).
2. Comunicaciones debe abrir los enlaces de las cifras publicadas.
3. Fotos: copia liviana de las grupales RDM-684 a RDM-940 (P-20).
4. Specs: escribir `SPEC-offices`; aprobar `SPEC-careers` (R16) y `SPEC-unit-sites` (R17).
5. Credenciales de Helena y José (para sus insignias) y cargo de José («Managing Partner» en la biografía y «Partner» en la tarjeta).
6. Perspectivas: primer artículo de un socio.
7. Revisar el logo flotante que se cruza con las fotos de Oficinas en el home.
8. Cerrar los issues #190 a #194 en GitHub.
9. Ramas de trabajo ya publicadas que se pueden borrar: `feature/nav-industrias-glass`, `feature/home-tarjetas-capabilities`, `feature/fase-0-posicionamiento`, `feature/r12-r13-education-social`, `feature/r14-r15-media-oil`, `release/r12-r15-industrias`, `consola-preview*`.
