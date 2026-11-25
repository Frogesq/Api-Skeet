# movement

Движение. [Все модули](../API_INDEX.ru.md) · [Условия использования](../COMMANDS.ru.md) · [Типы](../TYPES.ru.md).

- [movement.claim](#movementclaim)
- [movement.context](#movementcontext)

### movement.claim

<details>
<summary><code>movement.claim(feature)</code></summary>

Disable the selected native movement mode for this command after successful create_move dispatch.

| Аргумент | Тип и условия |
|---|---|
| `feature` | 'bhop'&#124;'strafe' |

Значения не возвращаются.

</details>

### movement.context

<details>
<summary><code>movement.context()</code></summary>

Prestate for the current command, nil when local player/movement/scene is unavailable.

Результаты:

- MovementSnapshot?

</details>

