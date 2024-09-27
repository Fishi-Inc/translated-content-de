---
title: AnimationTimeline
slug: Web/API/AnimationTimeline
l10n:
  sourceCommit: 34bc6ac7c5d03e5891bf94b0d4ebeccb0e7a29e5
---

{{ APIRef("Web Animations") }}

Das `AnimationTimeline`-Interface der [Web Animations API](/de/docs/Web/API/Web_Animations_API) repräsentiert die Zeitachse einer Animation. Dieses Interface existiert, um Zeitachsenmerkmale zu definieren, die von anderen Zeitachsenarten geerbt werden:

- [`DocumentTimeline`](/de/docs/Web/API/DocumentTimeline)
- [`ScrollTimeline`](/de/docs/Web/API/ScrollTimeline)
- [`ViewTimeline`](/de/docs/Web/API/ViewTimeline)

## Instanzeigenschaften

- [`currentTime`](/de/docs/Web/API/AnimationTimeline/currentTime) {{ReadOnlyInline}}
  - : Gibt den Zeitwert in Millisekunden für diese Zeitachse zurück oder `null`, wenn diese Zeitachse inaktiv ist.

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [`DocumentTimeline`](/de/docs/Web/API/DocumentTimeline), [`ScrollTimeline`](/de/docs/Web/API/ScrollTimeline), [`ViewTimeline`](/de/docs/Web/API/ViewTimeline)
- [`Document.timeline`](/de/docs/Web/API/Document/timeline)
- [Web Animations API](/de/docs/Web/API/Web_Animations_API)
- [CSS scroll-gesteuerte Animationen](/de/docs/Web/CSS/CSS_scroll-driven_animations)
