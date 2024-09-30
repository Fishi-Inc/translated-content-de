---
title: Math.exp()
slug: Web/JavaScript/Reference/Global_Objects/Math/exp
l10n:
  sourceCommit: 761b9047d78876cbd153be811efb1aa77b419877
---

{{JSRef}}

Die statische Methode **`Math.exp()`** gibt [e](/de/docs/Web/JavaScript/Reference/Global_Objects/Math/E) potenziert mit einer Zahl zurück. Das heißt:

<!-- prettier-ignore-start -->
<math display="block">
  <semantics><mrow><mrow><mo lspace="0em" rspace="0.16666666666666666em">𝙼𝚊𝚝𝚑.𝚎𝚡𝚙</mo><mo stretchy="false">(</mo><mi>𝚡</mi><mo stretchy="false">)</mo></mrow><mo>=</mo><msup><mi mathvariant="normal">e</mi><mi>x</mi></msup></mrow><annotation encoding="TeX">\mathtt{\operatorname{Math.exp}(x)}} = \mathrm{e}^x</annotation></semantics>
</math>
<!-- prettier-ignore-end -->

{{EmbedInteractiveExample("pages/js/math-exp.html")}}

## Syntax

```js-nolint
Math.exp(x)
```

### Parameter

- `x`
  - : Eine Zahl.

### Rückgabewert

Eine nichtnegative Zahl, die e<sup>x</sup> darstellt, wobei e die [Basis des natürlichen Logarithmus](/de/docs/Web/JavaScript/Reference/Global_Objects/Math/E) ist.

## Beschreibung

Da `exp()` eine statische Methode von `Math` ist, wird sie stets als `Math.exp()` verwendet, anstatt als Methode eines von Ihnen erstellten `Math`-Objekts (`Math` ist kein Konstruktor).

Seien Sie vorsichtig, dass `e` potenziert mit einer Zahl, die sehr nahe bei 0 liegt, sehr nahe bei 1 liegt und an Präzision verliert. In diesem Fall sollten Sie möglicherweise {{jsxref("Math.expm1")}} verwenden, um einen Bruchteil der Antwort mit wesentlich höherer Präzision zu erhalten.

## Beispiele

### Verwendung von Math.exp()

```js
Math.exp(-Infinity); // 0
Math.exp(-1); // 0.36787944117144233
Math.exp(0); // 1
Math.exp(1); // 2.718281828459045
Math.exp(Infinity); // Infinity
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- {{jsxref("Math.E")}}
- {{jsxref("Math.expm1()")}}
- {{jsxref("Math.log()")}}
- {{jsxref("Math.log10()")}}
- {{jsxref("Math.log1p()")}}
- {{jsxref("Math.log2()")}}
- {{jsxref("Math.pow()")}}
