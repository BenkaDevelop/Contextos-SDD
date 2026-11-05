# SPEC · home (R5) · Home

Estado: **aprobada por Jhohan Axelrod el 5 nov 2026** · **en producción** (PR BenkaDevelop/benka-group#230 → qa, release #231 → main) · Release R5 · Épica BenkaDevelop/benka-group#182 (historias #183, #184)

## 1. Objetivo
Cerrar el recorrido del home después de R3 y R4. Tres cosas:
- Las tarjetas "Únete al equipo" llevan a contenido de carrera.
- Las oficinas se ven en el home.
- El orden de las secciones queda definido.

## 2. Punto de partida (producción hoy)
Hero → "We Make Growth Happen" → carrusel de socios → **Lo más reciente de Benká** (R4) → Nuestro Impacto → Únete al equipo (3 tarjetas, solo se expanden) → Transforma tu carrera → Conversemos (Contacto, Business Inquires) → footer.

- El Ecosistema salió del home en R3 y vive en /holding.
- Las Oficinas (Cali, Bogotá, Medellín, Cartagena) están en /trajectory.
- /careers no existe todavía (R16).

## 3. Momentos (se aprueban uno por uno)

| # | Momento | Qué se ve | Estado |
|---|---|---|---|
| H5-1 | Tarjetas "Únete al equipo" | Las 3 tarjetas (Tu carrera, Ser consultor, Proceso de selección) son clicables y tienen "Ver más", que baja a "Transforma tu carrera" en el mismo home. Cuando exista /careers (R16) cambia a sus anclas | Aprobado |
| H5-2 | Oficinas en el home | Bloque de oficinas con las 4 ciudades y sus fotos originales; **se mueve de /trajectory al home** (sale de Trayectoria) | Aprobado |
| H5-3 | Orden del home | Hero → We Make Growth Happen → socios → Lo más reciente de Benká → Nuestro Impacto → **Oficinas** → Únete al equipo → Transforma tu carrera → Conversemos | Aprobado |

## 4. Decisiones (5 nov 2026, Jhohan Axelrod)
- **D1** · "Ver más" baja a Transforma tu carrera hasta que exista /careers (R16).
- **D2** · Las oficinas se mueven al home y salen de /trajectory.
- **D3** · Van después de Nuestro Impacto.
- **D4 · Ajuste a la historia #184**: confirmado sin Ecosistema. decía "Ecosistema con Oficinas debajo". Desde R3 el ecosistema vive en /holding, así que la historia queda solo con las oficinas.

## 5. Criterios de aceptación
- Sin desborde a 390 px; las tarjetas son accesibles con teclado.
- Las fotos de oficinas no se pixelan (WebP a 2× del tamaño mostrado).
- Ninguna sección aprobada del home se pierde.
