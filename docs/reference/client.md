# client

Состояние скрипта и клиента. [Все модули](../API_INDEX.ru.md) · [Условия использования](../SERVICES.ru.md) · [Типы](../TYPES.ru.md).

- [client.frametime](#clientframetime)
- [client.key_down](#clientkey_down)
- [client.log](#clientlog)
- [client.log_level](#clientlog_level)
- [client.map_name](#clientmap_name)
- [client.screen_size](#clientscreen_size)
- [client.stats](#clientstats)
- [client.time](#clienttime)
- [client.unload](#clientunload)

### client.frametime

<details>
<summary><code>client.frametime()</code></summary>

Результаты:

- number seconds

</details>

### client.key_down

<details>
<summary><code>client.key_down(vk)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `vk` | integer |

Результаты:

- boolean

</details>

### client.log

<details>
<summary><code>client.log(...)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `...` | any |

Значения не возвращаются.

</details>

### client.log_level

<details>
<summary><code>client.log_level(level, ...)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `level` | 'debug'&#124;'info'&#124;'warning'&#124;'error' |
| `...` | any |

Значения не возвращаются.

</details>

### client.map_name

<details>
<summary><code>client.map_name()</code></summary>

Current map basename, or nil outside a session. No file path is returned.

Результаты:

- string?

</details>

### client.screen_size

<details>
<summary><code>client.screen_size()</code></summary>

Результаты:

- integer width
- integer height

</details>

### client.stats

<details>
<summary><code>client.stats()</code></summary>

Результаты:

- ScriptStats

</details>

### client.time

<details>
<summary><code>client.time()</code></summary>

Результаты:

- number seconds Monotonic, not game time.

</details>

### client.unload

<details>
<summary><code>client.unload()</code></summary>

Deferred self-unload after the current callback returns.

Значения не возвращаются.

</details>

