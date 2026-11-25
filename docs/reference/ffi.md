# ffi

Native FFI. [Все модули](../FFI_INDEX.ru.md) · [Условия использования](../FFI.ru.md) · [Типы](../TYPES.ru.md).

- [ffi.abi](#ffiabi)
- [ffi.addressof](#ffiaddressof)
- [ffi.alignof](#ffialignof)
- [ffi.cast](#fficast)
- [ffi.cdef](#fficdef)
- [ffi.copy](#fficopy)
- [ffi.errno](#ffierrno)
- [ffi.eval](#ffieval)
- [ffi.fill](#ffifill)
- [ffi.gc](#ffigc)
- [ffi.istype](#ffiistype)
- [ffi.load](#ffiload)
- [ffi.metatype](#ffimetatype)
- [ffi.new](#ffinew)
- [ffi.offsetof](#ffioffsetof)
- [ffi.sizeof](#ffisizeof)
- [ffi.string](#ffistring)
- [ffi.tonumber](#ffitonumber)
- [ffi.toretval](#ffitoretval)
- [ffi.type](#ffitype)
- [ffi.typeof](#ffitypeof)

### ffi.abi

<details>
<summary><code>ffi.abi(flag)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `flag` | string |

Результаты:

- boolean

</details>

### ffi.addressof

<details>
<summary><code>ffi.addressof(value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value` | CData |

Результаты:

- CData pointer

</details>

### ffi.alignof

<details>
<summary><code>ffi.alignof(value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value` | CData&#124;string&#124;CType |

Результаты:

- integer

</details>

### ffi.cast

<details>
<summary><code>ffi.cast(ctype, value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `ctype` | string&#124;CType |
| `value` | any |

Результаты:

- CData

</details>

### ffi.cdef

<details>
<summary><code>ffi.cdef(declarations, ...)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `declarations` | string |

Значения не возвращаются.

</details>

### ffi.copy

<details>
<summary><code>ffi.copy(destination, source, length)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `destination` | CData |
| `source` | CData&#124;string |
| `length?` | integer |

Значения не возвращаются.

</details>

### ffi.errno

<details>
<summary><code>ffi.errno(value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value?` | integer |

Результаты:

- integer

</details>

### ffi.eval

<details>
<summary><code>ffi.eval(literal)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `literal` | string Numeric literal; not a C expression evaluator. |

Результаты:

- CData

</details>

### ffi.fill

<details>
<summary><code>ffi.fill(destination, length, byte)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `destination` | CData |
| `length` | integer |
| `byte?` | integer |

Значения не возвращаются.

</details>

### ffi.gc

<details>
<summary><code>ffi.gc(value, finalizer)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value` | CData |
| `finalizer?` | fun(value: CData) nil removes finalizer. |

Результаты:

- CData

</details>

### ffi.istype

<details>
<summary><code>ffi.istype(ctype, value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `ctype` | string&#124;CType |
| `value` | CData |

Результаты:

- boolean

</details>

### ffi.load

<details>
<summary><code>ffi.load(name, global)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `name` | string UTF-8 DLL name/path on Windows. |
| `global?` | boolean |

Результаты:

- CLibrary

</details>

### ffi.metatype

<details>
<summary><code>ffi.metatype(ctype, metatable)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `ctype` | string&#124;CType |
| `metatable` | table |

Результаты:

- CType

</details>

### ffi.new

<details>
<summary><code>ffi.new(ctype, ...)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `ctype` | string&#124;CType |

Результаты:

- CData

</details>

### ffi.offsetof

<details>
<summary><code>ffi.offsetof(ctype, field)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `ctype` | string&#124;CType |
| `field` | string |

Результаты:

- integer?

</details>

### ffi.sizeof

<details>
<summary><code>ffi.sizeof(value, ...)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value` | CData&#124;string&#124;CType |

Результаты:

- integer? nil when size is unknown.

</details>

### ffi.string

<details>
<summary><code>ffi.string(value, length)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value` | CData |
| `length?` | integer |

Результаты:

- string

</details>

### ffi.tonumber

<details>
<summary><code>ffi.tonumber(value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value` | CData&#124;number&#124;string |

Результаты:

- number?

</details>

### ffi.toretval

<details>
<summary><code>ffi.toretval(value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value` | CData |

Результаты:

- any

</details>

### ffi.type

<details>
<summary><code>ffi.type(value)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `value` | any |

Результаты:

- string 'cdata' for CData/CType, otherwise the ordinary Lua type.

</details>

### ffi.typeof

<details>
<summary><code>ffi.typeof(ctype, ...)</code></summary>

| Аргумент | Тип и условия |
|---|---|
| `ctype` | string&#124;CType |

Результаты:

- CType

</details>

