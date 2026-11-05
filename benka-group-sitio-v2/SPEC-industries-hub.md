# SPEC · industries-hub (R6) · Página /industries

Estado: **aprobada por Jhohan Axelrod el 5 nov 2026** · **en producción** (R6: PR BenkaDevelop/benka-group#232 → qa, release #233; ajuste de lista #234 → #235) · Release R6 · Épica BenkaDevelop/benka-group#185 (historias #186, #187, #188)

## 1. Objetivo
Convertir /industries en el hub de industrias al estilo McKinsey/BCG:
- La lista de industrias.
- Cómo trabajamos.
- Los casos con resultados reales.
- Un cierre que lleva al contacto.

## 2. Punto de partida (producción hoy)
- Título "Industrias", un texto, la foto `industries_img` y la lista de 9 industrias en inglés.
- La lista no tiene enlaces, y todavía no existe ninguna página de industria (Agroindustria llega en R7).

## 3. Momentos (se aprueban uno por uno)

| # | Momento | Qué se ve | Estado |
|---|---|---|---|
| I1 | Lista de industrias | Como en el HTML aprobado: nombre en **inglés** a 20 px (tamaño original), nombre en español a la derecha y "Ver más" con flecha · fila azul completa al pasar el cursor · **el clic no hace nada** hasta que cada industria tenga su página (Agro en R7) | Aprobado |
| I2 | Cómo trabajamos | Foto del equipo trabajando en mesa (`focus.png`; `meeting.png` ya se usa en otras páginas) · "Somos una firma de consultoría estratégica que implementa" · ruta de 4 pasos con avance automático y entregable por paso | Aprobado |
| I3 | Casos destacados | **Diseño B, cifra protagonista**: cifra grande sobre el color de cada compañía, reflejo de vidrio, segunda cifra en píldora glass, pie glass con el logo; rejilla fija para que todos los textos queden alineados · Nuevo modelo comercial (18% / 12%), Campañas de consumo (3,2X / +25 ROAS), Plataforma ATL con IA (US$90K / 72%), Formación en tecnología (40% / **+12% Alfabetización digital**) · solo título y cifras | Aprobado |
| I4 | Cierre | "¿Tu industria tiene un reto que nadie ha resuelto?" · "Hablemos" y "Ver capabilities" | Aprobado |

## 4. Decisiones (5 nov 2026, Jhohan Axelrod)
- **D1** · Sin clic hasta que exista la página de cada industria; la flecha y "Ver más" se muestran igual.
- **D2** · Casos con diseño B y solo título y cifras.
- **D3** · Industrias en inglés (ya estaba definido). El selector ES · EN · PT de todo el sitio va en un release propio después de R6 (P-40).

## 5. Criterios de aceptación
- Sin desborde a 390 px; las filas son accesibles con teclado.
- Ninguna cifra sin validar.
- La ruta respeta `prefers-reduced-motion`.
