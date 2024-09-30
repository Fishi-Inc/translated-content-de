---
title: Event
slug: Web/API/Event
l10n:
  sourceCommit: c640274a19227cd5790912ea76841732baa6731f
---

{{APIRef("DOM")}}{{AvailableInWorkers}}

Die **`Event`**-Schnittstelle repräsentiert ein Ereignis, das auf einem [`EventTarget`](/de/docs/Web/API/EventTarget) stattfindet.

Ein Ereignis kann durch eine Benutzeraktion ausgelöst werden, z. B. durch Klicken der Maustaste oder Tippen auf die Tastatur, oder durch APIs generiert werden, um den Fortschritt einer asynchronen Aufgabe darzustellen. Es kann auch programmgesteuert ausgelöst werden, z. B. durch Aufrufen der [`HTMLElement.click()`](/de/docs/Web/API/HTMLElement/click)-Methode eines Elements oder durch Definieren des Ereignisses und anschließendes Senden an ein bestimmtes Ziel mit [`EventTarget.dispatchEvent()`](/de/docs/Web/API/EventTarget/dispatchEvent).

Es gibt viele Arten von Ereignissen, von denen einige andere Schnittstellen verwenden, die auf der Hauptschnittstelle `Event` basieren. `Event` selbst enthält die Eigenschaften und Methoden, die für alle Ereignisse üblich sind.

Viele DOM-Elemente können so eingerichtet werden, dass sie diese Ereignisse entgegennehmen (oder "abhören") und Code als Reaktion darauf ausführen, um sie zu verarbeiten (oder "handhaben"). Ereignis-Handler werden normalerweise an verschiedene [HTML-Elemente](/de/docs/Web/HTML/Element) (wie `<button>`, `<div>`, `<span>` usw.) mit [`EventTarget.addEventListener()`](/de/docs/Web/API/EventTarget/addEventListener) angeschlossen, was allgemein die Verwendung der alten HTML-[Ereignis-Handler-Attribute](/de/docs/Web/HTML/Global_attributes) ersetzt. Darüber hinaus können solche Handler bei Bedarf auch mit [`removeEventListener()`](/de/docs/Web/API/EventTarget/removeEventListener) getrennt werden, wenn sie ordnungsgemäß hinzugefügt wurden.

> [!NOTE]
> Ein Element kann mehrere solcher Handler haben, sogar für genau dasselbe Ereignis – insbesondere, wenn separate, unabhängige Code-Module sie anschließen, jeweils für ihre eigenen unabhängigen Zwecke. (Zum Beispiel eine Webseite mit einem Werbemodul und einem Statistikmodul, die beide die Videoansicht überwachen.)

Wenn es viele verschachtelte Elemente gibt, die jeweils über ihren eigenen Handler verfügen, kann die Ereignisverarbeitung sehr komplex werden – insbesondere wenn ein übergeordnetes Element dasselbe Ereignis wie seine untergeordneten Elemente erhält, da sie "räumlich" überlappen und das Ereignis technisch in beiden auftritt. Die Reihenfolge der Verarbeitung solcher Ereignisse hängt von den [Event bubbling](/de/docs/Learn/JavaScript/Building_blocks/Event_bubbling)-Einstellungen der einzelnen ausgelösten Handler ab.

## Schnittstellen basierend auf Event

Nachfolgend finden Sie eine Liste von Schnittstellen, die auf der Hauptschnittstelle `Event` basieren, mit Links zu ihrer jeweiligen Dokumentation in der MDN API-Referenz.

Beachten Sie, dass alle Ereignis-Schnittstellen Namen haben, die auf "Event" enden.

