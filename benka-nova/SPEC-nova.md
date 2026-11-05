# SPEC · nova · Superagente comercial de Benká Group

Estado: **aprobada por Jhohan Axelrod el 5 nov 2026** (§1 a §12, sección por sección). Construcción: al terminar el sitio (D10). Las preguntas abiertas de §13 se resuelven antes de crear las historias.
Arquitectura de referencia: https://claude.ai/artifact/6aL6zio6hzKbdnwhCoueRS (pestañas Arquitectura y Nova).
Mientras esta spec no esté aprobada, los cambios en benkagroup.co están suspendidos (decisión de Jhohan Axelrod, 5 nov 2026).

## 1. Objetivo
Nova es el agente comercial de Benká Group. Su trabajo es mantener viva la arquitectura del ecosistema y convertirla en negocio:
- Conecta los sitios, los LinkedIn y los Instagram de Benká Group y de sus cuatro unidades.
- Escucha e investiga para encontrar organizaciones, personas, cotizaciones y requerimientos que encajan con lo que Benká ofrece en industrias, capabilities y unidades.
- Crea conversaciones estratégicas que generan interés.
- Alimenta sola la base de leads.
- Entrega cada lead calificado al socio indicado.

## 2. Decisiones tomadas

| # | Decisión | Fecha | Quién |
|---|---|---|---|
| D1 | Nova corre en esquema **híbrido**. Las tareas programadas en la nube hacen el research, el emparejamiento y los reportes. Lo que entra (formulario, comentarios, mensajes) llega por eventos a una función en la nube. Una máquina local es opcional y solo para tareas asistidas | 5 nov 2026 | Jhohan Axelrod |
| D2 | La base de leads es **una mezcla**: HubSpot, Firestore y SharePoint, más las bases que Benká cargue, más lo que Nova construye explorando LinkedIn e Instagram. **Nova alimenta la base sola** (ver §6) | 5 nov 2026 | Jhohan Axelrod |
| D3 | La spec de Nova se escribe antes de cualquier otro cambio en el sitio | 5 nov 2026 | Jhohan Axelrod |
| D4 | Exploración de LinkedIn e Instagram **dentro de las reglas**: APIs oficiales y contenido público; la búsqueda de personas la hace un socio con Sales Navigator o un proveedor B2B y Nova importa el resultado (§5 R2 aprobada) | 5 nov 2026 | Jhohan Axelrod |
| D6 | Alcance §3 aprobado; ritmo §9 aprobado (7:00 research, 17:00 resumen, lunes salud) | 5 nov 2026 | Jhohan Axelrod |
| D7 | Mientras no haya líderes de unidad, **Jhohan recibe los leads de Media, Digital LAB y Social Venture** y los reasigna | 5 nov 2026 | Jhohan Axelrod |
| D8 | Reglas §5 R1 a R6 aprobadas | 5 nov 2026 | Jhohan Axelrod |
| D9 | Calificación §7: arranca con encaje 40, intención 25, autoridad 20, momento 15; los socios revisan los primeros 30 leads y con eso se fija el umbral para HubSpot | 5 nov 2026 | Jhohan Axelrod |
| D10 | **Nova se construye al final, cuando termine el desarrollo de todo el sitio** (R7b a R17). La spec se aprueba ahora; las historias se crean en GitHub al iniciar la construcción | 5 nov 2026 | Jhohan Axelrod |
| D11 | §1, §4, §11 y §12 aprobados; las metas numéricas se fijan con el primer mes de operación | 5 nov 2026 | Jhohan Axelrod |
| D5 | Capa de leads mixta del §6 **aprobada**: Firestore como memoria de Nova, HubSpot como pipeline de socios, SharePoint para bases y reportes | 5 nov 2026 | Jhohan Axelrod |

## 3. Alcance
**Dentro**
- Escuchar los canales propios:
  - formulario Conversemos del sitio;
  - comentarios y menciones en las páginas de LinkedIn de Group y de las unidades;
  - comentarios, menciones y mensajes recibidos en Instagram.
- Investigar con fuentes públicas: web, prensa, gremios, convocatorias y SECOP II.
- Explorar LinkedIn e Instagram para construir la base de prospectos, dentro de las reglas de §5.
- Importar bases que cargue el equipo (Excel o CSV en SharePoint) y deduplicarlas.
- Emparejar cada necesidad con capability, industria, unidad, caso publicado y socio.
- Calificar, registrar y asignar cada lead.
- Redactar borradores de mensajes, respuestas y posts para los socios.
- Mantener la arquitectura: revisar la salud de sitios, enlaces y perfiles, y la coherencia entre el sitio y las redes.

