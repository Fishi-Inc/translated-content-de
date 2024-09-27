---
title: "ReadableStream: getReader() Methode"
short-title: getReader()
slug: Web/API/ReadableStream/getReader
l10n:
  sourceCommit: d8b4431bfde42f1bc195239ea1f378d763f8163e
---

{{APIRef("Streams")}}{{AvailableInWorkers}}

Die **`getReader()`**-Methode der [`ReadableStream`](/de/docs/Web/API/ReadableStream)-Schnittstelle erstellt einen Leser und sperrt den Stream für diesen.
Solange der Stream gesperrt ist, kann kein anderer Leser erworben werden, bis dieser freigegeben wird.

## Syntax

```js-nolint
getReader()
getReader(options)
```

### Parameter

- `options` {{optional_inline}}

  - : Ein Objekt, das die folgenden Eigenschaften enthält:

    - `mode` {{optional_inline}}

      - : Eine Eigenschaft, die den Typ des zu erstellenden Lesers angibt.
        Mögliche Werte sind:

        - `"byob"`, was zur Erstellung eines [`ReadableStreamBYOBReader`](/de/docs/Web/API/ReadableStreamBYOBReader) führt, der lesbare Byte-Streams lesen kann (Streams, die eine Zero-Copy-Übertragung von einer zugrunde liegenden Byte-Quelle zum Leser unterstützen, wenn die internen Stream-Puffer leer sind).
        - `undefined` (oder überhaupt nicht angegeben — dies ist der Standard), was zur Erstellung eines [`ReadableStreamDefaultReader`](/de/docs/Web/API/ReadableStreamDefaultReader) führt, der einzelne Chunks aus einem Stream lesen kann.

### Rückgabewert

Ein [`ReadableStreamDefaultReader`](/de/docs/Web/API/ReadableStreamDefaultReader) oder [`ReadableStreamBYOBReader`](/de/docs/Web/API/ReadableStreamBYOBReader)-Objektinstanz, abhängig vom `mode`-Wert.

### Ausnahmen

- {{jsxref("RangeError")}}
  - : Wird ausgelöst, wenn der angegebene Moduswert nicht `"byob"` oder `undefined` ist.
- {{jsxref("TypeError")}}
  - : Wird ausgelöst, wenn der Stream, für den Sie einen Leser erstellen möchten, bereits gesperrt ist oder kein [`ReadableStream`](/de/docs/Web/API/ReadableStream) ist.
    Dies wird auch ausgelöst, wenn ein BYOB-Leser angefordert wird und der Stream-Controller kein [`ReadableByteStreamController`](/de/docs/Web/API/ReadableByteStreamController) ist (der Stream wurde nicht als zugrunde liegende Quelle mit [`type="bytes"`](/de/docs/Web/API/ReadableStream/ReadableStream#type) [konstruiert](/de/docs/Web/API/ReadableStream/ReadableStream)).

## Beispiele

Im folgenden einfachen Beispiel wird ein zuvor erstellter benutzerdefinierter `ReadableStream` mithilfe eines [`ReadableStreamDefaultReader`](/de/docs/Web/API/ReadableStreamDefaultReader), der mit `getReader()` erstellt wurde, gelesen.
(Siehe unser [einfaches Zufallsstrom-Beispiel](https://mdn.github.io/dom-examples/streams/simple-random-stream/) für den vollständigen Code).
Jeder Chunk wird der Reihe nach gelesen und an die Benutzeroberfläche ausgegeben, bis der Stream vollständig gelesen ist, an welchem Punkt wir die rekursive Funktion verlassen und den gesamten Stream an einem anderen Teil der Benutzeroberfläche ausgeben.

```js
function fetchStream() {
  const reader = stream.getReader();
  let charsReceived = 0;

  // read() returns a promise that resolves
  // when a value has been received
  reader.read().then(function processText({ done, value }) {
    // Result objects contain two properties:
    // done  - true if the stream has already given you all its data.
    // value - some data. Always undefined when done is true.
    if (done) {
      console.log("Stream complete");
      para.textContent = value;
      return;
    }

    // value for fetch streams is a Uint8Array
    charsReceived += value.length;
    const chunk = value;
    let listItem = document.createElement("li");
    listItem.textContent = `Received ${charsReceived} characters so far. Current chunk = ${chunk}`;
    list2.appendChild(listItem);

    result += chunk;

    // Read some more, and call this function again
    return reader.read().then(processText);
  });
}
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [`ReadableStream()`](/de/docs/Web/API/ReadableStream/ReadableStream)-Konstruktor
- [`ReadableStreamDefaultReader`](/de/docs/Web/API/ReadableStreamDefaultReader)
- [`ReadableStreamBYOBReader`](/de/docs/Web/API/ReadableStreamBYOBReader)
- [Verwendung von lesbaren Streams](/de/docs/Web/API/Streams_API/Using_readable_streams)
- [Verwendung von lesbaren Bytestreams](/de/docs/Web/API/Streams_API/Using_readable_byte_streams)
