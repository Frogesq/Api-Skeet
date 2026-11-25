# scope

Свой прицел. [Все модули](../API_INDEX.ru.md) · [Условия использования](../RENDER.ru.md) · [Типы](../TYPES.ru.md).

- [scope.state](#scopestate)

### scope.state

<details>
<summary><code>scope.state()</code></summary>

Read the current local scope in paint, including when a script hides the built-in overlay. Geometry is sampled once per frame.

Результаты:

- {scoped: boolean, center_x: number, center_y: number, fraction: number, spread: number, gap: number, horizontal: number, vertical: number}? Pixel geometry and zoom animation (0..1), nil without an eligible live view.

</details>

