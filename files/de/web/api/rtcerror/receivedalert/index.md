---
title: "RTCError: receivedAlert-Eigenschaft"
short-title: receivedAlert
slug: Web/API/RTCError/receivedAlert
l10n:
  sourceCommit: 802b6063046dffb7634d2138aadcd92cb22ed40c
---

{{APIRef("WebRTC")}}

Die schreibgeschützte Eigenschaft **`receivedAlert`** des [`RTCError`](/de/docs/Web/API/RTCError) gibt den fatalen [DTLS](/de/docs/Glossary/DTLS)-Fehler an, der dazu führte, dass eine Warnung vom Remote-Peer empfangen wurde.

## Wert

Ein unsigned long Integer, der den fatalen [DTLS](/de/docs/Glossary/DTLS)-Fehler angibt, der dazu führte, dass eine Warnung vom Remote-Peer empfangen wurde.

> [!NOTE]
> Diese Eigenschaft ist `null`, wenn der `RTCError` keinen DTLS-Fehler darstellt (mit [`errorDetail`](/de/docs/Web/API/RTCError/errorDetail) auf `dtls-failure` gesetzt).

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}
