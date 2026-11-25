# combat

Расчёты и данные оружия. [Все модули](../API_INDEX.ru.md) · [Условия использования](../DATA.ru.md) · [Типы](../TYPES.ru.md).

- [combat.aim_punch](#combataim_punch)
- [combat.can_shoot](#combatcan_shoot)
- [combat.context](#combatcontext)
- [combat.damage](#combatdamage)
- [combat.double_tap](#combatdouble_tap)
- [combat.hitboxes](#combathitboxes)
- [combat.hitchance](#combathitchance)
- [combat.records](#combatrecords)
- [combat.spread_correction](#combatspread_correction)
- [combat.spread_sample](#combatspread_sample)
- [combat.weapon_state](#combatweapon_state)

### combat.aim_punch

<details>
<summary><code>combat.aim_punch()</code></summary>

Результаты:

- Vector3?

</details>

### combat.can_shoot

<details>
<summary><code>combat.can_shoot(ignore_next_attack)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `ignore_next_attack?` | boolean Still checks reload/ammo; useful while an R8 cock is already held. |

Результаты:

- boolean

</details>

### combat.context

<details>
<summary><code>combat.context()</code></summary>

Результаты:

- {valid: boolean, weapon_type: integer, item_id: integer, tick: integer, time: number, spread: number, inaccuracy: number, scoped: boolean, range: number, eye: Vector3}

</details>

### combat.damage

<details>
<summary><code>combat.damage(target_id, world_point, record_tick)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `target_id` | integer |
| `world_point` | Vector3 |
| `record_tick?` | integer Must still be an available non-future record. |

Результаты:

- {damage: number, hitbox: integer, hitgroup: integer, penetrated: boolean}?

</details>

### combat.double_tap

<details>
<summary><code>combat.double_tap()</code></summary>

Read a copied native observation in any callback, including paint. No engine simulation or mutation. Command callbacks before final serialization can see unavailable. Always returns a table; retain copies freely, fetch again for freshness.

Результаты:

- DoubleTapSnapshot

</details>

### combat.hitboxes

<details>
<summary><code>combat.hitboxes(id, record_tick)</code></summary>

Command callbacks only. nil if the record expired; latest record if tick omitted.

| Аргумент | Тип и условия |
|---|---|
| `id` | integer |
| `record_tick?` | integer |

Результаты:

- {tick: integer, time: number, hitboxes: HitboxSnapshot[]}?

</details>

### combat.hitchance

<details>
<summary><code>combat.hitchance(id, point, hitbox, record_tick)</code></summary>

At most 32 queries per command. Head probability excludes samples that first hit another hitbox of the target; no per-sample world traces.

| Аргумент | Тип и условия |
|---|---|
| `id` | integer |
| `point` | Vector3 |
| `hitbox` | integer 0..18 |
| `record_tick?` | integer |

Результаты:

- number? percentage 0..100

</details>

### combat.records

<details>
<summary><code>combat.records(target_id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `target_id` | integer |

Результаты:

- {tick: integer, time: number, origin: Vector3, velocity: Vector3, ducked: boolean, extrapolated: boolean}[]

</details>

### combat.spread_correction

<details>
<summary><code>combat.spread_correction(aim, tick, hidden_shot)</code></summary>

Return native spread correction for the supplied aim/tick, or nil if no solution.

| Аргумент | Тип и условия |
|---|---|
| `aim` | Vector3 |
| `tick?` | integer |
| `hidden_shot?` | boolean |

Результаты:

- Vector3?

</details>

### combat.spread_sample

<details>
<summary><code>combat.spread_sample(angles, tick)</code></summary>

Sample the current weapon's native spread for an exact command angle/tick.

| Аргумент | Тип и условия |
|---|---|
| `angles` | Vector3 |
| `tick?` | integer |

Результаты:

- {seed: integer, x: number, y: number}?

</details>

### combat.weapon_state

<details>
<summary><code>combat.weapon_state()</code></summary>

Результаты:

- {item_id: integer, is_revolver: boolean, client_tick: integer, tick_base: integer, ready_tick: integer, next_primary_tick: integer, next_secondary_tick: integer, ammo: integer, reloading: boolean, can_start_primary: boolean, postponed_primary_ready: boolean}?

</details>

