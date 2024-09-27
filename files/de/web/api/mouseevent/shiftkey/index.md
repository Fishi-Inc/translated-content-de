---
title: "MouseEvent: shiftKey-Eigenschaft"
short-title: shiftKey
slug: Web/API/MouseEvent/shiftKey
l10n:
  sourceCommit: ef75c1741b450c2331204be5563ee964ad5f4c48
---

{{APIRef("UI Events")}}

Die schreibgeschützte Eigenschaft **`MouseEvent.shiftKey`** ist ein boolescher Wert, der anzeigt, ob die <kbd>Umschalt</kbd>-Taste gedrückt war oder nicht, als ein bestimmtes Mausereignis auftrat.

## Wert

Ein boolescher Wert, wobei `true` anzeigt, dass die Taste gedrückt ist, und `false` anzeigt, dass die Taste _nicht_ gedrückt ist.

## Beispiele

Dieses Beispiel protokolliert die `shiftKey`-Eigenschaft, wenn Sie ein [`click`](/de/docs/Web/API/Element/click_event)-Ereignis auslösen.

### HTML

```html
<p>Click anywhere to test the <code>shiftKey</code> property.</p>
<p id="log"></p>
```

### JavaScript

```js
let log = document.querySelector("#log");
document.addEventListener("click", logKey);

function logKey(e) {
  log.textContent = `The shift key is pressed: ${e.shiftKey}`;
}
```

### Ergebnis

{{EmbedLiveSample("Examples")}}

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [`MouseEvent`](/de/docs/Web/API/MouseEvent)
