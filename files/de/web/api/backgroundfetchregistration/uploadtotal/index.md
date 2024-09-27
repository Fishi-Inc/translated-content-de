---
title: "BackgroundFetchRegistration: uploadTotal-Eigenschaft"
short-title: uploadTotal
slug: Web/API/BackgroundFetchRegistration/uploadTotal
l10n:
  sourceCommit: c77a11ee1509542c16b0348afc4fcb3ffe588e1c
---

{{APIRef("Background Fetch API")}}{{SeeCompatTable}}{{AvailableInWorkers}}

Die schreibgeschützte **`uploadTotal`**-Eigenschaft der [`BackgroundFetchRegistration`](/de/docs/Web/API/BackgroundFetchRegistration)-Schnittstelle gibt die Gesamtanzahl der Bytes zurück, die an den Server gesendet werden sollen.

## Wert

Eine {{jsxref("number")}}.

## Beispiele

Das Protokollieren dieser Eigenschaft in der Konsole gibt die Gesamtanzahl dieses Uploads zurück.

```js
console.log(bgFetch.uploadTotal);
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}
