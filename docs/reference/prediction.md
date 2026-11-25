# prediction

Снимки prediction. [Все модули](../API_INDEX.ru.md) · [Условия использования](../COMMANDS.ru.md) · [Типы](../TYPES.ru.md).

- [prediction.before](#predictionbefore)
- [prediction.result](#predictionresult)

### prediction.before

<details>
<summary><code>prediction.before()</code></summary>

Alias of movement.context; no second prediction transaction is run.

Результаты:

- MovementSnapshot?

</details>

### prediction.result

<details>
<summary><code>prediction.result()</code></summary>

Actual native prediction result in prediction/post callbacks; nil before prediction or on invalid output.

Результаты:

- {valid: boolean, command_number: integer, phase: string, tick: integer, flags: integer, move_type: integer, origin: Vector3, velocity: Vector3, landed: boolean, landed_fraction: number}?

</details>

