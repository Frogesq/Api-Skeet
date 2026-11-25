# renderer

Колонка индикаторов HUD. [Все модули](../API_INDEX.ru.md) · [Условия использования](../INDICATORS.ru.md) · [Типы](../TYPES.ru.md).

- [renderer.indicator](#rendererindicator)

### renderer.indicator

<details>
<summary><code>renderer.indicator(r, g, b, a, ...)</code></summary>

Append a single line above the built-in indicator rows during paint. Alpha zero reserves one row.

| Аргумент | Тип и условия |
|---|---|
| `r` | integer Red, 0..255. |
| `g` | integer Green, 0..255. |
| `b` | integer Blue, 0..255. |
| `a` | integer Alpha, 0..255. |
| `...` | any Text parts concatenated without separators, up to 2047 bytes total. Accepts strings, numbers, booleans, nil and objects with __tostring. |

Результаты:

- number? y Top edge in pixels, or nil when no row was submitted.

</details>

