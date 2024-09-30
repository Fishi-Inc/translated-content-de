---
title: Not equal
slug: WebAssembly/Reference/Numeric/Not_equal
l10n:
  sourceCommit: c681ed89305afd56d54ba6671673680bea041670
---

{{WebAssemblySidebar}}

Die **`ne`**-Instruktionen, kurz für _nicht gleich_, prüfen, ob zwei Zahlen nicht gleich sind. Wenn die Zahlen nicht gleich sind, wird `1` auf den Stapel gelegt, andernfalls wird `0` auf den Stapel gelegt.

{{EmbedInteractiveExample("pages/wat/ne.html", "tabbed-taller")}}

## Syntax

```wasm
;; load 2 numbers on to the stack
local.get $num
i32.const 2

;; check if $num is not equal to '2'
i32.ne

;; if $num is not equal to `2`, `1` will be pushed on to the stack,
;; otherwise `0` will be pushed on to the stack.
```

| Instruktion | Binärer Opcode |
| ----------- | -------------- |
| `i32.ne`    | `0x47`         |
| `i64.ne`    | `0x52`         |
| `f32.ne`    | `0x5c`         |
| `f64.ne`    | `0x62`         |
