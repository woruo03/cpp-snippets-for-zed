# C++ Snippets for Zed

## Installation

1. Clone this repo:

```shell
git clone https://github.com/woruo03/cpp-snippets-for-zed
```

2. Go to the Extensions menu in the Zed IDE
3. Click "Install Dev Extension"
4. Select the folder you cloned

## Available Snippets

### Program Structure

| Prefix  | Description                                |
| ------- | ------------------------------------------ |
| `main`  | `main(int argc, char* argv[])` with return |
| `mains` | Simple `main()` with return                |

### Preprocessor

| Prefix    | Description                                                         |
| --------- | ------------------------------------------------------------------- |
| `include` | `#include <...>`                                                    |
| `incs`    | `#include <...>` with placeholder                                   |
| `incl`    | `#include "..."` local header                                       |
| `once`    | `#pragma once` header guard                                         |
| `guard`   | `#ifndef` / `#define` / `#endif` header guard (linked placeholders) |
| `def`     | `#define NAME value` constant                                       |
| `defm`    | `#define NAME(args) (body)` function-like macro                     |

### Control Flow

| Prefix    | Description                                                |
| --------- | ---------------------------------------------------------- |
| `if`      | `if` statement                                             |
| `ifelse`  | `if`-`else` block                                          |
| `for`     | Indexed `for` loop (loop variable is a linked placeholder) |
| `forr`    | Reverse indexed `for` loop                                 |
| `fore`    | Range-based `for` loop (`auto&`)                           |
| `forec`   | Range-based `for` loop (`const auto&`)                     |
| `while`   | `while` loop                                               |
| `dowhile` | `do`-`while` loop                                          |
| `switch`  | `switch` statement with `default`                          |
| `case`    | Single `case` label with `break`                           |

### Functions

| Prefix | Description                           |
| ------ | ------------------------------------- |
| `fn`   | Function definition                   |
| `lam`  | Lambda expression                     |
| `alam` | Lambda assigned to an `auto` variable |

### Classes & OOP

| Prefix   | Description                                                    |
| -------- | -------------------------------------------------------------- |
| `class`  | Class definition with `public` / `private` sections            |
| `struct` | Struct definition                                              |
| `enum`   | Scoped `enum class` definition                                 |
| `ctor`   | Constructor with member-initializer list                       |
| `dtor`   | Destructor                                                     |
| `cctor`  | Copy constructor                                               |
| `mctor`  | Move constructor (`noexcept`)                                  |
| `casgn`  | Copy assignment `operator=`                                    |
| `masgn`  | Move assignment `operator=` (`noexcept`)                       |
| `rule5`  | Rule of five — all five special members explicitly `= default` |
| `nocopy` | Non-copyable — `delete` copy constructor and copy assignment   |
| `virt`   | `virtual override` method                                      |
| `pv`     | Pure `virtual` method (`= 0`)                                  |

### Templates

| Prefix    | Description                |
| --------- | -------------------------- |
| `tfn`     | Template function          |
| `tcls`    | Template class             |
| `concept` | C++20 `concept` definition |

### Smart Pointers

| Prefix | Description                          |
| ------ | ------------------------------------ |
| `uptr` | `std::make_unique<T>(...)` → `auto`  |
| `sptr` | `std::make_shared<T>(...)` → `auto`  |
| `wptr` | `std::weak_ptr<T>` from a shared_ptr |

### STL Containers & Types

| Prefix | Description                |
| ------ | -------------------------- |
| `vec`  | `std::vector<T>`           |
| `arr`  | `std::array<T, N>`         |
| `umap` | `std::unordered_map<K, V>` |
| `map`  | `std::map<K, V>`           |
| `str`  | `std::string`              |
| `opt`  | `std::optional<T>`         |
| `vari` | `std::variant<...>`        |
| `pair` | `std::pair<F, S>`          |
| `tup`  | `std::tuple<...>`          |

### I/O

| Prefix | Description                           |
| ------ | ------------------------------------- |
| `cout` | `std::cout << ... << '\n'`            |
| `cin`  | `std::cin >> ...`                     |
| `cerr` | `std::cerr << ... << '\n'` for errors |

### Error Handling

| Prefix  | Description                  |
| ------- | ---------------------------- |
| `try`   | `try`-`catch` block          |
| `catch` | `catch` block                |
| `throw` | `throw` a standard exception |

### Namespaces & Aliases

| Prefix  | Description                            |
| ------- | -------------------------------------- |
| `ns`    | `namespace` block with closing comment |
| `using` | `using Alias = Type` type alias        |

### Compile-time

| Prefix    | Description                                |
| --------- | ------------------------------------------ |
| `cxpr`    | `constexpr` variable                       |
| `cxfn`    | `constexpr` function                       |
| `sassert` | `static_assert` with message               |
| `assert`  | `assert(condition)` (requires `<cassert>`) |

### Casts

| Prefix  | Description                                 |
| ------- | ------------------------------------------- |
| `scast` | `static_cast<T>(expr)`                      |
| `dcast` | `dynamic_cast<T*>(expr)` with nullptr check |
| `rcast` | `reinterpret_cast<T>(expr)`                 |

### Algorithms & Utilities

| Prefix      | Description                                    |
| ----------- | ---------------------------------------------- |
| `sort`      | `std::sort` on a container                     |
| `find`      | `std::find` with iterator check                |
| `transform` | `std::transform` with a lambda                 |
| `sbd`       | Structured binding `auto [a, b] = ...` — C++17 |

## Recommend

### Problem

When expanding a snippet in Zed, typing inside a placeholder (like `$1`) opens
the completion popup (`showing_completions`). At this point, pressing `Tab`
triggers code completion instead of moving to the next snippet tabstop (`$2`),
breaking the flow. Standard `Ctrl+J` also defaults to toggling the bottom dock.

### Solution

Add the following rule to `~/.config/zed/keymap.json` to allow `Ctrl+J` and
`Ctrl+K` to bypass completion popups and jump between snippet placeholders
seamlessly:

```json
[
    {
        "context": "Editor",
        "bindings": {
            "ctrl-j": "editor::NextSnippetTabstop",
            "ctrl-k": "editor::PreviousSnippetTabstop"
        }
    }
]
```
