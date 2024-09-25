---
title: "MutationEvent: attrName-Eigenschaft"
short-title: attrName
slug: Web/API/MutationEvent/attrName
l10n:
  sourceCommit: acfe8c9f1f4145f77653a2bc64a9744b001358dc
---

{{APIRef("UI Events")}}{{Deprecated_Header}}

Die **`attrName`** schreibgeschützte Eigenschaft des {{domxref("MutationEvent")}}-Interfaces gibt einen String mit dem Namen des Knotens zurück, der vom `DOMAttrModified`-Ereignis betroffen ist. Für andere Ereignisse hat sie keine Bedeutung und wird dann auf den leeren String (`""`) gesetzt.

## Wert

Ein String.

## Beispiele

```js
element.addEventListener(
  "DOMAttrModified",
  (event) => {
    console.log(event.attrName);
  },
  false,
);
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}
