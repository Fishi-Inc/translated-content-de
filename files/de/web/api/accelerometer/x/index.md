---
title: "Accelerometer: x Eigenschaft"
short-title: x
slug: Web/API/Accelerometer/x
l10n:
  sourceCommit: 4ea748e5f025c2a00a8ca8babd7c505e73ad9def
---

{{securecontext_header}}{{APIRef("Sensor API")}}{{SeeCompatTable}}

Die **`x`** schreibgeschützte Eigenschaft des [`Accelerometer`](/de/docs/Web/API/Accelerometer) Interface gibt eine Zahl zurück, die die Beschleunigung des Geräts entlang seiner x-Achse angibt.

## Wert

Ein {{jsxref('Number')}}.

## Beispiele

Die Beschleunigung wird typischerweise im [`reading`](/de/docs/Web/API/Sensor/reading_event) Ereignis-Callback ausgelesen. Im folgenden Beispiel passiert dies sechzig Mal pro Sekunde.

```js
const accelerometer = new Accelerometer({ frequency: 60 });

accelerometer.addEventListener("reading", (e) => {
  console.log(`Acceleration along the X-axis ${accelerometer.x}`);
  console.log(`Acceleration along the Y-axis ${accelerometer.y}`);
  console.log(`Acceleration along the Z-axis ${accelerometer.z}`);
});
accelerometer.start();
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}