**Fuera (por ahora)**
- Enviar mensajes, comentarios o posts sin la aprobación de un socio.
- Operar las cuentas personales de LinkedIn de los socios.
- Extraer datos con robots o hacer acciones masivas que violen los términos de LinkedIn o Meta.
- Llamadas, cotizaciones formales y contratos.

## 4. Actores
- **Socios** (dueños de los leads):
  - Jhohan Axelrod: Loyalty as a Service, Cali.
  - Helena Valencia: Financial Inclusion, Bogotá.
  - José Martínez: Transformación y Estrategia, Cartagena.
- **Líderes de unidad** (Media, Digital LAB, Social Venture): por definir.
- **Comunicaciones:** confirma canales, tono y calendario de posts.
- **Nova:** agente; no tiene cuentas personales.

## 5. Reglas
- **R1 · El socio envía, Nova prepara.** Todo lo que sale hacia un tercero pasa por la aprobación del socio dueño del lead.
- **R2 · Solo canales permitidos.**
  - Cuentas propias: APIs oficiales de LinkedIn (páginas) e Instagram (cuentas business).
  - Exploración de LinkedIn e Instagram: solo contenido público y búsquedas que permiten las APIs. Para la búsqueda de personas, un socio puede usar herramientas licenciadas como Sales Navigator o un proveedor B2B; Nova importa el resultado.
  - Nada de robots que extraigan perfiles, ni mensajes automáticos desde cuentas personales.
- **R3 · Nunca inventa.** Cada lead guarda el enlace de su evidencia. Nova solo ofrece lo publicado en el sitio y solo cita casos validados.
- **R4 · Datos personales.**
  - Tratamiento según la Ley 1581 de 2012 y la política de privacidad del sitio.
  - Cada registro guarda la base legal y la fuente.
  - Se borra a solicitud.
- **R5 · Trazabilidad.** Cada acción de Nova queda en la bitácora con fecha, fuente, entrada y resultado.
- **R6 · Límites.** Nova respeta los límites de uso de cada plataforma y se detiene ante un error de acceso.

## 6. Datos: capa de leads mixta (D2)

| Pieza | Rol | Quién escribe |
|---|---|---|
| **Firestore · memoria de Nova** | Registro maestro de organizaciones, personas, señales y leads, con deduplicación y bitácora. Ya está en el stack del sitio | Nova (automático) |
| **HubSpot CRM** | Pipeline comercial de los socios: el socio dueño del lead, etapas, tareas y correo. Recibe solo los leads que superan el umbral | Nova crea y actualiza; el socio mueve las etapas |
| **SharePoint (Microsoft 365)** | Carpeta de bases cargadas por el equipo (Excel o CSV) y reportes semanales | Equipo carga; Nova importa y publica reportes |
| **Exploración de Nova** | Prospectos que Nova encuentra en LinkedIn, Instagram, web y SECOP II | Nova (automático, con evidencia) |

**Sincronización**
- Firestore es la fuente de verdad del contacto y la evidencia. HubSpot lo es del estado comercial.
- Cuando un socio cambia una etapa en HubSpot, Nova la trae de vuelta a Firestore.

**Deduplicación:** dominio de la empresa, correo y URL de perfil.

**Ficha del lead**
- `id`, `fecha`, `fuente` (formulario · LinkedIn · Instagram · SECOP · web · base cargada)
- `evidencia` (URL)
- `organizacion` (nombre, dominio, sector, ciudad, país, tamaño)
- `persona` (nombre, cargo, canal)
- `necesidad`
- `emparejamiento` (industria, capability, unidad, caso)
- `puntaje` (encaje, intención, autoridad, momento, total)
- `socio`
- `estado` (nuevo → contactado → reunión → propuesta → ganado / perdido)
- `proximo_paso`
- `consentimiento` (base legal, fecha)

## 7. Flujo
1. **Señal.** Llega por un evento o la encuentra una tarea programada.
2. **Escuchar.** Nova clasifica la señal (oportunidad, consulta, ruido) y la guarda.
3. **Investigar.** Completa el contexto con fuentes públicas.
4. **Emparejar.** Cruza la señal con la base de conocimiento, que se genera desde `src/data` del sitio y las specs.
5. **Calificar.** Encaje 40, intención 25, autoridad 20, momento 15 (D9). Los socios revisan los primeros 30 leads y con eso se fija el umbral para HubSpot.
6. **Registrar.** El lead entra a Firestore. Si supera el umbral, también se crea en HubSpot.
7. **Asignar.** Según la tabla de ruteo (§8).
8. **Conversar.** Nova deja un borrador en el Outlook del socio, o un borrador de post o de respuesta.
9. **Aprender.** Nova registra el resultado del socio y ajusta pesos y fuentes.

