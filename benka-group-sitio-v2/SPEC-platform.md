# SPEC · platform (transversal) · SEO, analítica, 404, imágenes y fuentes

Estado: **borrador 1 · por aprobar** (5 nov 2026) · Corre en paralelo: una historia por release · Pendientes de backlog P-31, P-33 a P-36

## 1. Objetivo
Que el sitio sea rápido, medible y encontrable, y que cada ruta profunda responda bien al recargar.

## 2. Punto de partida
- Assets del sitio: ~250 MB en imágenes (P-34). Ya se optimizaron las fotos de oficinas (28 MB → 1,8 MB).
- Sin sitemap ni metadatos para las rutas nuevas (P-35); sin GA4 (P-35); sin página 404 (P-36).
- Preload de CSS obsoleto en `index.html` (P-33).
- Typekit (Atyp) solo autorizado para benkagroup.co (P-31).

## 3. Historias
| # | Historia | Backlog |
|---|---|---|
| PL-1 | Optimizar imágenes: WebP a 2× del tamaño mostrado y carga diferida; meta propuesta: < 20 MB de assets | P-34 |
| PL-2 | Sitemap.xml y robots.txt con todas las rutas publicadas; metadatos (title, description, Open Graph) por página | P-35 |
| PL-3 | GA4 con banner de consentimiento y eventos de CTA (Contacto, Ver más, unidades ↗) | P-35 |
| PL-4 | Página 404 con la marca y reescritura SPA para rutas profundas en Hostinger | P-36 |
| PL-5 | Quitar el preload de CSS obsoleto | P-33 |
| PL-6 | Autorizar Typekit en cada dominio nuevo (con SPEC-unit-sites) | P-31 |

## 4. Criterios de aceptación
- Meta propuesta: Lighthouse ≥ 90 en rendimiento y SEO en Home y Agroindustria (escritorio).
- Recargar cualquier ruta publicada no da error.
- GA4 no registra nada antes del consentimiento.

## 5. Preguntas abiertas
1. ¿Cuenta de GA4 existente o nueva?
2. ¿Texto del banner de consentimiento (ligado a la política de privacidad)?
