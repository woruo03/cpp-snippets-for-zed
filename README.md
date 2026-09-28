# C++ Snippets for Zed

## Installation

1. Clone this repo
1. Go to the Extensions menu in the Zed IDE
1. Click "Install Dev Extension"
1. Select the folder you cloned

## Available Snippets

### Program Structure

| Prefix  | Description                                |
| ------- | ------------------------------------------ |
| `main`  | `main(int argc, char* argv[])` with return |
| `mains` | Simple `main()` with return                |

### Preprocessor

| Prefix  | Description                                                         |
| ------- | ------------------------------------------------------------------- |
| `inc`   | `#include <...>` system header                                      |
| `incl`  | `#include "..."` local header                                       |
| `once`  | `#pragma once` header guard                                         |
| `guard` | `#ifndef` / `#define` / `#endif` header guard (linked placeholders) |
| `def`   | `#define NAME value` constant                                       |
| `defm`  | `#define NAME(args) (body)` function-like macro                     |

### Control Flow

| Prefix    | Description                                                |
| --------- | ---------------------------------------------------------- |
| `if`      | `if` statement                                             |
| `ifelse`  | `if`-`else` block                                          |
| `elif`    | `else if` statement                                        |
| `ifc`     | `if constexpr` compile-time branch (C++17)                 |
| `ifinit`  | `if (init; condition)` with initializer (C++17)            |
| `for`     | Indexed `for` loop with linked index and `++i`             |
| `forr`    | Reverse indexed `for` loop                                 |
| `fore`    | Range-based `for` loop (`auto&`)                           |
| `forec`   | Range-based `for` loop (`const auto&`)                     |
| `foref`   | Range-based `for` loop with universal reference (`auto&&`) |
| `while`   | `while` loop                                               |
| `dowhile` | `do`-`while` loop                                          |
| `switch`  | `switch` statement with `default`                          |
| `case`    | Single `case` label with `break`                           |

### Functions & Lambdas

| Prefix | Description                           |
| ------ | ------------------------------------- |
| `fn`   | Function definition                   |
| `lam`  | Lambda expression                     |
| `alam` | Lambda assigned to an `auto` variable |

### Classes & Structs (Rule of Zero / Five / Move-Only)

| Prefix        | Description                                                                |
| ------------- | -------------------------------------------------------------------------- |
| `class`       | Class definition following **Rule of Zero**                                |
| `class5`      | Class definition following **Rule of Five/Six** (explicit special members) |
| `classm`      | Move-only class definition (`delete` copy, `= default` move)               |
| `classi`      | Abstract interface class with virtual destructor and pure virtual method   |
| `struct`      | Struct definition (plain aggregate / Rule of Zero)                         |
| `struct5`     | Struct definition following **Rule of Five** (explicit special members)    |
| `structm`     | Move-only struct definition (`delete` copy, `= default` move)              |
| `struct_cmp`  | Comparator struct for STL containers and algorithms                        |
| `struct_hash` | Hash struct for custom types in unordered containers                       |
| `enum`        | Scoped `enum class` definition                                             |
| `ctor`        | Constructor with member-initializer list                                   |
| `dtor`        | Destructor definition                                                      |
| `vdtor`       | Virtual destructor definition for base classes                             |
| `cctor`       | Copy constructor                                                           |
| `mctor`       | Move constructor (`noexcept`)                                              |
| `casgn`       | Copy assignment `operator=`                                                |
| `masgn`       | Move assignment `operator=` (`noexcept`)                                   |
| `rule3`       | Rule of three with default constructor                                     |
| `rule5`       | Rule of five/six with default constructor                                  |
| `nocopy`      | Non-copyable — `delete` copy constructor and copy assignment               |
| `nomove`      | Non-movable — `delete` move constructor and move assignment                |
| `moveonly`    | Move-only member declarations (`delete` copy, `= default` move)            |
| `swap`        | Friend `swap` function for Copy-and-Swap idiom                             |
| `virt`        | `virtual` method declaration in base class                                 |
| `ov`          | `override` method definition in derived class                              |
| `pv`          | Pure `virtual` method declaration (`= 0`)                                  |

### Templates & Concepts

