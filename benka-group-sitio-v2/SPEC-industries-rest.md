# SPEC · industries-rest (R8–R15) · Las otras 8 industrias

Estado: **borrador 1 · por aprobar** (5 nov 2026) · Releases R8 a R15, una industria por release · Modelo: SPEC-industry-agro (R7a en producción) · Referencia de diseño: prototipo v3.7 (`src/pages/industry-detail/*`)

## 1. Objetivo
Publicar las 8 industrias que faltan con el mismo nivel de Agroindustria, cada una con una estructura propia (un mundo por sector), y volver clicable su fila en el hub /industries.

## 2. Punto de partida
- **Producción:** /industries lista las 9 industrias; solo Agro-industry es clicable. El carrusel "Otras industrias" de Agro muestra las 8 con «Pronto».
- **Prototipo:** las 8 páginas existen con imágenes IA (aprobadas para producción, P-23) y bloques del catálogo de componentes. Los casos y cifras no están validados (P-03, P-05, P-06, P-07, P-15).

## 3. Orden propuesto (P-30, por confirmar)
| Release | Industria | Ruta |
|---|---|---|
| R8 | Consumo masivo | /industries/consumer-packaged-goods |
| R9 | Retail | /industries/retail |
| R10 | Servicios financieros | /industries/financial-services |
| R11 | Digital | /industries/digital |
| R12 | Educación | /industries/education |
| R13 | Sector social | /industries/social-sector |
| R14 | Medios y telecom | /industries/media-telecommunications |
| R15 | Oil & Gas | /industries/oil-gas |

## 4. Estructura común (heredada de Agro)
Toda industria tiene: Hero (glass, pantalla completa) · bloque propio del sector · Retos · ¿Cómo te acompañamos? (con unidad líder) · Caso · Expertos · Otras industrias (carrusel azul noche) · Cierre azul. Cada una se aprueba **momento por momento** antes de su PR.

## 5. Bloque propio de cada industria (prototipo)
| Industria | Momentos en el prototipo | Pendiente para aprobar |
|---|---|---|
| Consumo masivo | Hero viñedo · Quote · 6 palancas · Casos · Mosaico · Capacidades · Expertos | Caso P-03 sin cifras ni permiso · fotos de góndola y planta (P-21) |
| Retail | Hero pasillo · Mapa de tienda con puntos · Casos · Cifras de RMN y lealtad · Capacidades · Expertos | Cifras con fuente |
| Servicios financieros | Hero centro financiero · Embudo del cliente · Retos · Capacidades · Casos · Expertos | Caso P-06 sin cifras ni permiso · foto de pago móvil |
| Digital | Hero con video de fábrica · 5 capas tecnológicas · Del piloto a escala · Casos · Capacidades · Expertos | Video P-22 · hoy imagen fija |
| Educación | Hero Univalle · Ruta del estudiante · Historias reales · Retos · Capacidades · Casos · Expertos | Caso P-05 (aval de Univalle) |
| Sector social | Hero Quibdó · Cifras · Historias · Journey de impacto · Capacidades · Casos · Expertos | Caso P-07 sin cifras · foto de taller comunitario |
| Medios y telecom | Hero nocturno · Embudo de audiencia · Mosaico · Casos · Capacidades · Expertos | 4 fotos de stock (P-21) |
| Oil & Gas | Hero refinería de noche · Áreas up/mid/downstream y comunidades · Palancas · Retos · Casos (vacío) · Expertos | Sin caso · 4 fotos de stock |

## 6. Decisiones heredadas
- Regla de color permanente y glass del menú (SPEC-ui-base, SPEC-nav).
- Imágenes IA aprobadas (P-23) combinadas con fotos reales del equipo; sin repetir fotos entre industrias.
- Cifras de mercado solo con fuente visible; casos sin cifras hasta validarlas (P-01).
- Expertos por industria (P-28) por definir; mientras tanto, los socios de la práctica relacionada.

## 7. Criterios de aceptación
- Las mismas de SPEC-industry-agro §6, por cada industria.
- La fila de la industria en el hub y su tarjeta en "Otras industrias" se vuelven clicables al publicar.
- Ninguna industria enlaza a otra que no exista (siguen con «Pronto»).

## 8. Preguntas abiertas
1. ¿Se confirma el orden de P-30?
2. ¿Expertos de cada industria (P-28)?
3. ¿Casos: se publican cualitativos o se esperan las cifras validadas?
