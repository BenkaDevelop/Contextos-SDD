# SPEC · careers (R16) · Careers

Estado: **borrador 1 · por aprobar** (5 nov 2026) · Release R16 · Rediseño pendiente de diseño (P-26) · Referencia: prototipo v3.7 (pantalla Careers)

## 1. Objetivo
Crear /careers como la página de talento de Benká: por qué trabajar aquí, cómo es ser consultor y cómo es el proceso de selección. Las tarjetas "Únete al equipo" del home pasan de bajar a "Transforma tu carrera" a llevar a sus anclas en /careers.

## 2. Punto de partida
- **Producción:** no existe /careers. El menú tiene Careers con desplegable; el home tiene "Únete al equipo" (3 tarjetas con Ver más) y "Transformemos juntos tu carrera" (perfiles: estudiantes y voluntarios, perfiles junior, profesionales con experiencia, equipo senior y ejecutivo).
- **Prototipo:** secciones "Tu carrera en Benká", "Ser un consultor en Benká" y "Nuestro proceso de selección".

## 3. Momentos (por diseñar y aprobar uno por uno)
| # | Momento | Qué se ve en el prototipo | Pendiente |
|---|---|---|---|
| C1 | Hero | Foto del equipo trabajando y titular de talento | Foto real (RDM) y texto |
| C2 | Tu carrera en Benká (#tu-carrera) | Perfiles por etapa de carrera (los 4 del home) | Textos por perfil |
| C3 | Ser un consultor en Benká (#ser-consultor) | Día a día, aprendizaje y prácticas | Textos y fotos (P-19 nombres y autorización) |
| C4 | Nuestro proceso de selección (#proceso) | Etapas del proceso | Etapas reales y tiempos |
| C5 | Vacantes | No existe en el prototipo | ¿Lista propia, LinkedIn Jobs o correo? |
| C6 | Cierre | Banda azul con contacto | — |

## 4. Decisiones
- Se construye después de las industrias (ROADMAP).
- Fotos: solo reales del equipo, sin repetir las ya usadas en Agro y Home.

## 5. Criterios de aceptación
- Las 3 tarjetas del home llevan a #tu-carrera, #ser-consultor y #proceso.
- El desplegable Careers del menú lleva a las mismas anclas.
- Sin desborde a 390 px; respeta `prefers-reduced-motion`.

## 6. Preguntas abiertas
1. ¿Cómo se postula una persona (correo, formulario, LinkedIn Jobs)?
2. ¿Quién aprueba los textos de talento?
3. ¿Se muestran vacantes abiertas?
