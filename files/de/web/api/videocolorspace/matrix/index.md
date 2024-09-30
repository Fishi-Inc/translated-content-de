---
title: "VideoColorSpace: matrix-Eigenschaft"
short-title: matrix
slug: Web/API/VideoColorSpace/matrix
l10n:
  sourceCommit: fa772db7e9b781ab41d5692c9d70dac423fddb1f
---

{{APIRef("WebCodecs API")}}{{AvailableInWorkers("window_and_dedicated")}}

Die **`matrix`**-Eigenschaft von der [`VideoColorSpace`](/de/docs/Web/API/VideoColorSpace)-Schnittstelle gibt die Matrixkoeffizienten des Videos zurück. Matrixkoeffizienten beschreiben die Beziehung zwischen Sample-Komponentenwerten und Farbkoordinaten.

## Wert

Ein String, der einen der folgenden Werte enthält:

- `"rgb"`
  - : Matrixkoeffizienten, die von sRGB verwendet werden.
- `"bt709"`
  - : Matrixkoeffizienten, die von BT.709 verwendet werden.
- `"bt470bg"`
  - : Matrixkoeffizienten, die von BT.601 PAL verwendet werden.
- `"smpte170m"`
  - : Matrixkoeffizienten, die von BT.601 NTSC verwendet werden.

## Beispiele

Im folgenden Beispiel ist `colorSpace` ein `VideoColorSpace`-Objekt, das von [`VideoFrame`](/de/docs/Web/API/VideoFrame) zurückgegeben wird. Der Wert von `matrix` wird in die Konsole ausgegeben.

```js
let colorSpace = VideoFrame.colorSpace;
console.log(colorSpace.matrix);
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}
