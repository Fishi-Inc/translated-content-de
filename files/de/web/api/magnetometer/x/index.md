---
title: "Magnetometer: x Eigenschaft"
short-title: x
slug: Web/API/Magnetometer/x
l10n:
  sourceCommit: 4ea748e5f025c2a00a8ca8babd7c505e73ad9def
---

{{securecontext_header}}{{APIRef("Sensor API")}}{{SeeCompatTable}}

Die schreibgeschützte Eigenschaft **`x`** des
{{domxref("Magnetometer")}}-Interfaces gibt eine Zahl zurück, die das Magnetfeld entlang der x-Achse des Geräts angibt.

## Wert

Ein {{jsxref('Number')}}.

## Beispiele

Der Magnetometer wird typischerweise im {{domxref('Sensor.reading_event', 'reading')}} Ereignis-Callback ausgelesen. Im Beispiel unten geschieht dies sechzig Mal pro Sekunde.

```js
let magSensor = new Magnetometer({ frequency: 60 });

magSensor.addEventListener("reading", (e) => {
  console.log(`Magnetic field along the X-axis ${magSensor.x}`);
  console.log(`Magnetic field along the Y-axis ${magSensor.y}`);
  console.log(`Magnetic field along the Z-axis ${magSensor.z}`);
});
magSensor.start();
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}
