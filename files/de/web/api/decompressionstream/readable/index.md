---
title: "DecompressionStream: readable-Eigenschaft"
short-title: readable
slug: Web/API/DecompressionStream/readable
l10n:
  sourceCommit: d8b4431bfde42f1bc195239ea1f378d763f8163e
---

{{APIRef("Compression Streams API")}}{{AvailableInWorkers}}

Die schreibgeschützte Eigenschaft **`readable`** des [`DecompressionStream`](/de/docs/Web/API/DecompressionStream)-Interfaces gibt einen [`ReadableStream`](/de/docs/Web/API/ReadableStream) zurück.

## Wert

Ein [`ReadableStream`](/de/docs/Web/API/ReadableStream).

## Beispiele

Das folgende Beispiel gibt einen [`ReadableStream`](/de/docs/Web/API/ReadableStream) aus einem `DecompressionStream` zurück.

```js
let stream = new DecompressionStream("gzip");
console.log(stream.readable); //a ReadableStream
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}
