---
title: ":seeking"
slug: Web/CSS/:seeking
l10n:
  sourceCommit: c3be131cfd2c33822cb36b21cb4fca78980a6b4e
---

{{CSSRef}}

Der **`:seeking`** [CSS](/de/docs/Web/CSS) [Pseudoklassen](/de/docs/Web/CSS/Pseudo-classes) Selektor repräsentiert ein Element, das abspielbar ist, wie zum Beispiel {{htmlelement("audio")}} oder {{htmlelement("video")}}, wenn das abspielbare Element eine bestimmte Wiedergabeposition in der Medienressource sucht.
Eine Ressource wird als suchend betrachtet, wenn der Benutzer die Wiedergabe einer bestimmten Position in der Medienressource angefordert hat, das Medienelement diese Position jedoch noch nicht erreicht hat.

Das Suchen unterscheidet sich von {{cssxref(":buffering")}} darin, dass das Medienelement momentan keine Daten lädt, sondern stattdessen zu einer neuen Position in der Medienressource springt.
Für weitere Informationen siehe den [Leitfaden zu Media Buffering, Seeking und Zeitbereichen](/de/docs/Web/Media/Audio_and_video_delivery/buffering_seeking_time_ranges#seekable).

## Syntax

```css
:seeking {
  /* ... */
}
```

## Beispiele

### CSS

```css
:seeking {
  outline: 5px solid red;
}

video:seeking {
  outline: 5px solid blue;
}
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- {{cssxref(":buffering")}}
- {{cssxref(":muted")}}
- {{cssxref(":paused")}}
- {{cssxref(":playing")}}
- {{cssxref(":stalled")}}
- {{cssxref(":volume-locked")}}
- [CSS Selektoren](/de/docs/Web/CSS/CSS_selectors)
