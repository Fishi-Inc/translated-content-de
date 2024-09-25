---
title: "HTMLFieldSetElement: name-Eigenschaft"
short-title: name
slug: Web/API/HTMLFieldSetElement/name
l10n:
  sourceCommit: d064784c78ec30c87ec3c3d9681b147999fd782f
---

{{ApiRef("HTML DOM")}}

Die **`name`**-Eigenschaft der {{domxref("HTMLFieldSetElement")}}-Schnittstelle gibt den Namen des {{HTMLElement("fieldset")}}-Elements an. Sie spiegelt das [`name`](/de/docs/Web/HTML/Element/fieldset#name) Attribut des Elements wider.

## Wert

Ein String, der den Namen des Elements darstellt.

## Beispiel

```js
const fs = document.querySelector("fieldset");
console.log(`Element's name: ${fs.name}`);
fs.name = "billing"; // sets or updates the element's name
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- {{domxref("HTMLFieldSetElement.elements")}}
- {{domxref("HTMLFieldSetElement.disabled")}}
- {{domxref("HTMLLegendElement")}}
- {{domxref("HTMLFormElement")}}
- {{HTMLElement("fieldset")}}
- {{HTMLElement("legend")}}
- {{HTMLElement("form")}}
