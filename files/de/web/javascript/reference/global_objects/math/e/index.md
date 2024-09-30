---
title: Math.E
slug: Web/JavaScript/Reference/Global_Objects/Math/E
l10n:
  sourceCommit: 761b9047d78876cbd153be811efb1aa77b419877
---

{{JSRef}}

Die statische Dateneigenschaft **`Math.E`** repräsentiert die Eulersche Zahl, die Basis der natürlichen Logarithmen, e, die ungefähr 2,718 beträgt.

{{EmbedInteractiveExample("pages/js/math-e.html")}}

## Wert

<!-- prettier-ignore-start -->
<math display="block">
  <semantics><mrow><mi>𝙼𝚊𝚝𝚑.𝙴</mi><mo>=</mo><mi>e</mi><mo>≈</mo><mn>2.718</mn></mrow><annotation encoding="TeX">\mathtt{Math.E} = e \approx 2.718</annotation></semantics>
</math>
<!-- prettier-ignore-end -->

{{js_property_attributes(0, 0, 0)}}

## Beschreibung

Da `E` eine statische Eigenschaft von `Math` ist, wird sie immer als `Math.E` verwendet und nicht als Eigenschaft eines neu erstellten `Math`-Objekts (da `Math` kein Konstruktor ist).

## Beispiele

### Verwendung von Math.E

Die folgende Funktion gibt e zurück:

```js
function getNapier() {
  return Math.E;
}

getNapier(); // 2.718281828459045
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- {{jsxref("Math.exp()")}}
- {{jsxref("Math.log()")}}
- {{jsxref("Math.log1p()")}}
