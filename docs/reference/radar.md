# radar

Радар. [Все модули](../API_INDEX.ru.md) · [Условия использования](../RADAR.ru.md) · [Типы](../TYPES.ru.md).

- [radar.project](#radarproject)
- [radar.snapshot](#radarsnapshot)

### radar.project

<details>
<summary><code>radar.project(world, center, yaw, range, x, y, size, rotate, clamp_edge)</code></summary>

Pure coordinate conversion; does not read entities or trace. Rotation keeps camera forward at the top.

| Аргумент | Тип и условия |
|---|---|
| `world` | Vector3 Position to project. |
| `center` | Vector3 Radar center in world space, usually snapshot.center. |
| `yaw` | number Camera heading in degrees; ignored when rotate=false. |
| `range` | number Positive world distance from radar center to an edge. |
| `x` | number Screen X of the square's top-left corner. |
| `y` | number Screen Y of the square's top-left corner. |
| `size` | number Positive square side in pixels. |
| `rotate?` | boolean Default true; false keeps +X right and +Y up. |
| `clamp_edge?` | boolean Default true; outside points are clamped along the direction to the square edge. |

Результаты:

- number x Screen coordinate.
- number y Screen coordinate.
- boolean inside Whether the original point was inside the square before clamping.

</details>

### radar.snapshot

<details>
<summary><code>radar.snapshot(paths)</code></summary>

Request/read copied client data; usable in paint. Nil outside a valid session or while the first snapshot is pending. No map texture is supplied.

| Аргумент | Тип и условия |
|---|---|
| `paths?` | boolean Also request cached grenade trajectories; default false. |

Результаты:

- RadarSnapshot? snapshot
- string? reason snapshot_unavailable when nil.

</details>

