---
title: "SpeechSynthesisEvent: name Eigenschaft"
short-title: name
slug: Web/API/SpeechSynthesisEvent/name
l10n:
  sourceCommit: acfe8c9f1f4145f77653a2bc64a9744b001358dc
---

{{APIRef("Web Speech API")}}

Die **`name`**-Eigenschaft (nur lesbar) des [`SpeechSynthesisUtterance`](/de/docs/Web/API/SpeechSynthesisUtterance)-Interfaces gibt den Namen zurück, der mit bestimmten Ereignistypen verknüpft ist, die auftreten, während der Text der [`SpeechSynthesisUtterance.text`](/de/docs/Web/API/SpeechSynthesisUtterance/text) gesprochen wird:
den Namen des [SSML](https://www.w3.org/TR/speech-synthesis/#S3.3.2)-Markers, der im Fall eines [`mark`](/de/docs/Web/API/SpeechSynthesisUtterance/mark_event)-Ereignisses erreicht wurde, oder die Art der Grenze, die im Fall eines [`boundary`](/de/docs/Web/API/SpeechSynthesisUtterance/boundary_event)-Ereignisses erreicht wurde.

## Wert

Ein String.

## Beispiele

```js
utterThis.onboundary = (event) => {
  console.log(
    `${event.name} boundary reached after ${event.elapsedTime} seconds.`,
  );
};
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [Web Speech API](/de/docs/Web/API/Web_Speech_API)