**Mantener la arquitectura (semanal)**
- Los sitios responden.
- Los enlaces del footer y de las unidades funcionan.
- Las bios y los enlaces de cada perfil apuntan al dominio correcto.
- Las noticias del sitio también están en las redes.

## 8. Ruteo a socios (por validar con cada socio)

| Socio | Recibe |
|---|---|
| Jhohan Axelrod | LaaS, retail, consumo masivo, commerce media y leads sin dueño claro |
| Helena Valencia | Servicios financieros e inclusión financiera |
| José Martínez | Transformación corporativa, estrategia y Transformation Office |
| Líderes de unidad | Leads propios de Media, Digital LAB y Social Venture. Mientras no estén definidos, los recibe Jhohan (D7) |

## 9. Ritmo

| Cuándo | Qué |
|---|---|
| Al llegar un evento | Clasificar y avisar al socio si es urgente |
| Diario 7:00 | Research, emparejamiento, calificación y registro |
| Diario 17:00 | Resumen por socio con borradores |
| Lunes | Salud de la arquitectura y estado del pipeline (reporte en SharePoint) |
| Cada release del sitio | Regenerar la base de conocimiento |

## 10. Historias (se crean como issues cuando arranque la construcción de Nova, al terminar el sitio · D10)

| ID | Historia | Fase |
|---|---|---|
| NOVA-01 | Como Benká quiero un orquestador híbrido (tareas programadas + eventos) con bitácora, para que Nova trabaje sin una máquina siempre prendida | 1 |
| NOVA-02 | Como Nova necesito una base de conocimiento generada desde el sitio y las specs, para emparejar sin inventar | 1 |
| NOVA-03 | Como socio quiero que cada solicitud del formulario se convierta en lead calificado | 1 |
| NOVA-04 | Como socio quiero que los comentarios y menciones de las páginas de LinkedIn lleguen como señales | 1 |
| NOVA-05 | Como socio quiero que los comentarios, menciones y mensajes de Instagram lleguen como señales | 1 |
| NOVA-06 | Como Jhohan quiero un reporte semanal de salud de sitios, enlaces y perfiles | 1 |
| NOVA-14 | Como socio quiero una capa de leads mixta (Firestore + HubSpot + SharePoint) que Nova alimente sola y sin duplicados | 1 |
| NOVA-15 | Como socio quiero recibir solo los leads de mi práctica | 1 |
| NOVA-17 | Como equipo quiero cargar bases propias (Excel o CSV) y que Nova las importe y deduplique | 1 |
| NOVA-07 | Como socio quiero que Nova investigue cada señal con fuentes públicas y evidencia | 2 |
| NOVA-08 | Como socio quiero oportunidades de SECOP II filtradas por nuestras capabilities | 2 |
| NOVA-09 | Como socio quiero ver la capability, unidad y caso sugeridos con la razón del cruce | 2 |
| NOVA-10 | Como socio quiero contexto de LinkedIn para preparar mis conversaciones | 2 |
| NOVA-11 | Como socio quiero un puntaje y prioridad por lead | 2 |
| NOVA-18 | Como Benká quiero que Nova explore LinkedIn e Instagram dentro de las reglas y sume prospectos con evidencia | 2 |
| NOVA-12 | Como socio quiero borradores de mensajes en mi Outlook | 3 |
| NOVA-13 | Como Comunicaciones quiero borradores de posts basados en lo que Nova escucha | 3 |
| NOVA-16 | Como Jhohan quiero un panel con métricas del pipeline y de Nova | 3 |

## 11. Criterios de aceptación generales
- El 100% de los leads tiene evidencia y fuente.
- Ningún mensaje sale sin aprobación (verificable en la bitácora).
- No hay duplicados por dominio, correo o URL de perfil.
- El resumen diario llega a cada socio antes de las 17:30.
- Si una fuente falla, Nova sigue con las demás y lo reporta.

## 12. Métricas (metas por definir con el primer mes de operación · D11)
- Leads calificados por semana.
- Tiempo de primera respuesta.
- Conversación → reunión.
- Reunión → propuesta.
- Porcentaje de leads con evidencia.
- Salud de la arquitectura.

## 13. Preguntas abiertas
1. ¿Quiénes serán los líderes de Media, Digital LAB y Social Venture? (mientras tanto, Jhohan · D7)
2. ¿Cuáles son los Instagram y los dominios de Consulting, Media y Digital LAB?
3. ¿Aprobamos herramientas con costo: Sales Navigator, proveedor de datos B2B y HubSpot de pago si hace falta?
4. ~~¿Qué umbral pasa a HubSpot?~~ Se fija tras revisar los primeros 30 leads (D9).
5. ¿Quién administra las apps de LinkedIn y Meta para habilitar las APIs?