- [`AnimationEvent`](/de/docs/Web/API/AnimationEvent)
- [`AudioProcessingEvent`](/de/docs/Web/API/AudioProcessingEvent) {{Deprecated_Inline}}
- [`BeforeUnloadEvent`](/de/docs/Web/API/BeforeUnloadEvent)
- [`BlobEvent`](/de/docs/Web/API/BlobEvent)
- [`ClipboardEvent`](/de/docs/Web/API/ClipboardEvent)
- [`CloseEvent`](/de/docs/Web/API/CloseEvent)
- [`CompositionEvent`](/de/docs/Web/API/CompositionEvent)
- [`CustomEvent`](/de/docs/Web/API/CustomEvent)
- [`DeviceMotionEvent`](/de/docs/Web/API/DeviceMotionEvent)
- [`DeviceOrientationEvent`](/de/docs/Web/API/DeviceOrientationEvent)
- [`DragEvent`](/de/docs/Web/API/DragEvent)
- [`ErrorEvent`](/de/docs/Web/API/ErrorEvent)
- [`FetchEvent`](/de/docs/Web/API/FetchEvent)
- [`FocusEvent`](/de/docs/Web/API/FocusEvent)
- [`FontFaceSetLoadEvent`](/de/docs/Web/API/FontFaceSetLoadEvent)
- [`FormDataEvent`](/de/docs/Web/API/FormDataEvent)
- [`GamepadEvent`](/de/docs/Web/API/GamepadEvent)
- [`HashChangeEvent`](/de/docs/Web/API/HashChangeEvent)
- [`HIDInputReportEvent`](/de/docs/Web/API/HIDInputReportEvent)
- [`IDBVersionChangeEvent`](/de/docs/Web/API/IDBVersionChangeEvent)
- [`InputEvent`](/de/docs/Web/API/InputEvent)
- [`KeyboardEvent`](/de/docs/Web/API/KeyboardEvent)
- [`MediaStreamEvent`](/de/docs/Web/API/MediaStreamEvent) {{Deprecated_Inline}}
- [`MessageEvent`](/de/docs/Web/API/MessageEvent)
- [`MouseEvent`](/de/docs/Web/API/MouseEvent)
- [`MutationEvent`](/de/docs/Web/API/MutationEvent) {{Deprecated_Inline}}
- [`OfflineAudioCompletionEvent`](/de/docs/Web/API/OfflineAudioCompletionEvent)
- [`PageTransitionEvent`](/de/docs/Web/API/PageTransitionEvent)
- [`PaymentRequestUpdateEvent`](/de/docs/Web/API/PaymentRequestUpdateEvent)
- [`PointerEvent`](/de/docs/Web/API/PointerEvent)
- [`PopStateEvent`](/de/docs/Web/API/PopStateEvent)
- [`ProgressEvent`](/de/docs/Web/API/ProgressEvent)
- [`RTCDataChannelEvent`](/de/docs/Web/API/RTCDataChannelEvent)
- [`RTCPeerConnectionIceEvent`](/de/docs/Web/API/RTCPeerConnectionIceEvent)
- [`StorageEvent`](/de/docs/Web/API/StorageEvent)
- [`SubmitEvent`](/de/docs/Web/API/SubmitEvent)
- [`SVGEvent`](/de/docs/Web/API/SVGEvent) {{Deprecated_Inline}}
- [`TimeEvent`](/de/docs/Web/API/TimeEvent)
- [`TouchEvent`](/de/docs/Web/API/TouchEvent)
- [`TrackEvent`](/de/docs/Web/API/TrackEvent)
- [`TransitionEvent`](/de/docs/Web/API/TransitionEvent)
- [`UIEvent`](/de/docs/Web/API/UIEvent)
- [`WebGLContextEvent`](/de/docs/Web/API/WebGLContextEvent)
- [`WheelEvent`](/de/docs/Web/API/WheelEvent)

## Konstruktor

- [`Event()`](/de/docs/Web/API/Event/Event)
  - : Erstellt ein `Event`-Objekt und gibt es an den Aufrufer zurück.

## Instanz-Eigenschaften

- [`Event.bubbles`](/de/docs/Web/API/Event/bubbles) {{ReadOnlyInline}}
  - : Ein boolescher Wert, der angibt, ob das Ereignis durch das DOM nach oben blubbert.
- [`Event.cancelable`](/de/docs/Web/API/Event/cancelable) {{ReadOnlyInline}}
  - : Ein boolescher Wert, der angibt, ob das Ereignis abgebrochen werden kann.
- [`Event.composed`](/de/docs/Web/API/Event/composed) {{ReadOnlyInline}}
  - : Ein boolescher Wert, der angibt, ob das Ereignis die Grenze zwischen dem Shadow DOM und dem normalen DOM aufblubbern kann.
- [`Event.currentTarget`](/de/docs/Web/API/Event/currentTarget) {{ReadOnlyInline}}
  - : Eine Referenz auf das aktuell registrierte Ziel für das Ereignis. Dies ist das Objekt, an das das Ereignis gerade gesendet werden soll. Es ist möglich, dass sich dies durch _Retargeting_ geändert hat.
- [`Event.defaultPrevented`](/de/docs/Web/API/Event/defaultPrevented) {{ReadOnlyInline}}
  - : Gibt an, ob der Aufruf von [`event.preventDefault()`](/de/docs/Web/API/Event/preventDefault) das Ereignis abgebrochen hat.
- [`Event.eventPhase`](/de/docs/Web/API/Event/eventPhase) {{ReadOnlyInline}}
  - : Gibt an, welche Phase des Ereignis-Flows gerade verarbeitet wird. Es ist eine der folgenden Zahlen: `NONE`, `CAPTURING_PHASE`, `AT_TARGET`, `BUBBLING_PHASE`.
- [`Event.isTrusted`](/de/docs/Web/API/Event/isTrusted) {{ReadOnlyInline}}
  - : Gibt an, ob das Ereignis vom Browser initiiert wurde (nach einem Benutzer-Klick, zum Beispiel) oder durch ein Skript (unter Verwendung einer Ereigniserstellungsmethode, zum Beispiel).
- [`Event.srcElement`](/de/docs/Web/API/Event/srcElement) {{ReadOnlyInline}} {{Deprecated_Inline}}
  - : Ein Alias für die Eigenschaft [`Event.target`](/de/docs/Web/API/Event/target). Verwenden Sie stattdessen [`Event.target`](/de/docs/Web/API/Event/target).
