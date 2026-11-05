# Contextos SDD · Benká Group

Specs (Spec-Driven Development) de los productos digitales de Benká Group.
El código vive en cada repositorio; aquí vive el **qué** y el **por qué**: mapa de módulos, specs, decisiones y pendientes.

## Flujo

1. **Mapa de módulos** aprobado (fase 0).
2. **Spec por módulo** (`SPEC-<modulo>.md`) aprobada antes de escribir código.
3. **Historias** como issues en el repo de código, enlazadas a su spec.
4. **Implementación** historia por historia: rama desde `main` → PR a `qa` → PR `qa` → `main` (producción).

## Proyectos

| Carpeta | Producto | Repo de código | Tablero |
|---|---|---|---|
| [benka-group-sitio-v2](benka-group-sitio-v2/) | Sitio benkagroup.co v2 y sitios de unidades | [BenkaDevelop/benka-group](https://github.com/BenkaDevelop/benka-group) | [Project 3](https://github.com/users/BenkaDevelop/projects/3) |

En cada carpeta: `ROADMAP.md` (módulos y releases), `SPEC-*.md` (specs) y `BACKLOG-pendientes.md` (temas por definir).
