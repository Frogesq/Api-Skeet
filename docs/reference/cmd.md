# cmd

Командные запросы. [Все модули](../API_INDEX.ru.md) · [Условия использования](../COMMANDS.ru.md) · [Типы](../TYPES.ru.md).

- [cmd.get](#cmdget)
- [cmd.set_angles](#cmdset_angles)
- [cmd.set_button](#cmdset_button)
- [cmd.set_button_state](#cmdset_button_state)
- [cmd.set_movement](#cmdset_movement)

### cmd.get

<details>
<summary><code>cmd.get()</code></summary>

Current command plus this script's staged values; post events are read-only.

Результаты:

- CommandSnapshot

</details>

### cmd.set_angles

<details>
<summary><code>cmd.set_angles(angles, visible)</code></summary>

Stage grenade view input in create_move after grenades.claim. Native firearm AA uses settings overrides.

| Аргумент | Тип и условия |
|---|---|
| `angles` | Vector3 Finite pitch clamped to -89..89, yaw normalized, roll zero. |
| `visible?` | boolean Also update camera on successful commit. |

Значения не возвращаются.

</details>

### cmd.set_button

<details>
<summary><code>cmd.set_button(mask, pressed)</code></summary>

create_move only. Movement buttons; attack/attack2 require active grenade claim. Other buttons rejected.

| Аргумент | Тип и условия |
|---|---|
| `mask` | integer |
| `pressed` | boolean |

Значения не возвращаются.

</details>

### cmd.set_button_state

<details>
<summary><code>cmd.set_button_state(mask, held, changed, scroll)</code></summary>

Stage held/changed/scroll bits; same phase and mask rules as set_button.

| Аргумент | Тип и условия |
|---|---|
| `mask` | integer |
| `held` | boolean |
| `changed` | boolean |
| `scroll` | boolean |

Значения не возвращаются.

</details>

### cmd.set_movement

<details>
<summary><code>cmd.set_movement(forward, side, up)</code></summary>

Stage normalized movement before native prediction; whole script dispatch must succeed.

| Аргумент | Тип и условия |
|---|---|
| `forward` | number -1..1 (clamped). |
| `side` | number -1..1; positive is left, matching the native movement model. |
| `up?` | number -1..1. |

Значения не возвращаются.

</details>

