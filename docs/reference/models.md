# models

Модели. [Все модули](../API_INDEX.ru.md) · [Условия использования](../SERVICES.ru.md) · [Типы](../TYPES.ru.md).

- [models.clear](#modelsclear)
- [models.current](#modelscurrent)
- [models.list](#modelslist)
- [models.set](#modelsset)
- [models.status](#modelsstatus)

### models.clear

<details>
<summary><code>models.clear()</code></summary>

Release this script's choice. The next Lua choice, built-in agent or native model is applied on a game frame.

Значения не возвращаются.

</details>

### models.current

<details>
<summary><code>models.current()</code></summary>

Результаты:

- string? path This script's current virtual model path, or nil.

</details>

### models.list

<details>
<summary><code>models.list()</code></summary>

Excludes arm/arms/hand/hands filename tokens (case-insensitive; separators _, -, .).

Результаты:

- CustomModel[] models Up to 512 compiled models found under CS2 game/csgo/characters/models; filename filtering does not validate model contents.

</details>

### models.set

<details>
<summary><code>models.set(id)</code></summary>

Compatible legacy CS body rigs are adapted in-match and in the main-menu character; selection is not animation validation.

| Аргумент | Тип и условия |
|---|---|
| `id` | string ID returned by models.list(). |

Результаты:

- string path Virtual model path; this script's choice overrides the built-in agent changer while enabled.

</details>

### models.status

<details>
<summary><code>models.status()</code></summary>

Результаты:

- 'idle'&#124;'ready'&#124;'error' status Ready confirms file existence, not engine rendering.
- string? message Error detail when status is error.

</details>

