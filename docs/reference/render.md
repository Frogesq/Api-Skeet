# render

Графика. [Все модули](../API_INDEX.ru.md) · [Условия использования](../RENDER.ru.md) · [Типы](../TYPES.ru.md).

- [render.arc](#renderarc)
- [render.builtin_font](#renderbuiltin_font)
- [render.circle](#rendercircle)
- [render.circle_3d](#rendercircle_3d)
- [render.circle_fade](#rendercircle_fade)
- [render.circle_fade_3d](#rendercircle_fade_3d)
- [render.circle_filled_3d](#rendercircle_filled_3d)
- [render.concave_polygon](#renderconcave_polygon)
- [render.create_texture_rgba](#rendercreate_texture_rgba)
- [render.frame_count](#renderframe_count)
- [render.frame_time](#renderframe_time)
- [render.grenade_icon](#rendergrenade_icon)
- [render.line](#renderline)
- [render.measure_text](#rendermeasure_text)
- [render.menu_icon](#rendermenu_icon)
- [render.panel](#renderpanel)
- [render.poly_line](#renderpoly_line)
- [render.polygon](#renderpolygon)
- [render.pop_clip_rect](#renderpop_clip_rect)
- [render.push_clip_rect](#renderpush_clip_rect)
- [render.rect](#renderrect)
- [render.rect_filled_fade](#renderrect_filled_fade)
- [render.screen_size](#renderscreen_size)
- [render.setup_font](#rendersetup_font)
- [render.setup_texture](#rendersetup_texture)
- [render.setup_texture_from_memory](#rendersetup_texture_from_memory)
- [render.setup_texture_rgba](#rendersetup_texture_rgba)
- [render.text](#rendertext)
- [render.texture](#rendertexture)
- [render.texture_rotated](#rendertexture_rotated)
- [render.texture_size](#rendertexture_size)
- [render.update_texture_pixels](#renderupdate_texture_pixels)
- [render.update_texture_rgba](#renderupdate_texture_rgba)
- [render.world_to_screen](#renderworld_to_screen)

### render.arc

<details>
<summary><code>render.arc(x, y, radius, start_angle, end_angle, color, thickness, segments)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `x` | number |
| `y` | number |
| `radius` | number |
| `start_angle` | number Radians. |
| `end_angle` | number Radians. |
| `color` | Color |
| `thickness?` | number Default 1. |
| `segments?` | integer 2..256, default 64. |

Значения не возвращаются.

</details>

### render.builtin_font

<details>
<summary><code>render.builtin_font(target, font)</code></summary>

Override built-in ESP label fonts. The legacy watermark target is accepted for script compatibility. Call in paint; pass nil to release this script's override.

| Аргумент | Тип и условия |
|---|---|
| `target` | 'esp'&#124;'watermark' |
| `font?` | integer |

Значения не возвращаются.

</details>

### render.circle

<details>
<summary><code>render.circle(x, y, radius, color, filled)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `x` | number |
| `y` | number |
| `radius` | number |
| `color` | Color |
| `filled?` | boolean |

Значения не возвращаются.

</details>

### render.circle_3d

<details>
<summary><code>render.circle_3d(position, radius, color, normal)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `position` | Vector3 |
| `radius` | number |
| `color` | Color |
| `normal?` | Vector3 Default {x=0,y=0,z=1}. |

Значения не возвращаются.

</details>

### render.circle_fade

<details>
<summary><code>render.circle_fade(x, y, radius, inside, outside)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `x` | number |
| `y` | number |
| `radius` | number |
| `inside` | Color |
| `outside` | Color |

Значения не возвращаются.

</details>

### render.circle_fade_3d

<details>
<summary><code>render.circle_fade_3d(position, radius, inside, outside, normal)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `position` | Vector3 |
| `radius` | number |
| `inside` | Color |
| `outside` | Color |
| `normal?` | Vector3 |

Значения не возвращаются.

</details>

### render.circle_filled_3d

<details>
<summary><code>render.circle_filled_3d(position, radius, color, normal)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `position` | Vector3 |
| `radius` | number |
| `color` | Color |
| `normal?` | Vector3 |

Значения не возвращаются.

</details>

### render.concave_polygon

<details>
<summary><code>render.concave_polygon(points, color)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `points` | Vector2[] Same contract as polygon. |
| `color` | Color |

Значения не возвращаются.

</details>

### render.create_texture_rgba

<details>
<summary><code>render.create_texture_rgba(width, height)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `width` | integer 1..4096; total pixels <=1048576. |
| `height` | integer |

Результаты:

- integer? texture Mutable, private to this script; retained/reused after unload.
- string? error

</details>

### render.frame_count

<details>
<summary><code>render.frame_count()</code></summary>

Результаты:

- integer count Number of scripting paint passes since DLL initialization.

</details>

### render.frame_time

<details>
<summary><code>render.frame_time()</code></summary>

Результаты:

- number seconds

</details>

### render.grenade_icon

<details>
<summary><code>render.grenade_icon(kind)</code></summary>

Native grenade artwork, paint only; same owned texture handle as render.texture. One cached raster per kind.

| Аргумент | Тип и условия |
|---|---|
| `kind` | 'hegrenade'&#124;'flashbang'&#124;'smokegrenade'&#124;'molotov'&#124;'incgrenade'&#124;'decoy' |

Результаты:

- integer? handle
- integer&#124;string width_or_error
- integer? height

</details>

### render.line

<details>
<summary><code>render.line(x1, y1, x2, y2, color, thickness)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `x1` | number |
| `y1` | number |
| `x2` | number |
| `y2` | number |
| `color` | Color |
| `thickness?` | number |

Значения не возвращаются.

</details>

### render.measure_text

<details>
<summary><code>render.measure_text(text, font)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `text` | string |
| `font?` | integer Custom fonts require paint. |

Результаты:

- number width
- number height

</details>

### render.menu_icon

<details>
<summary><code>render.menu_icon(name)</code></summary>

Menu artwork during paint. Use extensions, rage/<profile key> or legit/<category key>.

| Аргумент | Тип и условия |
|---|---|
| `name` | string |

Результаты:

- integer? handle
- integer&#124;string width_or_error
- integer? height

</details>

### render.panel

<details>
<summary><code>render.panel(x, y, width, height, color, rounding, blur, shadow, border)</code></summary>

Draws a rounded panel during paint. Blur samples the scene before applying the fill.

| Аргумент | Тип и условия |
|---|---|
| `x` | number |
| `y` | number |
| `width` | number |
| `height` | number |
| `color` | Color Use a translucent fill to reveal the scene. |
| `rounding?` | number Corner radius in pixels. |
| `blur?` | number Gaussian blur strength from 0 to 1. Zero disables blur. |
| `shadow?` | boolean Draw the menu window shadow. |
| `border?` | Color Optional rounded outline. |

Значения не возвращаются.

</details>

### render.poly_line

<details>
<summary><code>render.poly_line(points, color, thickness, closed)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `points` | Vector2[] 2..256 points. |
| `color` | Color |
| `thickness?` | number 0.1..100, default 1. |
| `closed?` | boolean Default false. |

Значения не возвращаются.

</details>

### render.polygon

<details>
<summary><code>render.polygon(points, color)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `points` | Vector2[] 3..256 vertices; simple polygon without holes. |
| `color` | Color |

Значения не возвращаются.

</details>

### render.pop_clip_rect

<details>
<summary><code>render.pop_clip_rect()</code></summary>

Значения не возвращаются.

</details>

### render.push_clip_rect

<details>
<summary><code>render.push_clip_rect(x, y, width, height)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `x` | number |
| `y` | number |
| `width` | number |
| `height` | number |

Значения не возвращаются.

</details>

### render.rect

<details>
<summary><code>render.rect(x, y, width, height, color, filled)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `x` | number |
| `y` | number |
| `width` | number |
| `height` | number |
| `color` | Color |
| `filled?` | boolean |

Значения не возвращаются.

</details>

### render.rect_filled_fade

<details>
<summary><code>render.rect_filled_fade(x, y, w, h, tl, tr, br, bl)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `x` | number |
| `y` | number |
| `w` | number |
| `h` | number |
| `tl` | Color |
| `tr` | Color |
| `br` | Color |
| `bl` | Color |

Значения не возвращаются.

</details>

### render.screen_size

<details>
<summary><code>render.screen_size()</code></summary>

Результаты:

- integer width
- integer height

</details>

### render.setup_font

<details>
<summary><code>render.setup_font(basename, size, sizing, hinting)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `basename` | string TTF/OTF under config_dir/resources/<basename>, or fonts/<basename> under config_dir/fonts. |
| `size` | number 6..96 pixels. |
| `sizing?` | "real_dim"&#124;"nominal" Default real_dim. Nominal uses the Unicode charmap and a 72 DPI character size. |
| `hinting?` | "auto"&#124;"native" Default auto. Native uses font outlines and the font's own hints. |

Результаты:

- integer? font
- string? error Resource failure code; nil on success.

</details>

### render.setup_texture

<details>
<summary><code>render.setup_texture(basename)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `basename` | string File under config_dir/resources/<basename>, or skeetles/name.png under config_dir/skeetles; at most 4 MiB. |

Результаты:

- integer? texture Handle; nil on missing/unsupported image.
- string? error Resource failure code; nil on success.

</details>

### render.setup_texture_from_memory

<details>
<summary><code>render.setup_texture_from_memory(bytes)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `bytes` | string Binary encoded image, at most 4 MiB. |

Результаты:

- integer? texture
- string? error Resource failure code; nil on success.

</details>

### render.setup_texture_rgba

<details>
<summary><code>render.setup_texture_rgba(bytes, width, height)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `bytes` | string Raw RGBA bytes; exactly width*height*4. |
| `width` | integer 1..4096, total pixels at most 1048576. |
| `height` | integer 1..4096 |

Результаты:

- integer? texture
- string? error Resource failure code; nil on success.

</details>

### render.text

<details>
<summary><code>render.text(x, y, text, color, font)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `x` | number |
| `y` | number |
| `text` | string |
| `color` | Color |
| `font?` | integer Handle obtained by this script in paint. |

Значения не возвращаются.

</details>

### render.texture

<details>
<summary><code>render.texture(texture, x, y, width, height, tint, rounding)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `texture` | integer Handle returned to this script. |
| `x` | number |
| `y` | number |
| `width` | number |
| `height` | number |
| `tint?` | Color Default white. |
| `rounding?` | number Default 0. |

Значения не возвращаются.

</details>

### render.texture_rotated

<details>
<summary><code>render.texture_rotated(texture, center_x, center_y, width, height, angle, tint)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `texture` | integer Handle returned to this script. |
| `center_x` | number Rotation center in screen pixels. |
| `center_y` | number Rotation center in screen pixels. |
| `width` | number Drawn width. |
| `height` | number Drawn height. |
| `angle` | number Clockwise rotation in radians. |
| `tint?` | Color Default white. |

Значения не возвращаются.

</details>

### render.texture_size

<details>
<summary><code>render.texture_size(texture)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `texture` | integer Handle returned to this script. |

Результаты:

- integer width Original pixel width.
- integer height Original pixel height.

</details>

### render.update_texture_pixels

<details>
<summary><code>render.update_texture_pixels(texture, bytes, format, pitch)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `texture` | integer Handle from render.create_texture_rgba. |
| `bytes` | string Pixel bytes, <=4 MiB; at least pitch*(height-1)+row_bytes, at most pitch*height. |
| `format` | 'rgba8'&#124;'bgra8'&#124;'bgrx8'&#124;'rgb565'&#124;'rgb555' 16-bit formats use little-endian words. |
| `pitch?` | integer Bytes per source row; default tightly packed; >=width*bytes_per_pixel. |

Результаты:

- boolean? success
- string? error Resource error; invalid arguments raise a Lua error.

</details>

### render.update_texture_rgba

<details>
<summary><code>render.update_texture_rgba(texture, bytes)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `texture` | integer Handle from render.create_texture_rgba. |
| `bytes` | string Exactly width*height*4 RGBA bytes; call before drawing this frame. |

Результаты:

- boolean? success
- string? error

</details>

### render.world_to_screen

<details>
<summary><code>render.world_to_screen(world)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `world` | Vector3 |

Результаты:

- number? x
- number? y
- boolean? on_screen

</details>

