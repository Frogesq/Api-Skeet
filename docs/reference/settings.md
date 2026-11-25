# settings

Настройки и бинды. [Все модули](../API_INDEX.ru.md) · [Условия использования](../SETTINGS.ru.md) · [Типы](../TYPES.ru.md).

- [settings.add_bind](#settingsadd_bind)
- [settings.bind](#settingsbind)
- [settings.binds](#settingsbinds)
- [settings.get](#settingsget)
- [settings.list](#settingslist)
- [settings.override](#settingsoverride)
- [settings.remove_bind](#settingsremove_bind)
- [settings.set](#settingsset)
- [settings.weapon_profiles](#settingsweapon_profiles)

### settings.add_bind

<details>
<summary><code>settings.add_bind(category, name, options)</code></summary>

Attach a native bind marker; stored in the ordinary config and independent of script lifetime. Existing registration is preserved unless replace=true. Non-Boolean values need an explicit active value. Boolean settings retain native modes and activate true; other fields restore their base value when inactive. Actions without registered fields, custom/changer fields, private preferences and forced watermark fields are excluded.

| Аргумент | Тип и условия |
|---|---|
| `category` | string Exact category from settings.list(). |
| `name` | string Exact field name from settings.list(). |
| `options?` | {key?: integer, mode?: integer, value?: any, replace?: boolean} key 0..255, mode 0 toggle / 1 hold_on / 2 hold_off / 3 always_on. value must match field type and intended control range. |

Результаты:

- {key: integer, mode: integer, active: boolean}

</details>

### settings.bind

<details>
<summary><code>settings.bind(category, name, key, mode)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `category` | string |
| `name` | string |
| `key?` | integer Windows virtual key, 0..255. |
| `mode?` | integer 0 toggle, 1 hold_on, 2 hold_off, 3 always_on. |

Результаты:

- {key: integer, mode: integer, active: boolean}

</details>

### settings.binds

<details>
<summary><code>settings.binds()</code></summary>

Результаты:

- BindSnapshot[] Native bound settings, added field bindings and active scripts' Lua checkbox binds; includes inactive binds, excludes archived per-weapon profiles.

</details>

### settings.get

<details>
<summary><code>settings.get(category, name)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `category` | string |
| `name` | string |

Результаты:

- any value

</details>

### settings.list

<details>
<summary><code>settings.list(category_filter)</code></summary>

Refresh categories from weapon_profiles() after changing group overrides or loading a config. Aim/shot fields reject set/override but allow explicit native bindings. Legacy get/bind reads use the held weapon in that class when the command context is valid, otherwise its first menu entry.

| Аргумент | Тип и условия |
|---|---|
| `category_filter?` | string |

Результаты:

- SettingDescriptor[]

</details>

### settings.override

<details>
<summary><code>settings.override(category, name, value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `category` | string |
| `name` | string |
| `value` | any Pass nil to release this script's override. |

Значения не возвращаются.

</details>

### settings.remove_bind

<details>
<summary><code>settings.remove_bind(category, name)</code></summary>

Remove an added marker/binding and restore an active non-Boolean field's base value. Save the config to persist removal.

| Аргумент | Тип и условия |
|---|---|
| `category` | string |
| `name` | string |

Значения не возвращаются.

</details>

### settings.set

<details>
<summary><code>settings.set(category, name, value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `category` | string |
| `name` | string |
| `value` | any |

Значения не возвращаются.

</details>

### settings.weapon_profiles

<details>
<summary><code>settings.weapon_profiles()</code></summary>

Результаты:

- WeaponProfile[] All 34 firearms, stable catalog order; categories reflect current group overrides; available at script load, excludes Zeus/knives/grenades.

</details>

