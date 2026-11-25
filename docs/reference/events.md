# events

События. [Все модули](../API_INDEX.ru.md) · [Условия использования](../EVENTS.ru.md) · [Типы](../TYPES.ru.md).

- [events.off](#eventsoff)
- [events.on](#eventson)

### events.off

<details>
<summary><code>events.off(id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | integer |

Результаты:

- boolean removed

</details>

### events.on

<details>
<summary><code>events.on(name, callback)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `name` | EventName |
| `callback` | fun(event: table) Callback return values are ignored. |

Результаты:

- integer subscription

Дополнительная типизированная форма: `fun(name: 'game_event', callback: fun(event: GameEvent)): integer`.

</details>

