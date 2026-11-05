# Backlog de pendientes · Benká Group sitio v2

Temas que deben quedar **definidos en el spec** antes de que la historia que los usa pase a producción.
Cada ítem tiene dueño sugerido y la historia que bloquea. Al resolverse, se actualiza el spec del módulo y se cierra aquí.

Regla mientras tanto: **nada marcado "Por validar" sale a producción sin una decisión registrada en este backlog** (validar, ocultar o publicar con etiqueta).

## 1. Política de contenido "Por validar"

| # | Pendiente | Decide | Bloquea |
|---|---|---|---|
| P-01 | Definir si las cifras y textos sin validar se ocultan en producción o salen con la etiqueta "Por validar" | Jhohan + Comunicaciones | Todas las historias con DraftChip |
| P-02 | Definir quién valida (Comunicaciones, socio del caso, cliente) y en qué plazo | Jhohan | P-03 a P-12 |

## 2. Casos de éxito sin validar

| # | Caso | Industria | Qué falta |
|---|---|---|---|
| P-03 | Transformación holística en empresas familiares | Consumo masivo | Cifras de resultado y permiso del cliente |
| P-04 | Profesionalización de una agroindustria familiar (banner con ingenio del Valle) | Agroindustria | Cifras de resultado, permiso y foto real o aprobación de la imagen IA |
| P-05 | TransformaMiPyMEs (Univalle) | Educación | Cifras y aval de la Universidad del Valle |
| P-06 | Ecosistema de lealtad para aumentar la principalidad | Servicios financieros | Cifras y permiso |
| P-07 | Robótica para jóvenes en Quibdó | Sector social | Cifras de impacto |

Casos validados (pueden salir): Nuevo modelo comercial (18% / 12%), Campañas de consumo (3,2X / +25 ROAS), Plataforma ATL con IA (US$90K / 72%), Formación en tecnología (40%).

## 3. Cifras de mercado y KPIs

| # | Pendiente | Dónde | Nota |
|---|---|---|---|
| P-08 | KPIs ilustrativos de agro (+18% productividad, −12% logística, −28% merma, 100% trazabilidad) | Agro › Impacto | Son referencia sectorial, no de clientes. Validar o retirar |
| P-09 | Exportaciones 2024 (US$11.492 M) | Agro › DataPanel | Estimada a partir del +33,2% reportado; reemplazar por cifra oficial |
| P-10 | "Hasta 64% de la fruta se pierde" | Eslabón Cosecha y acopio | Estimación de un seminario, no dato oficial |
| P-11 | PIB agro IV-2025: −0,4% vs −0,3% | Agro › DataPanel | Fuentes no coinciden; usar el boletín DANE definitivo |
| P-12 | Adopción tecnológica del agro: 15% vs 30% | Eslabón Cultivo | Fuentes no comparables |
| P-13 | Revisar las 12 cifras de retos y las de los 5 eslabones contra fuentes primarias (DANE, DNP, gremios) | Agro | Hoy vienen de prensa económica |
| P-14 | ~~Presencia regional~~ **Resuelto 5 nov 2026:** los 5 países (Colombia, Ecuador, Perú, Chile, Argentina) se publican como operación activa | Holding | Decisión de Jhohan |
| P-15 | Indicadores del grupo (5-10%, 8+, 3X, 25+) y "+100 proyectos" | Home, Holding, Consulting | Confirmar fuente interna |

## 4. Contenido y medios

| # | Pendiente | Dueño | Bloquea |
|---|---|---|---|
| P-16 | Fotos y videos de Black Women Shaping Afro Future (Drive de Comunicaciones), priorizando a Helena | Comunicaciones | news · historia BWS |
| P-17 | Cita textual de Helena Valencia del lanzamiento y fecha/lugar del evento | Helena / Comunicaciones | news · historia BWS |
| P-18 | Textos de las noticias borrador (Voz de Helena, TransformaMiPyMEs, Robótica Quibdó, Becas Sueños de Paz) | Comunicaciones | news |
| P-19 | Nombres de las personas en las fotos del equipo (personas A–D) y autorización de uso de imagen | Talento | Careers, Home |
| P-20 | Curación de fotos: revisadas 24 de ~940 (archivos > 5 MB no se pudieron leer) | Comunicaciones | Todas |
| P-21 | 24 espacios de foto/video de stock con dirección de arte; habilitar bancos (images.unsplash.com, images.pexels.com, videos.pexels.com, cdn.pixabay.com) o comprar licencias | TI / Comunicaciones | industries-rest |
| P-22 | Video de la fábrica tecnológica para Digital (loop 10–15 s) | Media | Industria Digital |
| P-23 | ~~Imágenes IA~~ **Resuelto 5 nov 2026:** Jhohan aprueba las 18 imágenes IA para producción; se reemplazan cuando haya fotos reales | Jhohan | — |
| P-40 | Selector de idioma ES · EN · PT para todo el sitio: quién traduce y aprueba EN y PT, y si las URL cambian por idioma | Jhohan | Release R6b (i18n) |
| P-39 | Enlace de la nota "Becario Sueños de Paz" (Fundación Lumni); en Firestore está vacío | Jhohan / Comunicaciones | news |
| P-24 | Retrato de Helena sin líneas de marca (hoy el de perfil trae líneas) | Comunicaciones | news · BWS |

## 5. Decisiones de producto

| # | Pendiente | Decide |
|---|---|---|
| P-25 | Dominios propios de las unidades (benkaconsulting.co, benkamedia.com, benkadigitallab.com, benkasocialventure.org). Mientras tanto los logos enlazan a las redes. **Avisar a Jhohan para comprarlos antes de activar los sitios de unidad en producción** | Jhohan + Helena |
| P-26 | Rediseño completo de Careers | Jhohan |
| P-27 | Quién aprueba los PR de `qa` → `main` | Jhohan |
| P-38 | El flujo de PR publica por FTP directo en producción (no hay QA). Jhohan decidió mantenerlo (5 nov 2026); cada PR se abre solo con diseño aprobado en el preview | Jhohan |
| P-28 | Expertos por industria (hoy Agro: Jhohan, Helena, José; resto por definir) | Jhohan |
| P-29 | ~~Unidad líder de LaaS~~ **Resuelto 5 nov 2026:** Benká Media | Jhohan |
| P-30 | Orden de las industrias R8–R15 (sugerido: Consumo masivo, Retail, Servicios financieros, Digital, Educación, Sector social, Medios y telecom, Oil & Gas) | Jhohan |

## 6. Técnico

| # | Pendiente | Módulo |
|---|---|---|
| P-31 | Fuente Atyp (Typekit) por dominio | platform |
| P-32 | URL de LinkedIn de Social Venture truncada en el footer | nav |
| P-33 | Preload de CSS obsoleto en index.html | platform |
| P-34 | Optimización de imágenes (~250 MB de assets) | platform |
| P-35 | Sitemap, metadatos y GA4 para las rutas nuevas | platform |
| P-36 | Página 404 | platform |
| P-37 | Conector de Google Drive caído en las sesiones de Claude (error de autorización) | TI |
