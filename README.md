# event-contracts

Contratos de los eventos que se intercambian los sistemas del portafolio: el sobre estándar, los esquemas JSON Schema de cada evento y versión, los ejemplos y el catálogo.

Este repositorio es lo único que comparten los sistemas; ninguno depende del código de otro.

Estado: **hito 0 completado**. Los esquemas y el CI que los valida llegan en el hito 8, que es paralelizable con el resto de la Fase 1.

## Sobre estándar

Todo evento lleva: `id`, `type`, `version`, `occurredAt`, `source`, `correlationId`, `causationId` (opcional) y `payload`. En la Fase 1 solo se definen los eventos de Inventory: `stock.adjusted`, `stock.low`, `stock.reserved` y `stock.failed`.

## Estructura prevista

```text
event-contracts/
├── envelope/           # esquema del sobre
├── events/<tipo>/      # esquema y ejemplo de cada evento y versión
├── catalog.md          # catálogo de eventos
└── ...                 # CI que valida esquemas y ejemplos
```

## Convenciones

- UUID v7 en los identificadores y fechas ISO 8601 en UTC.
- Sin datos sensibles en los eventos.
- El esquema se versiona; un cambio incompatible crea una versión nueva.
- Commits en inglés con *Conventional Commits*; documentación en español.

Detalle: [CONTRIBUTING.md](CONTRIBUTING.md) y el [documento de contratos](https://github.com/eric-good-game/platform/blob/main/docs/06-event-contracts.md).

## Licencia

MIT. Ver [LICENSE](LICENSE).
