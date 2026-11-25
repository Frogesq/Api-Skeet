# console

Игровая консоль. [Все модули](../API_INDEX.ru.md) · [Условия использования](../SERVICES.ru.md) · [Типы](../TYPES.ru.md).

- [console.clear_pending](#consoleclear_pending)
- [console.exec](#consoleexec)
- [console.print](#consoleprint)
- [console.say](#consolesay)

### console.clear_pending

<details>
<summary><code>console.clear_pending()</code></summary>

Cancel this script's queued requests; requests already handed to the engine are unaffected.

Результаты:

- integer removed

</details>

### console.exec

<details>
<summary><code>console.exec(command)</code></summary>

Queue game console commands for a following game frame-stage; true means queued.

| Аргумент | Тип и условия |
|---|---|
| `command` | string 1..1024 bytes; NUL forbidden. Game command batches are allowed. |

Результаты:

- boolean accepted
- string? reason console_unavailable, queue_full, rate_limited or script_stopping.

</details>

### console.print

<details>
<summary><code>console.print(text)</code></summary>

Queue literal text in the game console, with a trailing newline. Percent signs are literal.

| Аргумент | Тип и условия |
|---|---|
| `text` | string Up to 2048 bytes; NUL forbidden. |

Результаты:

- boolean accepted
- string? reason

</details>

### console.say

<details>
<summary><code>console.say(text, team_only)</code></summary>

Queue a single quoted say/say_team command, without command injection.

| Аргумент | Тип и условия |
|---|---|
| `text` | string 1..200 UTF-8 bytes; controls, quotes, backslashes and semicolons forbidden. |
| `team_only?` | boolean Defaults to false. |

Результаты:

- boolean accepted
- string? reason

</details>

