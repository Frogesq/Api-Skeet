# audio

Звук. [Все модули](../API_INDEX.ru.md) · [Условия использования](../SERVICES.ru.md) · [Типы](../TYPES.ru.md).

- [audio.play](#audioplay)
- [audio.preload](#audiopreload)
- [audio.stop](#audiostop)
- [audio.volume](#audiovolume)

### audio.play

<details>
<summary><code>audio.play(basename, loop)</code></summary>

Prepared play uses retained PCM/voice. The first unprepared play loads synchronously.

| Аргумент | Тип и условия |
|---|---|
| `basename` | string MP3/WAV basename under %LOCALAPPDATA%/skeet/muzon, or sounds/<basename>.mp3/.wav under %LOCALAPPDATA%/skeet/sounds. |
| `loop?` | boolean Repeat until stopped. |

Результаты:

- boolean ok
- string? error

</details>

### audio.preload

<details>
<summary><code>audio.preload(basename)</code></summary>

Prepare once at top level during script loading. No playback is started.

| Аргумент | Тип и условия |
|---|---|
| `basename` | string MP3/WAV basename in muzon, or sounds/<basename>.mp3/.wav. Encoded file <=64 MiB; decoded PCM <=128 MiB. |

Результаты:

- boolean ok
- string? error

</details>

### audio.stop

<details>
<summary><code>audio.stop()</code></summary>

Stop playback but retain prepared sounds until script unload.

Значения не возвращаются.

</details>

### audio.volume

<details>
<summary><code>audio.volume(percent)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `percent` | number Finite; clamped to 0..100. Per-script volume, also accepted before playback. |

Результаты:

- boolean ok

</details>

