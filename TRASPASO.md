# Traspaso · Benká Group sitio v2 y Nova

Escrito el 6 nov 2026 al cerrar la sesión de Claude `session_01WEQvrcMdnj1MpVZe5igTBG`, para seguir el trabajo desde un proyecto. Léelo completo antes de tocar algo.

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
  - Desde el 6 nov se aprueba **por página completa**, con un HTML que muestre capturas de escritorio y celular, momentos, cifras con fuente y pendientes.
- **Preguntas:** siempre de opción múltiple, con la recomendación marcada.
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
- **Idioma:** los nombres de industria van en inglés.
- **Dominios:** avisar a Jhohan antes de activar los sitios de unidad, para que compre los dominios (P-25).

## 3. Estado al 6 nov 2026
**En producción (hasta el PR #265):**
- Releases R1 a R7a.
- Oficinas por ciudad (`/offices/:id`).
- **R7b:** los 5 eslabones de Agroindustria.
- **R8 a R11:** Consumer Packaged Goods, Retail, Financial Services y Digital (#262 y #263).
- **Plataforma:** página 404, `.htaccess`, sitemap con 28 URL, títulos y descripciones por página, imágenes en WebP con el build de 233 a 75 MB (#264 y #265).

**En construcción en sesiones paralelas** (cada una sube su rama y deja un resumen; ninguna abre PR):

| Release | Sesión | Rama |
|---|---|---|
| R12 Education | `session_01WEQvrbhiVLyRYDydVN3whG` | `feature/r12-education` |
| R13 Social Sector | `session_01WEQvrb1QqZ8B75qJbeaLYm` | `feature/r13-social-sector` |
| R14 Media & Telecommunications | `session_01WEQvreWdaK4vXfLAMRUgDQ` | `feature/r14-media-telecommunications` |
| R15 Oil & Gas | `session_01WEQvrdBMBo3ix1dvyuMZGd` | `feature/r15-oil-gas` |

- Revisa cada sesión con `get_session` o `list_events` y cada rama con `git ls-remote`.
- Para publicar:
  1. Construye cada rama.
  2. Toma capturas de escritorio y de iPhone 13.
  3. Arma el HTML de aprobación.
  4. Con la aprobación, integra en una rama `release/…`. Los conflictos en `src/router/routes.tsx` y en `src/data/industries-hub.ts` se resuelven conservando las líneas de ambas ramas; en `industries-hub.ts` hay que quitar las filas duplicadas.
- Los carruseles «Otras industrias» leen `hubIndustries`, así que una industria aparece como en vivo en cuanto su `live` es `true`.

**Specs:**
- Aprobados: `SPEC-nova` (D1 a D13).
- Borradores por aprobar: `SPEC-careers` y `SPEC-unit-sites`.
- `SPEC-industries-rest` y `SPEC-platform`: estado parcial, según lo que ya salió a producción.
- Están en producción sin spec: Oficinas, el botón Ingresar con la cápsula del menú y el Impacto glass del home. Hay que escribir o actualizar `SPEC-offices`, `SPEC-nav` y `SPEC-home`.

## 4. Nova
- **Spec:** `benka-nova/SPEC-nova.md`. Las decisiones D12 (tres frentes en paralelo) y D13 (la intranet como canal) reemplazan a D10.
- **Código:** `BenkaDevelop/benka-nova`, con la base de conocimiento, el emparejamiento, el ruteo, la salud de la arquitectura y las rutinas.
- **Intranet (SharePoint):** `Comercial › Crecimiento › Nova`, con las subcarpetas `Bases` y `Reportes`.
  - URL: https://benkagroup.sharepoint.com/sites/Benka/Comercial/Crecimiento/Nova
  - driveId: `b!BA-tYjeNDkanGo_fpg9T7ssborIp49hAvygwpdjPHWs_7dY2_VjtSoBImFqmfIgT`
- **Tareas programadas:**
  - «Nova · Salud de la arquitectura (lunes)»: `trig_01G9u1Noo2EsXumEMX8uSUHc`, lunes 6:41 hora de Bogotá.
  - «Nova · Resumen diario a socios»: `trig_01GFGPeDTsEztszpDPNKr5gA`, de lunes a viernes a las 16:38.
  - **Pendiente:** a ninguna de las dos se le pudo agregar el conector de Microsoft 365 desde la sesión. Hay que agregarlo en claude.ai, en tareas programadas.
- **Red:** el entorno permite `benkagroup.co`. Los scripts de Node necesitan `NODE_USE_ENV_PROXY=1` (ya está en `npm run health`).
- **Tareas de Jhohan para destrabar:**
  - Comprar los 4 dominios de las unidades.
  - Crear la app en LinkedIn Developers (API de páginas).
  - Crear la app en Meta for Developers (Instagram para cuentas business).
  - Abrir la cuenta de HubSpot.
  - Confirmar los Instagram de Consulting, Media y Digital LAB.
  - Más adelante, entregar una cuenta de servicio de Firestore como secreto.

## 5. Enlaces
- Arquitectura v4 (diagrama interactivo, Nova, componentes y experiencia): https://claude.ai/artifact/6aL6zio6hzKbdnwhCoueRS
- Tablero de estado SDD: https://claude.ai/artifact/L3tJTmvur8CC3H84zSDE3k
- Aprobación de industrias (R7b a R11, ya publicadas): https://claude.ai/artifact/YZRThKAFYfxXTaN78qyFAz
- Vista navegable del prototipo v3.7: https://claude.ai/artifact/HZfJpcmheqTCWVuEu19Vq4

## 6. Pendientes principales
1. Aprobar y publicar R12 a R15 cuando sus sesiones terminen.
2. Comunicaciones debe abrir los enlaces de las cifras publicadas (se publicaron con fuente, para revisión posterior).
3. Fotos: copia liviana de las fotos grupales RDM-684 a RDM-940 (P-20). Varias secciones de industria quedaron sin foto.
4. Specs: `SPEC-offices`; actualizar `SPEC-nav` (Ingresar y cápsula) y `SPEC-home` (Impacto glass); aprobar `SPEC-careers` (R16) y `SPEC-unit-sites` (R17).
5. Revisar el logo flotante (`floating-logo`) que se cruza con las fotos de Oficinas en el home.
6. Cerrar los issues #190 a #194 en GitHub (la sesión no tuvo permiso).
7. Actualizar el HTML de arquitectura y el tablero de estado con lo publicado el 6 nov.
