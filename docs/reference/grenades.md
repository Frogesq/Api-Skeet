# grenades

Гранаты. [Все модули](../API_INDEX.ru.md) · [Условия использования](../GRENADES.ru.md) · [Типы](../TYPES.ru.md).

- [grenades.cancel](#grenadescancel)
- [grenades.claim](#grenadesclaim)
- [grenades.context](#grenadescontext)
- [grenades.observations](#grenadesobservations)
- [grenades.predict](#grenadespredict)
- [grenades.predict_throw](#grenadespredict_throw)
- [grenades.preview](#grenadespreview)

### grenades.cancel

<details>
<summary><code>grenades.cancel()</code></summary>

Discard this script's pending command request. Does not undo published commands or unthrow a primed grenade.

Значения не возвращаются.

</details>

### grenades.claim

<details>
<summary><code>grenades.claim()</code></summary>

create_move only; authorize grenade angles/attack for the same weapon handle and suppress native AA for this command.

Результаты:

- boolean claimed False when no active grenade exists.

</details>

### grenades.context

<details>
<summary><code>grenades.context()</code></summary>

Current grenade; all command callbacks. Missing optional schema data is nil, never guessed.

Результаты:

- {item_id: integer, handle: integer, command_number: integer, pin_pulled: boolean?, throw_time: number?, strength: number?}?

</details>

### grenades.observations

<details>
<summary><code>grenades.observations(paths)</code></summary>

Copied observations, at most 128. First call can be empty until the next render-start update; minimum refresh interval 8/16/50 ms according to active forecasts, expiry 250 ms.

| Аргумент | Тип и условия |
|---|---|
| `paths?` | boolean Request cached flight predictions; false by default. Does not trace in paint. |

Результаты:

- GrenadeObservation[]

</details>

### grenades.predict

<details>
<summary><code>grenades.predict(origin, velocity, item_id, age)</code></summary>

Command callbacks only. Bounded hull-trace prediction; does not run player prediction or edit commands.

| Аргумент | Тип и условия |
|---|---|
| `origin` | Vector3 Initial position in world units; magnitude at most 10000000. |
| `velocity` | Vector3 Initial units per second; magnitude at most 100000. |
| `item_id` | integer 43..48. |
| `age?` | number Seconds since release, finite and nonnegative; default 0. |

Результаты:

- GrenadePath path Check valid and complete; never treat a budget-truncated endpoint as a landing.

</details>

### grenades.predict_throw

<details>
<summary><code>grenades.predict_throw(angles, strength)</code></summary>

Command callbacks only. Predict from the validated current first-person eye or pawn origin + view offset in third person, using the actual held grenade; does not throw it.

| Аргумент | Тип и условия |
|---|---|
| `angles` | Vector3 Desired pitch/yaw in degrees; pitch clamped to -89..89, roll ignored. |
| `strength` | number 0..1: secondary 0, both buttons 0.5, primary 1; intermediate strength is allowed. |

Результаты:

- GrenadePath path May report no_active_grenade, player_velocity_unavailable, player_eye_unavailable, throw_origin_unavailable_or_budget, throw_origin_start_solid or throw_origin_invalid_collision. Missing native throw velocity uses the standard 750 profile.

</details>

### grenades.preview

<details>
<summary><code>grenades.preview()</code></summary>

Request/read the held grenade preview from the game-thread cache. No command writes; first call may return nil.

Результаты:

- GrenadePath? path Approximate physics, including incomplete results; check valid and complete.
- string? reason snapshot_unavailable or preview_unavailable when no path exists.

</details>