- [`Event.target`](/de/docs/Web/API/Event/target) {{ReadOnlyInline}}
  - : Eine Referenz auf das Objekt, an das das Ereignis ursprünglich gesendet wurde.
- [`Event.timeStamp`](/de/docs/Web/API/Event/timeStamp) {{ReadOnlyInline}}
  - : Der Zeitpunkt, zu dem das Ereignis erstellt wurde (in Millisekunden). Laut Spezifikation ist dieser Wert die Zeit seit dem Epochenanfang – in der Realität variieren jedoch die Definitionen der Browser. Zudem wird daran gearbeitet, dies in einen [`DOMHighResTimeStamp`](/de/docs/Web/API/DOMHighResTimeStamp) zu ändern.
- [`Event.type`](/de/docs/Web/API/Event/type) {{ReadOnlyInline}}
  - : Der Name, der den Typ des Ereignisses identifiziert.

### Veraltete und nicht standardmäßige Eigenschaften

- [`Event.cancelBubble`](/de/docs/Web/API/Event/cancelBubble) {{deprecated_inline}}
  - : Ein historischer Alias für [`Event.stopPropagation()`](/de/docs/Web/API/Event/stopPropagation), der stattdessen verwendet werden sollte. Wenn sein Wert vor der Rückkehr aus einem Ereignis-Handler auf `true` gesetzt wird, verhindert dies die Weiterverbreitung des Ereignisses.
- [`Event.explicitOriginalTarget`](/de/docs/Web/API/Event/explicitOriginalTarget) {{non-standard_inline}} {{ReadOnlyInline}}
  - : Das explizite ursprüngliche Ziel des Ereignisses.
- [`Event.originalTarget`](/de/docs/Web/API/Event/originalTarget) {{non-standard_inline}} {{ReadOnlyInline}}
  - : Das ursprüngliche Ziel des Ereignisses, bevor irgendwelche Retargetings stattgefunden haben.
- [`Event.returnValue`](/de/docs/Web/API/Event/returnValue) {{deprecated_inline}}
  - : Eine historische Eigenschaft, die immer noch unterstützt wird, um sicherzustellen, dass bestehende Sites weiterhin funktionieren. Verwenden Sie [`Event.preventDefault()`](/de/docs/Web/API/Event/preventDefault) und [`Event.defaultPrevented`](/de/docs/Web/API/Event/defaultPrevented) stattdessen.
- [`Event.scoped`](/de/docs/Web/API/Event/composed) {{ReadOnlyInline}} {{deprecated_inline}}
  - : Ein boolescher Wert, der anzeigt, ob das gegebene Ereignis durch den Shadow Root in das Standard-DOM aufblubbern wird. Verwenden Sie stattdessen [`composed`](/de/docs/Web/API/Event/composed).

## Instanz-Methoden

- [`Event.composedPath()`](/de/docs/Web/API/Event/composedPath)
  - : Gibt den Pfad des Ereignisses zurück (ein Array von Objekten, auf denen Listener aufgerufen werden). Dies schließt keine Knoten in Shadow-Bäumen ein, wenn die Shadow Root mit ihrem [`ShadowRoot.mode`](/de/docs/Web/API/ShadowRoot/mode) im geschlossenen Modus erstellt wurde.
- [`Event.preventDefault()`](/de/docs/Web/API/Event/preventDefault)
  - : Bricht das Ereignis ab (falls es abbrechbar ist).
- [`Event.stopImmediatePropagation()`](/de/docs/Web/API/Event/stopImmediatePropagation)
  - : Verhindert für dieses bestimmte Ereignis, dass alle anderen Listener aufgerufen werden. Dies schließt Listener ein, die am gleichen Element angefügt sind sowie jene, die an Elementen angefügt sind, die später durchlaufen werden (während der Erfassungsphase zum Beispiel).
- [`Event.stopPropagation()`](/de/docs/Web/API/Event/stopPropagation)
  - : Stoppt die Weiterverbreitung von Ereignissen weiter im DOM.

### Veraltete Methoden

- [`Event.initEvent()`](/de/docs/Web/API/Event/initEvent) {{deprecated_inline}}
  - : Initialisiert den Wert eines erzeugten Ereignisses. Wenn das Ereignis bereits gesendet wurde, tut diese Methode nichts. Verwenden Sie den Konstruktor ([`Event()`](/de/docs/Web/API/Event/Event) stattdessen).

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- Verfügbare Arten von Ereignissen: [Ereignisreferenz](/de/docs/Web/Events)
- [Einführung in Ereignisse](/de/docs/Learn/JavaScript/Building_blocks/Events)
- [Event bubbling](/de/docs/Learn/JavaScript/Building_blocks/Event_bubbling)
- [Erstellen und Auslösen benutzerdefinierter Ereignisse](/de/docs/Web/Events/Creating_and_triggering_events)
