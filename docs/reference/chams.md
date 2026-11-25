# chams

Материалы. [Все модули](../API_INDEX.ru.md) · [Условия использования](../SERVICES.ru.md) · [Типы](../TYPES.ru.md).

- [chams.builtin_material](#chamsbuiltin_material)
- [chams.create_material](#chamscreate_material)
- [chams.load_material](#chamsload_material)
- [chams.set](#chamsset)
- [chams.targets](#chamstargets)

### chams.builtin_material

<details>
<summary><code>chams.builtin_material(name)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `name` | string "bloom", "glow", "flat" or "glass". Load phase only. |

Результаты:

- integer? handle Script-local handle with visible and ignorez variants.
- string? error "material_unavailable" on native failure.

</details>

### chams.create_material

<details>
<summary><code>chams.create_material(brightness, tint)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `brightness` | number 0.1..8. Only allowed while the script loads. |
| `tint` | Color RGB baked into a new solidcolor material; alpha is ignored. |

Результаты:

- integer handle Script-local handle, valid until the script is unloaded.

</details>

### chams.load_material

<details>
<summary><code>chams.load_material(visible_path, ignorez_path)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `visible_path` | string Virtual materials/.../*.vmat or .vmat_c resource path. Load phase only. |
| `ignorez_path` | string? Optional separately authored ignorez material path. |

Результаты:

- integer? handle Script-local handle; no ignorez variant unless explicitly provided.
- string? error Missing resource/interface errors; invalid arguments raise a Lua error.

</details>

### chams.set

<details>
<summary><code>chams.set(target, handle, color)</code></summary>

attachments: local owned inventory weapons in thirdperson, including held and holstered pistol/knife models.

| Аргумент | Тип и условия |
|---|---|
| `target` | string One of chams.targets(). |
| `handle` | integer? Script-local material handle; nil releases this target. |
| `color` | Color? Render RGBA; required unless handle is nil. |

Значения не возвращаются.

</details>

### chams.targets

<details>
<summary><code>chams.targets()</code></summary>

Результаты:

- string[] targets enemy, enemy_invisible, team, team_invisible, local, arms, weapon, attachments.

</details>

