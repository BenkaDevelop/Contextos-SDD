# Spec: capabilities · Página /capabilities

Módulo `capabilities` · Release R3 (junto con `holding`) · Épica BenkaDevelop/benka-group#173 · Historias #174, #175, #176
Depende de: `ui-base` (R1), `nav` (R2)
Estado: **borrador para aprobación**

## Objetivo

Mostrar "lo que sabemos hacer": 22 prácticas derivadas de las industrias en las que trabaja Benká, cada una con la compañía del holding que la lidera y las industrias donde más se aplica. Se enciende en el menú como **Capabilities** con un desplegable de 3 columnas en orden alfabético.

Éxito: /capabilities en producción igual al prototipo aprobado (v3.7) y cada opción del desplegable lleva a su tarjeta.

## Alcance

| Historia | Qué se publica |
|---|---|
| #174 Datos | 22 prácticas en orden alfabético (Transformación corporativa y Transformation Office unificadas); unidad líder e industrias por práctica |
| #175 Página | Hero con foto y 4 grupos (Estrategia y transformación, Comercial/marca/lealtad, Digital/datos/IA, Impacto); filtros por grupo; tarjeta con resultados, industrias y logo de la unidad líder; CTA |
| #176 Menú | Capabilities en el menú con desplegable glass de 3 columnas ordenado por columnas; cada opción baja a su tarjeta |

## Supuestos

1. Las industrias de cada tarjeta se muestran como etiquetas **sin enlace** mientras no existan las páginas de industria (R6+); se vuelven enlaces al publicarlas.
2. Loyalty as a Service queda liderada por Media (P-29), salvo que se decida otra cosa.
3. Sin cifras en este módulo: no hay nada "Por validar".

## Estructura

```
src/data/practices.ts               → 22 prácticas + grupos
src/pages/practices/Practices.tsx + .scss
src/data/navigation.ts              → Capabilities enabled + items (3 columnas)
src/components/header/*             → soporte de desplegable de 3 columnas y salto a ancla
```

## Verificación

- Build y lint en verde; revisión en 1440, 1100 y 390 px; el desplegable no se sale de la pantalla en 1280 px.
- Preview HTML aprobado por Jhohan antes de abrir el PR.
- Cada una de las 22 opciones del menú baja a su tarjeta.

## Límites

- **Siempre:** orden alfabético; rama desde `main`.
- **Preguntar antes:** agregar o quitar prácticas.
- **Nunca:** enlazar industrias que aún no tienen página en producción.

## Criterios de éxito

1. /capabilities en producción con 22 prácticas y filtros.
2. Desplegable de 3 columnas en orden alfabético con salto a cada tarjeta.

## Preguntas abiertas

1. **P-29:** ¿Loyalty as a Service la lidera Media o Consulting?
