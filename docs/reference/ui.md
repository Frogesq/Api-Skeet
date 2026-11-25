# ui

Контролы и оформление. [Все модули](../API_INDEX.ru.md) · [Условия использования](../UI.ru.md) · [Типы](../TYPES.ru.md).

- [ui.attach_menu](#uiattach_menu)
- [ui.attach_tab](#uiattach_tab)
- [ui.attach_window](#uiattach_window)
- [ui.bind](#uibind)
- [ui.create](#uicreate)
- [ui.create_tab](#uicreate_tab)
- [ui.create_tab_group](#uicreate_tab_group)
- [ui.create_window](#uicreate_window)
- [ui.create_window_group](#uicreate_window_group)
- [ui.create_window_page](#uicreate_window_page)
- [ui.get](#uiget)
- [ui.get_language](#uiget_language)
- [ui.get_languages](#uiget_languages)
- [ui.get_menu_colors](#uiget_menu_colors)
- [ui.get_menu_font](#uiget_menu_font)
- [ui.get_menu_groups](#uiget_menu_groups)
- [ui.get_menu_rect](#uiget_menu_rect)
- [ui.get_translation_keys](#uiget_translation_keys)
- [ui.get_window](#uiget_window)
- [ui.is_menu_opened](#uiis_menu_opened)
- [ui.mouse_state](#uimouse_state)
- [ui.nl_style](#uinl_style)
- [ui.register_language](#uiregister_language)
- [ui.remove_tab](#uiremove_tab)
- [ui.reset_theme](#uireset_theme)
- [ui.set](#uiset)
- [ui.set_blur_opacity](#uiset_blur_opacity)
- [ui.set_language](#uiset_language)
- [ui.set_language_font](#uiset_language_font)
- [ui.set_menu_font](#uiset_menu_font)
- [ui.set_menu_skin](#uiset_menu_skin)
- [ui.set_style_color](#uiset_style_color)
- [ui.set_tab_style](#uiset_tab_style)
- [ui.set_window_open](#uiset_window_open)
- [ui.style_colors](#uistyle_colors)
- [ui.translate](#uitranslate)
- [ui.unregister_language](#uiunregister_language)
- [ui.window_bind](#uiwindow_bind)

### ui.attach_menu

<details>
<summary><code>ui.attach_menu(control, tab, group)</code></summary>

Append an owned control to an existing native group, retaining its value/bind persistence. Unknown destinations fail without changing the old attachment. Multiple owners coexist. Attaching to LUA/A or LUA/B reveals the shared Lua tab. Unload removes only this owner's controls. Clears any window/shared-tab attachment. The control remains available on its CONFIG script page. No new native groups are created; placements are declared by the script, not saved as config data.

| Аргумент | Тип и условия |
|---|---|
| `control` | string Owned ui.create control id. |
| `tab?` | string Exact tab name from ui.get_menu_groups; nil detaches. |
| `group?` | string Exact existing group name; required with tab. |

Значения не возвращаются.

</details>

### ui.attach_tab

<details>
<summary><code>ui.attach_tab(control, tab, group)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `control` | string Owned ui.create control. |
| `tab?` | string Owned slot id; controls remain on the script page; nil removes the association. |
| `group?` | string Required if the tab has groups. Otherwise nil adds controls to A. |

Значения не возвращаются.

</details>

### ui.attach_window

<details>
<summary><code>ui.attach_window(control_id, window_id, group_id)</code></summary>

Moves an existing ui.create control into this script's window; nil restores Config placement.

| Аргумент | Тип и условия |
|---|---|
| `control_id` | string |
| `window_id?` | string |
| `group_id?` | string Required for a grouped menu window. Owned by this window. |

Значения не возвращаются.

</details>

### ui.bind

<details>
<summary><code>ui.bind(id, key, mode)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string Checkbox control id. |
| `key?` | integer Windows VK 0..255; 0 removes the key. |
| `mode?` | integer 0 toggle, 1 hold_on, 2 hold_off, 3 always_on. |

Результаты:

- {key: integer, mode: integer, active: boolean} bind

</details>

### ui.create

<details>
<summary><code>ui.create(kind, id, label, default, min_or_options, max)</code></summary>

Text controls accept only printable ASCII when typed in the menu; programmatic string values are preserved.

| Аргумент | Тип и условия |
|---|---|
| `kind` | 'checkbox'&#124;'button'&#124;'slider'&#124;'combo'&#124;'color'&#124;'text' |
| `id` | string |
| `label` | string |
| `default` | any |
| `min_or_options?` | number&#124;string[]&#124;{key: integer, mode: integer} Checkbox accepts optional bind table (key 0..255; mode 0 toggle, 1 hold_on, 2 hold_off, 3 always_on). |
| `max?` | number |

Результаты:

- string id

</details>

### ui.create_tab

<details>
<summary><code>ui.create_tab(id, title, options)</code></summary>

Register this script's sections in the shared hidden Lua tab after CONFIG. Multiple scripts coexist. The last owner removal hides the tab and returns to CONFIG. Native A/B columns and the Lua text icon are shared; style options are retained metadata.

| Аргумент | Тип и условия |
|---|---|
| `id` | string Script-local stable id, 1..80 UTF-8 bytes. |
| `title` | string Literal UTF-8 caption, 1..96 bytes. |
| `options?` | MenuTabStyle |

Результаты:

- string id One tab per owner. Controls also remain on the script page.

</details>

### ui.create_tab_group

<details>
<summary><code>ui.create_tab_group(tab, id, title, column, layout)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `tab` | string Owned tab id. |
| `id` | string Stable group id, 1..80 bytes. |
| `title` | string Literal caption, 1..96 bytes. |
| `column?` | integer 1 left (default), 2 right. Up to 16 groups per tab. |
| `layout?` | MenuTabLayout Legacy layout metadata; shared A/B columns stack groups in registration order. |

Результаты:

- string id

</details>

### ui.create_window

<details>
<summary><code>ui.create_window(id, title, options)</code></summary>

Registers an interactive, draggable/resizable script window; at most 8 per script.

| Аргумент | Тип и условия |
|---|---|
| `id` | string Unique script-owned UTF-8 ID, 1..80 bytes |
| `title` | string Script-authored UTF-8 title, 1..160 bytes |
| `options?` | LuaWindowOptions |

Результаты:

- string id

</details>

### ui.create_window_group

<details>
<summary><code>ui.create_window_group(window, page, id, title, column, layout)</code></summary>

Create a native group in a menu-window page. Up to 16 per window; no overlaps.

| Аргумент | Тип и условия |
|---|---|
| `window` | string Owned window id. |
| `page` | string Owned page id. |
| `id` | string Unique group id within the window, 1..80 bytes. |
| `title` | string Group caption, 1..96 bytes. |
| `column?` | integer 1 left (default), 2 right. |
| `layout?` | {top?: number, bottom?: number} Fractions 0..1, defaults 0/1, minimum height 0.12. |

Результаты:

- string id

</details>

### ui.create_window_page

<details>
<summary><code>ui.create_window_page(window, id, title, icon)</code></summary>

Create a left sidebar page in a style=menu window. Up to 8 per window.

| Аргумент | Тип и условия |
|---|---|
| `window` | string Owned window id. |
| `id` | string Unique page id, 1..80 bytes. |
| `title` | string Page title, 1..96 bytes. |
| `icon` | string Literal UTF-8 sidebar symbol, 1..16 bytes. |

Результаты:

- string id

</details>

### ui.get

<details>
<summary><code>ui.get(id)</code></summary>

For a button, consumes the pending click and returns true once. Poll in paint.

| Аргумент | Тип и условия |
|---|---|
| `id` | string |

Результаты:

- any

</details>

### ui.get_language

<details>
<summary><code>ui.get_language()</code></summary>

Результаты:

- string id Effective language ID; en when the saved custom ID is unavailable

</details>

### ui.get_languages

<details>
<summary><code>ui.get_languages()</code></summary>

Результаты:

- MenuLanguage[] languages English, Simplified Chinese, Brazilian Portuguese, then custom IDs in alphabetical order

</details>

### ui.get_menu_colors

<details>
<summary><code>ui.get_menu_colors()</code></summary>

Read current base menu preferences; does not change or save them. Transient Lua style patches are excluded.

Результаты:

- {accent: Color, top_line: Color, custom_top_line: boolean}

</details>

### ui.get_menu_font

<details>
<summary><code>ui.get_menu_font()</code></summary>

Результаты:

- MenuFontInfo font Metadata; GPU creation is deferred

</details>

### ui.get_menu_groups

<details>
<summary><code>ui.get_menu_groups()</code></summary>

List valid destinations for ui.attach_menu. This does not create groups.

Результаты:

- BuiltinMenuGroup[] groups

</details>

### ui.get_menu_rect

<details>
<summary><code>ui.get_menu_rect()</code></summary>

paint only. Screen pixels.

Результаты:

- {x: number, y: number, w: number, h: number}

</details>

### ui.get_translation_keys

<details>
<summary><code>ui.get_translation_keys()</code></summary>

Результаты:

- string[] keys Sorted English menu text, without ## suffixes

</details>

### ui.get_window

<details>
<summary><code>ui.get_window(id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string |

Результаты:

- LuaWindowInfo window

</details>

### ui.is_menu_opened

<details>
<summary><code>ui.is_menu_opened()</code></summary>

paint only.

Результаты:

- boolean

</details>

### ui.mouse_state

<details>
<summary><code>ui.mouse_state()</code></summary>

paint only. Current-frame mouse coordinates in screen pixels; clicked is a new left press, down is held. All paint callbacks see the same click. Drag only while the menu is open; stop on release or menu close.

Результаты:

- {x: number, y: number, down: boolean, clicked: boolean}

</details>

### ui.nl_style

<details>
<summary><code>ui.nl_style()</code></summary>

Returns the NL shell palette, metrics, icon strings and script-owned font/texture handles. Obtain once during paint.

Результаты:

- table skin

</details>

### ui.register_language

<details>
<summary><code>ui.register_language(id, name, translations)</code></summary>

Registers/replaces this script's UTF-8 menu dictionary. Built-ins en/zh-CN/pt-BR are reserved. Removed on script unload/error; missing entries fall back to the original English text. Applies only to Skeet's native interface/editor shell; Lua UI, source and logs stay literal.

| Аргумент | Тип и условия |
|---|---|
| `id` | string ASCII letters/digits/-/_, 1..48 bytes |
| `name` | string UTF-8 display name, 1..96 bytes |
| `translations` | table<string,string> English visible text => UTF-8 translation |

Результаты:

- boolean success False for another owner's ID or registry limit

</details>

### ui.remove_tab

<details>
<summary><code>ui.remove_tab(id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string Owned tab id; controls remain on the script page. |

Значения не возвращаются.

</details>

### ui.reset_theme

<details>
<summary><code>ui.reset_theme()</code></summary>

Значения не возвращаются.

</details>

### ui.set

<details>
<summary><code>ui.set(id, value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string |
| `value` | any |

Значения не возвращаются.

</details>

### ui.set_blur_opacity

<details>
<summary><code>ui.set_blur_opacity(surface, opacity)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `surface` | 'sidebar'&#124;'header'&#124;'body'&#124;'surface'&#124;'card'&#124;'control' |
| `opacity?` | number 0..1; nil removes this script's override. |

Значения не возвращаются.

</details>

### ui.set_language

<details>
<summary><code>ui.set_language(id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string |

Результаты:

- boolean success False for an unknown ID; selection is saved with the config

</details>

### ui.set_language_font

<details>
<summary><code>ui.set_language_font(id, filename, size)</code></summary>

Associates a local TTF/OTF/TTC/OTC file with this script's registered language. CPU validation happens now; GPU font creation is deferred to the next menu frame. nil filename removes the language font, falling back to a menu override or the default. Lua UI/source/logs retain their own fonts.

| Аргумент | Тип и условия |
|---|---|
| `id` | string This script's language ID; built-ins/other owners are protected |
| `filename?` | string UTF-8 basename directly in %LOCALAPPDATA%/skeet |
| `size?` | number 8..24 pixels, default 11; one size across the native interface |

Результаты:

- boolean success
- string? error File/format/ownership/cache failure; previous selection is preserved

</details>

### ui.set_menu_font

<details>
<summary><code>ui.set_menu_font(filename, size, sizing, hinting)</code></summary>

Sets this script's default menu font without changing the selected language. A font attached to the selected language takes priority. Latest live default override wins.

| Аргумент | Тип и условия |
|---|---|
| `filename?` | string Basename in %LOCALAPPDATA%/skeet; nil releases this script's override |
| `size?` | number 8..24 pixels, default 11 |
| `sizing?` | "real_dim"&#124;"nominal" Default real_dim. Nominal uses the Unicode charmap and a 72 DPI character size. |
| `hinting?` | "auto"&#124;"native" Default auto. Native uses font outlines and the font's own hints. |

Результаты:

- boolean success
- string? error

</details>

### ui.set_menu_skin

<details>
<summary><code>ui.set_menu_skin(options)</code></summary>

Replaces this script's native-menu presentation lease; settings/binds remain native. Latest live skin wins as a whole; older skin palettes do not leak into it. nil removes only this script's skin. Unload/error releases it automatically. Validation is transactional; unknown keys/invalid metrics/foreign or dynamic logos raise an error. Existing menu color/alpha patches still compose in owner update order. Fonts are separate.

| Аргумент | Тип и условия |
|---|---|
| `options?` | MenuSkin Full replacement, not a patch to this script's previous skin. |

Значения не возвращаются.

</details>

### ui.set_style_color

<details>
<summary><code>ui.set_style_color(backend, name, color)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `backend` | 'menu' |
| `name` | string |
| `color?` | Color nil removes this script's color override. |

Значения не возвращаются.

</details>

### ui.set_tab_style

<details>
<summary><code>ui.set_tab_style(id, options)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string Owned tab id. |
| `options?` | MenuTabStyle Partial update; nil resets style/icon and preserves id/title/groups. |

Значения не возвращаются.

</details>

### ui.set_window_open

<details>
<summary><code>ui.set_window_open(id, open)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string |
| `open` | boolean Follow-mode windows remain hidden while Skeet is closed |

Значения не возвращаются.

</details>

### ui.style_colors

<details>
<summary><code>ui.style_colors(backend)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `backend` | 'menu' |

Результаты:

- string[]

</details>

### ui.translate

<details>
<summary><code>ui.translate(text, id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `text` | string |
| `id?` | string Defaults to the effective menu language |

Результаты:

- string text Unknown language/key returns the original text

</details>

### ui.unregister_language

<details>
<summary><code>ui.unregister_language(id)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string |

Результаты:

- boolean removed Only the owning script can remove a custom dictionary

</details>

### ui.window_bind

<details>
<summary><code>ui.window_bind(id, key)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `id` | string |
| `key?` | integer Query if omitted; 0 follows Skeet, 1..255 independent VK key |

Результаты:

- {key: integer, open: boolean, follows_menu: boolean} bind

</details>

