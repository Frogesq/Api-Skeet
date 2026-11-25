# indicators

Индикаторы. [Все модули](../API_INDEX.ru.md) · [Условия использования](../INDICATORS.ru.md) · [Типы](../TYPES.ru.md).

- [indicators.get](#indicatorsget)

### indicators.get

<details>
<summary><code>indicators.get(category, name)</code></summary>

Read-only snapshot in any callback. The ragebot/double tap pair returns native DT state. Other Boolean settings return toggle state; missing, ambiguous or non-Boolean fields raise an error. No charge is invented for other features.

| Аргумент | Тип и условия |
|---|---|
| `category` | string Exact category from settings.list(). |
| `name` | string Exact setting name from settings.list(). |

Результаты:

- DoubleTapSnapshot&#124;ToggleIndicator

</details>

