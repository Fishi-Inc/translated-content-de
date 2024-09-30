---
title: "MediaDevices: enumerateDevices() Methode"
short-title: enumerateDevices()
slug: Web/API/MediaDevices/enumerateDevices
l10n:
  sourceCommit: b2875dbaa70efb5850084b9802803b439db325f5
---

{{APIRef("Media Capture and Streams")}}{{SecureContext_Header}}

Die **`enumerateDevices()`**-Methode der [`MediaDevices`](/de/docs/Web/API/MediaDevices)-Schnittstelle fordert eine Liste der derzeit verfügbaren Medien-Ein- und -Ausgabegeräte an, wie Mikrofone, Kameras, Headsets usw.
Das zurückgegebene {{jsxref("Promise")}} wird mit einem Array von [`MediaDeviceInfo`](/de/docs/Web/API/MediaDeviceInfo)-Objekten aufgelöst, die die Geräte beschreiben.

Die zurückgegebene Liste wird alle Geräte auslassen, die durch die Dokument-[Berechtigungsrichtlinie](/de/docs/Web/HTTP/Headers/Permissions-Policy) blockiert sind: [`microphone`](/de/docs/Web/HTTP/Headers/Permissions-Policy/microphone), [`camera`](/de/docs/Web/HTTP/Headers/Permissions-Policy/camera), [`speaker-selection`](/de/docs/Web/HTTP/Headers/Permissions-Policy/speaker-selection) (für Ausgabegeräte) usw.
Der Zugriff auf bestimmte, nicht standardmäßige Geräte wird auch durch die [Permissions API](/de/docs/Web/API/Permissions_API) beschränkt, und die Liste wird Geräte auslassen, für die der Benutzer keine explizite Erlaubnis erteilt hat.

## Syntax

```js-nolint
enumerateDevices()
```

### Parameter

Keine.

### Rückgabewert

Ein {{jsxref("Promise")}}, das mit einem Array von [`MediaDeviceInfo`](/de/docs/Web/API/MediaDeviceInfo)-Objekten erfüllt wird.
Jedes Objekt im Array beschreibt eines der verfügbaren Medien-Ein- und -Ausgabegeräte.
Die Reihenfolge ist signifikant — die Standardaufnahmegeräte werden zuerst aufgelistet.

Abgesehen von Standardgeräten sind nur Geräte verfügbar, für die Berechtigungen erteilt wurden.

Wenn das Mediengerät ein Eingabegerät ist, wird stattdessen ein [`InputDeviceInfo`](/de/docs/Web/API/InputDeviceInfo)-Objekt zurückgegeben.

Wenn die Aufzählung fehlschlägt, wird das Versprechen abgelehnt.

## Sicherheitsanforderungen

Der Zugriff auf die API unterliegt folgenden Einschränkungen:

- Die Methode muss in einem [sicheren Kontext](/de/docs/Web/Security/Secure_Contexts) aufgerufen werden.
- Das Dokument muss vollständig aktiv sein, und seine Sichtbarkeit muss "sichtbar" sein.

## Beispiele

Hier ist ein Beispiel für die Verwendung von `enumerateDevices()`. Es gibt eine Liste der [Geräte-IDs](/de/docs/Web/API/MediaDeviceInfo/deviceId) mit ihren Labels aus, sofern verfügbar.

```js
if (!navigator.mediaDevices?.enumerateDevices) {
  console.log("enumerateDevices() not supported.");
} else {
  // List cameras and microphones.
  navigator.mediaDevices
    .enumerateDevices()
    .then((devices) => {
      devices.forEach((device) => {
        console.log(`${device.kind}: ${device.label} id = ${device.deviceId}`);
      });
    })
    .catch((err) => {
      console.error(`${err.name}: ${err.message}`);
    });
}
```

Dies könnte ergeben:

```plain
videoinput: id = csO9c0YpAf274OuCPUA53CNE0YHlIr2yXCi+SqfBZZ8=
audioinput: id = RKxXByjnabbADGQNNZqLVLdmXlS0YkETYCIbg+XxnvM=
audioinput: id = r2/xw1xUPIyZunfV1lGrKOma5wTOvCkWfZ368XCndm0=
```

oder wenn ein oder mehrere [`MediaStream`](/de/docs/Web/API/MediaStream)s aktiv sind oder dauerhafte Berechtigungen erteilt wurden:

```plain
videoinput: FaceTime HD Camera (Built-in) id=csO9c0YpAf274OuCPUA53CNE0YHlIr2yXCi+SqfBZZ8=
audioinput: default (Built-in Microphone) id=RKxXByjnabbADGQNNZqLVLdmXlS0YkETYCIbg+XxnvM=
audioinput: Built-in Microphone id=r2/xw1xUPIyZunfV1lGrKOma5wTOvCkWfZ368XCndm0=
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [`MediaDevices.getUserMedia`](/de/docs/Web/API/MediaDevices/getUserMedia)
- [WebRTC](/de/docs/Web/API/WebRTC_API) - die Einführungsseite zur API
- [Media Capture and Streams API](/de/docs/Web/API/Media_Capture_and_Streams_API) - die API für die Medienstrom-Objekte
- [Webcam-Fotos aufnehmen](/de/docs/Web/API/Media_Capture_and_Streams_API/Taking_still_photos) - ein
  Tutorial zur Verwendung von `getUserMedia()` zum Aufnehmen von Fotos anstelle von Videos.
