# SPEC · i18n (R6b) · Idiomas ES · EN · PT

Estado: **aprobada por Jhohan Axelrod el 5 nov 2026** · selector **en producción** (PR BenkaDevelop/benka-group#236 → qa, release #237) · traducciones al final del sitio v2 · Backlog P-40

## 1. Objetivo
Que todo benkagroup.co se pueda leer en español, inglés y portugués.
- El español sigue siendo la versión original.
- Las traducciones las hace IA y las revisa un agente de idiomas antes de la aprobación de Jhohan.

## 2. Decisiones (5 nov 2026, Jhohan Axelrod)
- **Traducción:** IA, con un agente de idiomas que revisa terminología, tono y consistencia antes de la aprobación final.
- **Direcciones por idioma:**
  - Español sin prefijo (`/holding`).
  - Inglés con `/en` (`/en/holding`).
  - Portugués con `/pt` (`/pt/holding`).
  - Cada página declara sus versiones con `hreflang` para Google.
- **Selector:** variante A. Globo + código de idioma, pequeño, al lado de "Contacto". Se abre con la misma pestaña azul glass del menú.
- **En celular:** el selector va visible en la barra, junto a la hamburguesa.
- **Menú hamburguesa:** aparece por debajo de 1280 px (antes 1160) para que el menú, el selector y el logo no se crucen.

## 3. Momentos

| # | Momento | Qué se ve | Estado |
|---|---|---|---|
| L1 | Selector | Globo + ES/EN/PT junto a Contacto. Panel azul glass con Español, English y Português; el idioma activo queda marcado. En celular, visible en la barra. **English y Português se ven con la marca "Pronto" y no se pueden elegir** hasta que existan las traducciones | En producción |
| L2 | Rutas por idioma | `/en/...` y `/pt/...` muestran la misma página traducida. Al cambiar de idioma, la página no cambia, solo el prefijo. El idioma elegido se recuerda | Pendiente |
| L3 | Textos traducidos | Todos los textos fijos del sitio salen de archivos por idioma (`es`, `en`, `pt`). Los nombres de industria se quedan en inglés en todos los idiomas | Pendiente |
| L4 | Revisión por agente de idiomas | Para cada página, un agente revisa la traducción: glosario de marca (Benká, Capabilities, Holding, Loyalty as a Service), tono ejecutivo, cifras y nombres propios intactos. Deja un informe por página | Pendiente |
| L5 | Aprobación por página | Jhohan aprueba cada página en EN y PT con capturas antes de publicarla. Las páginas sin aprobar redirigen a su versión en español | Pendiente |

## 4. Cuándo se traduce
Las traducciones (L2 a L5) van **al final**, cuando todas las páginas del sitio v2 estén montadas (después de Careers y antes de los sitios de unidad). Orden: Menú y footer → Home → Holding → Capabilities → Industries y cada industria → Noticias → Black Women Shaping Afrofutures → Trayectoria → Nosotros / socios → Careers.

## 5. Glosario (no se traduce)
Benká Group, Benká Consulting, Benká Media, Benká Digital LAB, Benká Social Venture, Capabilities, Holding, Loyalty as a Service, Retail Media Networks, nombres de industria (en inglés), nombres de personas y de medios.

## 6. Criterios de aceptación
- Ninguna página en EN o PT sale sin aprobación.
- Las cifras y los nombres son idénticos en los tres idiomas.
- `hreflang` correcto en las tres versiones; sin desborde a 390 px con textos más largos (portugués).
