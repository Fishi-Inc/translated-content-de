---
title: Math.asin()
slug: Web/JavaScript/Reference/Global_Objects/Math/asin
l10n:
  sourceCommit: 761b9047d78876cbd153be811efb1aa77b419877
---

{{JSRef}}

Die **`Math.asin()`** statische Methode gibt den Arkussinus (in Radiant) einer Zahl zurück. Das heißt,

<!-- prettier-ignore-start -->
<math display="block">
  <semantics><mrow><mo>∀</mo><mi>x</mi><mo>∊</mo><mo stretchy="false">[</mo><mrow><mo>−</mo><mn>1</mn></mrow><mo>,</mo><mn>1</mn><mo stretchy="false">]</mo><mo>,</mo><mspace width="0.2777777777777778em"></mspace><mrow><mo lspace="0em" rspace="0.16666666666666666em">𝙼𝚊𝚝𝚑.𝚊𝚜𝚒𝚗</mo><mo stretchy="false">(</mo><mi>𝚡</mi><mo stretchy="false">)</mo></mrow><mo>=</mo><mo lspace="0em" rspace="0em">arcsin</mo><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo><mo>=</mo><mtext>der eindeutige&nbsp;</mtext><mi>y</mi><mo>∊</mo><mrow><mo>[</mo><mrow><mo>−</mo><mfrac><mi>π</mi><mn>2</mn></mfrac><mo>,</mo><mfrac><mi>π</mi><mn>2</mn></mfrac></mrow><mo>]</mo></mrow><mtext>&nbsp;so dass&nbsp;</mtext><mo lspace="0em" rspace="0em">sin</mo><mo stretchy="false">(</mo><mi>y</mi><mo stretchy="false">)</mo><mo>=</mo><mi>x</mi></mrow><annotation encoding="TeX">\forall x \in [{-1}, 1],\;\mathtt{\operatorname{Math.asin}(x)} = \arcsin(x) = \text{der eindeutige } y \in \left[-\frac{\pi}{2}, \frac{\pi}{2}\right] \text{ so dass } \sin(y) = x</annotation></semantics>
</math>
<!-- prettier-ignore-end -->

{{EmbedInteractiveExample("pages/js/math-asin.html")}}

## Syntax

```js-nolint
Math.asin(x)
```

### Parameter

- `x`
  - : Eine Zahl im Bereich von -1 bis 1, einschließlich, die den Sinuswert des Winkels darstellt.

### Rückgabewert

Der Arkussinus (Winkel in Radiant zwischen <math><semantics><mrow><mo>-</mo><mfrac><mi>π</mi><mn>2</mn></mfrac></mrow><annotation encoding="TeX">-\frac{\pi}{2}</annotation></semantics></math> und <math><semantics><mfrac><mi>π</mi><mn>2</mn></mfrac><annotation encoding="TeX">\frac{\pi}{2}</annotation></semantics></math>, einschließlich) von `x`. Wenn `x` kleiner als -1 oder größer als 1 ist, gibt {{jsxref("NaN")}} zurück.

## Beschreibung

Da `asin()` eine statische Methode von `Math` ist, verwenden Sie sie immer als `Math.asin()`, anstatt als eine Methode eines `Math` Objekts, das Sie erstellt haben (`Math` ist kein Konstruktor).

## Beispiele

### Verwendung von Math.asin()

```js
Math.asin(-2); // NaN
Math.asin(-1); // -1.5707963267948966 (-π/2)
Math.asin(-0); // -0
Math.asin(0); // 0
Math.asin(0.5); // 0.5235987755982989 (π/6)
Math.asin(1); // 1.5707963267948966 (π/2)
Math.asin(2); // NaN
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- {{jsxref("Math.acos()")}}
- {{jsxref("Math.atan()")}}
- {{jsxref("Math.atan2()")}}
- {{jsxref("Math.cos()")}}
- {{jsxref("Math.sin()")}}
- {{jsxref("Math.tan()")}}
