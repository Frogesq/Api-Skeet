# storage

Сохранение. [Все модули](../API_INDEX.ru.md) · [Условия использования](../SERVICES.ru.md) · [Типы](../TYPES.ru.md).

- [storage.get](#storageget)
- [storage.set](#storageset)

### storage.get

<details>
<summary><code>storage.get(key, default)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `key` | string |
| `default?` | any |

Результаты:

- any

</details>

### storage.set

<details>
<summary><code>storage.set(key, value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `key` | string 1..128 bytes. |
| `value` | any Pass nil to remove the key. Total serialized storage <=64 KiB; saved periodically and on unload. |

Значения не возвращаются.

</details>

