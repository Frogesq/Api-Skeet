# entity

Сущности. [Все модули](../API_INDEX.ru.md) · [Условия использования](../DATA.ru.md) · [Типы](../TYPES.ru.md).

- [entity.bone](#entitybone)
- [entity.bounds](#entitybounds)
- [entity.get](#entityget)
- [entity.items](#entityitems)
- [entity.local_player](#entitylocal_player)
- [entity.players](#entityplayers)
- [entity.spectators](#entityspectators)
- [entity.weapon](#entityweapon)

### entity.bone

<details>
<summary><code>entity.bone(id, bone_index)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | integer |
| `bone_index` | integer 0..127 |

Результаты:

- Vector3?

</details>

### entity.bounds

<details>
<summary><code>entity.bounds(id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | integer |

Результаты:

- {x: number, y: number, w: number, h: number}?

</details>

### entity.get

<details>
<summary><code>entity.get(id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | integer |

Результаты:

- PlayerSnapshot?

</details>

### entity.items

<details>
<summary><code>entity.items()</code></summary>

Результаты:

- {id: integer, class_hash: integer, origin: Vector3}[]

</details>

### entity.local_player

<details>
<summary><code>entity.local_player()</code></summary>

Результаты:

- PlayerSnapshot?

</details>

### entity.players

<details>
<summary><code>entity.players(enemies_only)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `enemies_only?` | boolean |

Результаты:

- PlayerSnapshot[]

</details>

### entity.spectators

<details>
<summary><code>entity.spectators()</code></summary>

Observers following the current view target in first-person or chase mode, sorted by controller index. Independent of the built-in Spectators checkbox. The first request starts collection for this script and may return an empty array until the next game frame.

Результаты:

- SpectatorSnapshot[]

</details>

### entity.weapon

<details>
<summary><code>entity.weapon(id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | integer |

Результаты:

- {item_id: integer, ammo: integer, reloading: boolean}?

</details>

