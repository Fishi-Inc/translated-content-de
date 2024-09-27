---
title: "CustomStateSet: add() Methode"
short-title: add()
slug: Web/API/CustomStateSet/add
l10n:
  sourceCommit: f33c6e8a7204272b90d8f005f3d8c743333d7dbf
---

{{APIRef("Web Components")}}

Die **`add`**-Methode der [`CustomStateSet`](/de/docs/Web/API/CustomStateSet)-Schnittstelle fügt einen Wert, der einen benutzerdefinierten Zustand darstellt, dem `CustomStateSet` hinzu.

Benutzerdefinierte Elemente mit einem bestimmten Zustand können mit der [`:state()`](/de/docs/Web/CSS/:state)-Pseudoklasse ausgewählt werden, indem der gewünschte Zustand als Argument angegeben wird.

## Syntax

```js-nolint
add(value)
```

### Parameter

- `value`
  - : Ein String, der den benutzerdefinierten Zustand darstellt.

### Rückgabewert

Undefiniert.

## Beispiele

Die folgende Funktion fügt den Zustand `checked` einem `CustomStateSet` hinzu.

```js
class MyCustomElement extends HTMLElement {
  set checked(flag) {
    if (flag) {
      this._internals.states.add("checked");
    }
  }
}
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}
