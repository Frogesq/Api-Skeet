# api

Среда и обработка ошибок. [Все модули](../API_INDEX.ru.md) · [Условия использования](../RUNTIME.ru.md) · [Типы](../TYPES.ru.md).

- [api.budget](#apibudget)
- [api.capabilities](#apicapabilities)
- [api.protect](#apiprotect)

### api.budget

<details>
<summary><code>api.budget()</code></summary>

Budget snapshot; querying it consumes a host API call. Finish callback when recovering=true.

Результаты:

- LuaBudget budget

</details>

### api.capabilities

<details>
<summary><code>api.capabilities()</code></summary>

Implemented features; false means unavailable, not a simulated success.

Результаты:

- {command_requests: boolean, prediction_snapshot: boolean, prediction_simulate: boolean, grenade_control: boolean, grenade_observations: boolean, grenade_icons: boolean, grenade_trajectory: boolean, inferno_geometry: boolean, radar_snapshot: boolean, double_tap_snapshot: boolean, custom_indicators: boolean, indicator_stack: boolean, scope_state: boolean, rage_control: boolean}

</details>

### api.protect

<details>
<summary><code>api.protect(fn, limits)</code></summary>

Catch ordinary errors and budget exhaustion. Allocation failures remain fatal. Pending command edits are restored on failure; settings, draws, UI and other effects are not rolled back. fn receives no arguments; use a closure.

| Аргумент | Тип и условия |
|---|---|
| `fn` | fun(): ... |
| `limits?` | {instructions?: integer, time_ms?: number} Defaults 1000000 / 25 ms; maxima 20000000 / 250 ms; parent limits apply. |

Результаты:

- boolean ok
- string? error Exact 'budget_exceeded' for budget failure; ordinary errors have a traceback; nil on success.
- ... results All fn results including nils on success; LuaBudgetError as third result on budget failure.

</details>