| Prefix         | Description                                                            |
| -------------- | ---------------------------------------------------------------------- |
| `tfn`          | Template function                                                      |
| `tclass`       | Template class (Rule of Zero)                                          |
| `tclass5`      | Template class following **Rule of Five** (explicit special members)   |
| `tclassm`      | Template move-only class definition (`delete` copy, `= default` move)  |
| `tclass_req`   | Template class with C++20 `requires` concept constraint                |
| `tclass_spec`  | Full template class specialization                                     |
| `tstruct`      | Template struct (Rule of Zero)                                         |
| `tstruct5`     | Template struct following **Rule of Five** (explicit special members)  |
| `tstructm`     | Template move-only struct definition (`delete` copy, `= default` move) |
| `tstruct_req`  | Template struct with C++20 `requires` concept constraint               |
| `tstruct_spec` | Template struct specialization (e.g. type traits)                      |
| `thash`        | Specialization of `std::hash<T>` for custom types                      |
| `tfmt`         | Specialization of `std::formatter<T>` for `std::format` (C++20)        |
| `concept`      | C++20 `concept` definition                                             |
| `requires`     | C++20 `requires` expression clause                                     |

### Smart Pointers

| Prefix  | Description                          |
| ------- | ------------------------------------ |
| `uptr`  | `std::make_unique<T>(...)` → `auto`  |
| `uptrd` | `std::unique_ptr<T>` declaration     |
| `sptr`  | `std::make_shared<T>(...)` → `auto`  |
| `sptrd` | `std::shared_ptr<T>` declaration     |
| `wptr`  | `std::weak_ptr<T>` from a shared_ptr |

### STL Containers & Views

| Prefix   | Description                |
| -------- | -------------------------- |
| `vec`    | `std::vector<T>`           |
| `arr`    | `std::array<T, N>`         |
| `umap`   | `std::unordered_map<K, V>` |
| `map`    | `std::map<K, V>`           |
| `uset`   | `std::unordered_set<T>`    |
| `set`    | `std::set<T>`              |
| `queue`  | `std::queue<T>`            |
| `pqueue` | `std::priority_queue<T>`   |
| `stack`  | `std::stack<T>`            |
| `deque`  | `std::deque<T>`            |
| `str`    | `std::string`              |
| `sv`     | `std::string_view` (C++17) |
| `span`   | `std::span<T>` (C++20)     |
| `opt`    | `std::optional<T>`         |
| `vari`   | `std::variant<...>`        |
| `pair`   | `std::pair<F, S>`          |
| `tup`    | `std::tuple<...>`          |

### I/O

| Prefix    | Description                                          |
| --------- | ---------------------------------------------------- |
| `cout`    | `std::cout << ... << '\n'`                           |
| `cin`     | `std::cin >> ...`                                    |
| `cerr`    | `std::cerr << ... << '\n'` for errors                |
| `getline` | `std::getline(std::cin, str)`                        |
| `println` | `std::println("...", args)` formatted print (C++23)  |
| `print`   | `std::print("...", args)` formatted print (C++23)    |
| `fmt`     | `std::format("...", args)` string formatting (C++20) |
| `fastio`  | Fast I/O setup for competitive programming           |

### Concurrency & Multi-threading

| Prefix    | Description                                        |
| --------- | -------------------------------------------------- |
| `thread`  | `std::thread` definition                           |
| `jthread` | `std::jthread` auto-joining thread (C++20)         |
| `lock`    | `std::scoped_lock` RAII multi-lock (C++17)         |
| `slock`   | `std::shared_lock` for `std::shared_mutex` (C++17) |
| `ulock`   | `std::unique_lock<std::mutex>`                     |
| `mtx`     | `std::mutex` declaration                           |
| `smtx`    | `std::shared_mutex` declaration (C++17)            |
| `atomic`  | `std::atomic<T>` declaration                       |
| `cv`      | `std::condition_variable` declaration              |

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
| `ceval`   | `consteval` immediate function (C++20)     |
| `sassert` | `static_assert` with message               |
| `assert`  | `assert(condition)` (requires `<cassert>`) |

### Casts

| Prefix  | Description                                                 |
| ------- | ----------------------------------------------------------- |
| `scast` | `static_cast<T>(expr)`                                      |
| `dcast` | `if (auto* ptr = dynamic_cast<T*>(expr))` with scoped check |
| `rcast` | `reinterpret_cast<T>(expr)`                                 |
| `ccast` | `const_cast<T>(expr)`                                       |

### Algorithms & Utilities

| Prefix       | Description                                        |
| ------------ | -------------------------------------------------- |
| `sort`       | `std::sort` on a container                         |
| `rsort`      | `std::ranges::sort` on a container (C++20)         |
| `find`       | `std::find` with iterator check                    |
| `rfind`      | `std::ranges::find` with iterator check (C++20)    |
| `transform`  | `std::transform` with a lambda and return          |
| `sbd`        | Structured binding `auto [a, b] = ...` (C++17)     |
| `move`       | `std::move(var)` cast                              |
| `fwd`        | `std::forward<T>(arg)` perfect forwarding          |
| `timeit`     | Duration timing block with `std::chrono`           |
| `overloaded` | Overloaded lambda visitor pattern for `std::visit` |

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
