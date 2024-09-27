---
title: font-variant-ligatures
slug: Web/CSS/font-variant-ligatures
l10n:
  sourceCommit: 8d8f3f44b498aef7b8cf2729d5656f96d2ff6ae5
---

{{CSSRef}}

Die **`font-variant-ligatures`** [CSS](/de/docs/Web/CSS) Eigenschaft steuert, welche [Ligaturen](/de/docs/Glossary/ligature) und [kontextuellen Formen](/de/docs/Glossary/contextual_forms) im Textinhalt der Elemente verwendet werden, auf die sie angewendet wird. Dies führt zu harmonischeren Formen im resultierenden Text.

{{EmbedInteractiveExample("pages/css/font-variant-ligatures.html")}}

## Syntax

```css
/* Keyword values */
font-variant-ligatures: normal;
font-variant-ligatures: none;
font-variant-ligatures: common-ligatures; /* <common-lig-values> */
font-variant-ligatures: no-common-ligatures; /* <common-lig-values> */
font-variant-ligatures: discretionary-ligatures; /* <discretionary-lig-values> */
font-variant-ligatures: no-discretionary-ligatures; /* <discretionary-lig-values> */
font-variant-ligatures: historical-ligatures; /* <historical-lig-values> */
font-variant-ligatures: no-historical-ligatures; /* <historical-lig-values> */
font-variant-ligatures: contextual; /* <contextual-alt-values> */
font-variant-ligatures: no-contextual; /* <contextual-alt-values> */

/* Two keyword values */
font-variant-ligatures: no-contextual common-ligatures;

/* Four keyword values */
font-variant-ligatures: common-ligatures no-discretionary-ligatures
  historical-ligatures contextual;

/* Global values */
font-variant-ligatures: inherit;
font-variant-ligatures: initial;
font-variant-ligatures: revert;
font-variant-ligatures: revert-layer;
font-variant-ligatures: unset;
```

Die Eigenschaft `font-variant-ligatures` wird als `normal`, `none`, oder einer oder mehreren der unten aufgelisteten Wertetypen angegeben. Mehrere Werte werden durch Leerzeichen getrennt.

### Werte

- `normal`
  - : Dieses Schlüsselwort aktiviert die üblichen Ligaturen und kontextuellen Formen, die für eine korrekte Darstellung erforderlich sind. Die aktivierten Ligaturen und Formen hängen von der Schriftart, der Sprache und der Art des Skripts ab. Dies ist der Standardwert.
- `none`
  - : Dieses Schlüsselwort gibt an, dass alle Ligaturen und kontextuellen Formen deaktiviert sind, auch die gebräuchlichen.
- _`<common-lig-values>`_

  - : Diese Werte steuern die gebräuchlichsten Ligaturen, wie `fi`, `ffi`, `th` oder ähnliche. Sie entsprechen den OpenType-Werten `liga` und `clig`. Zwei Werte sind möglich:

    - `common-ligatures` aktiviert diese Ligaturen. Beachten Sie, dass das Schlüsselwort `normal` diese Ligaturen aktiviert.
    - `no-common-ligatures` deaktiviert diese Ligaturen.

- _`<discretionary-lig-values>`_

  - : Diese Werte steuern spezifische Ligaturen, die spezifisch für die Schriftart und vom Schriftgestalter definiert sind. Sie entsprechen den OpenType-Werten `dlig`. Zwei Werte sind möglich:

    - `discretionary-ligatures` aktiviert diese Ligaturen.
    - `no-discretionary-ligatures` deaktiviert die Ligaturen. Beachten Sie, dass das Schlüsselwort `normal` diese Ligaturen normalerweise deaktiviert.

- _`<historical-lig-values>`_

  - : Diese Werte steuern die historisch verwendeten Ligaturen, wie sie in alten Büchern vorkommen, z.B. das deutsche tz-Digraph als ꜩ. Sie entsprechen den OpenType-Werten `hlig`. Zwei Werte sind möglich:

    - `historical-ligatures` aktiviert diese Ligaturen.
    - `no-historical-ligatures` deaktiviert die Ligaturen. Beachten Sie, dass das Schlüsselwort `normal` diese Ligaturen normalerweise deaktiviert.

- _`<contextual-alt-values>`_

  - : Diese Werte steuern, ob Buchstaben an ihren Kontext angepasst werden – das heißt, ob sie sich an die umgebenden Buchstaben anpassen. Diese Werte entsprechen den OpenType-Werten `calt`. Zwei Werte sind möglich:

    - `contextual` gibt an, dass die kontextuellen Alternativen verwendet werden sollen. Beachten Sie, dass das Schlüsselwort `normal` diese Ligaturen normalerweise ebenfalls aktiviert.
    - `no-contextual` verhindert deren Verwendung.

## Formale Definition

{{cssinfo}}

## Formale Syntax

{{csssyntax}}

## Beispiele

### Festlegen von Schriftligaturen und kontextuellen Formen

#### HTML

```html
<link href="//fonts.googleapis.com/css?family=Lora" rel="stylesheet" />
<p class="normal">
  normal<br />
  if fi ff tf ft jf fj
</p>
<p class="none">
  none<br />
  if fi ff tf ft jf fj
</p>
<p class="common-ligatures">
  common-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="no-common-ligatures">
  no-common-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="discretionary-ligatures">
  discretionary-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="no-discretionary-ligatures">
  no-discretionary-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="historical-ligatures">
  historical-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="no-historical-ligatures">
  no-historical-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="contextual">
  contextual<br />
  if fi ff tf ft jf fj
</p>
<p class="no-contextual">
  no-contextual<br />
  if fi ff tf ft jf fj
</p>
```

#### CSS

```css
p {
  font-family: Lora, serif;
}
.normal {
  font-variant-ligatures: normal;
}

.none {
  font-variant-ligatures: none;
}

.common-ligatures {
  font-variant-ligatures: common-ligatures;
}

.no-common-ligatures {
  font-variant-ligatures: no-common-ligatures;
}

.discretionary-ligatures {
  font-variant-ligatures: discretionary-ligatures;
}

.no-discretionary-ligatures {
  font-variant-ligatures: no-discretionary-ligatures;
}

.historical-ligatures {
  font-variant-ligatures: historical-ligatures;
}

.no-historical-ligatures {
  font-variant-ligatures: no-historical-ligatures;
}

.contextual {
  font-variant-ligatures: contextual;
}

.no-contextual {
  font-variant-ligatures: no-contextual;
}
```

#### Ergebnis

{{ EmbedLiveSample('Setting font ligatures and contextual forms', '', '700') }}

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [`font-variant`](/de/docs/Web/CSS/font-variant)
- [`font-variant-caps`](/de/docs/Web/CSS/font-variant-caps)
- [`font-variant-emoji`](/de/docs/Web/CSS/font-variant-emoji)
- [`font-variant-east-asian`](/de/docs/Web/CSS/font-variant-east-asian)
- [`font-variant-numeric`](/de/docs/Web/CSS/font-variant-numeric)
- [`font-variant-position`](/de/docs/Web/CSS/font-variant-position)
- [CSS Fonts Modul](/de/docs/Web/CSS/CSS_fonts)
