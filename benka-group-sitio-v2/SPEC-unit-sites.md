# SPEC · unit-sites (R17+) · Sitios de las 4 unidades

Estado: **borrador 1 · por aprobar** (5 nov 2026) · Releases R17a a R17d, un sitio por release · Bloqueado por dominios (P-25: avisar a Jhohan para comprarlos) · Referencia: prototipo v3.7 (`/sites/:unidad`)

## 1. Objetivo
Darle a cada unidad su propio sitio y dominio, con su marca y su estructura, conectado al Grupo: comparte header y footer (con los colores y el logo de la unidad), enlaza a las industrias de benkagroup.co y alimenta a Nova (SPEC-nova).

## 2. Punto de partida
- **Producción:** no existen. Los logos de unidad enlazan a LinkedIn o Instagram (`src/data/units-brand.ts`).
- **Prototipo:** los 4 sitios simulados en /sites/:unidad.
- **Dominios propuestos (P-25, por confirmar):** benkaconsulting.co, benkamedia.com, benkadigitallab.com, benkasocialventure.org.

## 3. Momentos por sitio (prototipo)
| Sitio | Estilo | Momentos en el prototipo |
|---|---|---|
| Benká Consulting | Firma estratégica editorial, paleta beige, referencia McKinsey | Hero editorial serif · Métricas · Capacidades (8) · Industrias ↗ Group · Casos · Enfoque · Insights · Nosotros · Footer |
| Benká Media | Agencia creativa: tipografía grande, negro y verde (#D8EF4D) | Hero tipográfico + reel · Marquee de servicios · Trabajo · Servicios · Commerce Media & LaaS · Estudio |
| Benká Digital LAB | Inmersivo oscuro con video de fábrica | Hero con video · Build · Scale · Operate · Capacidades · Aceleradores + caso · Stack |
| Benká Social Venture | Organización de impacto, morado (#3C096C) | Hero de misión · Impacto · Programas · Historias reales · ODS · Súmate |

## 4. Arquitectura técnica (propuesta)
- Un repositorio o un monorepo con un build por dominio; despliegue igual al actual (GitHub Actions → hosting) o un hosting por dominio.
- Componentes compartidos: SiteHeader y SiteFooter (marca de la unidad), Arw, glass, UnitLogo.
- Typekit autorizado por dominio (P-31); sitemap y GA4 por dominio (SPEC-platform).
- Al publicar cada sitio, `units-brand.ts` cambia el enlace del logo de la red social al dominio.

## 5. Criterios de aceptación
- Cada sitio responde en su dominio con HTTPS y su 404.
- Los enlaces cruzados (Group ↔ unidad) funcionan.
- Ninguna cifra sin fuente; ningún texto sin aprobación.

## 6. Preguntas abiertas
1. ¿Se compran los 4 dominios propuestos? (P-25)
2. ¿Un repositorio por sitio o un monorepo?
3. ¿Hosting en Hostinger para los 4?
4. ¿Responsable de contenido por unidad?
