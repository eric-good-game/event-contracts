# Cómo contribuir

Repositorio personal de portafolio, pero con las reglas de trabajo de un equipo.

## Idioma

- Código, nombres de archivo, ramas y commits en inglés.
- La documentación se redacta en español.

## Commits

Se siguen *Conventional Commits* en inglés. Tipos usados: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.

- Mensaje en imperativo y en minúscula: `feat: add stock.reserved schema`.
- El repositorio admite solo *squash merge*, así que el **título del pull request** es el mensaje que queda en `main`. El CI lo valida (`commitlint`).

## Ramas

- `feature/<hito>-<tema>`, por ejemplo `feature/8-event-schemas`.
- `fix/<tema>`, `docs/<tema>`, `chore/<tema>`.
- Ramas cortas, una por cambio, integradas pronto.

## Pull requests

- Título en *Conventional Commits*; descripción con la plantilla del repositorio.
- CI en verde antes de fusionar.
- La rama `main` está protegida: no admite *push* directo, *force-push* ni borrado.
- Un cambio de esquema incompatible crea una versión nueva; nunca modifica una versión publicada.

## Antes de abrir el pull request

```bash
npx --yes markdownlint-cli2@0.18.0
npx --yes yaml-lint@1.7.0 '.github/**/*.{yml,yaml}'
node scripts/check-repo.mjs
```

Cuando existan esquemas (hito 8) el CI valida además que cada esquema es válido y que cada ejemplo lo cumple.

## Hitos

El trabajo se organiza por hitos verticales. Ver el [plan de la Fase 1](https://github.com/eric-good-game/platform/blob/main/docs/09-phase-1-implementation-plan.md).
