---
title: vertikale Ausrichtung
slug: Web/CSS/vertical-align
l10n:
  sourceCommit: 583d48191a7a8605d831aff357bef6cc63aef2e3
---

{{CSSRef}}

Die **`vertical-align`**-[CSS](/de/docs/Web/CSS)-Eigenschaft legt die vertikale Ausrichtung eines Inline-, Inline-Block- oder Tabellenzellen-Box fest.

{{EmbedInteractiveExample("pages/css/vertical-align.html")}}

Die Eigenschaft vertical-align kann in zwei Kontexten verwendet werden:

- Um eine Inline-Elementbox innerhalb ihrer enthaltenen Zeilenbox vertikal auszurichten. Beispielsweise könnte es verwendet werden, um [ein Bild in einer Textzeile vertikal zu positionieren](#vertikale_ausrichtung_in_einer_zeilenbox).
- Um [den Inhalt einer Zelle in einer Tabelle](#vertikale_ausrichtung_in_einer_tabellenzelle) vertikal auszurichten.

Beachten Sie, dass `vertical-align` nur auf Inline-, Inline-Block- und Tabellenzellen-Elemente anwendbar ist: Sie können es nicht verwenden, um [Block-Level-Elemente](/de/docs/Glossary/Block-level_content) vertikal auszurichten.

## Syntax

```css
/* Schlüsselwortwerte */
vertical-align: baseline;
vertical-align: sub;
vertical-align: super;
vertical-align: text-top;
vertical-align: text-bottom;
vertical-align: middle;
vertical-align: top;
vertical-align: bottom;

/* <length>-Werte */
vertical-align: 10em;
vertical-align: 4px;

/* <percentage>-Werte */
vertical-align: 20%;

/* Globale Werte */
vertical-align: inherit;
vertical-align: initial;
vertical-align: revert;
vertical-align: revert-layer;
vertical-align: unset;
```

Die `vertical-align`-Eigenschaft wird mit einem der unten aufgeführten Werte spezifiziert.

### Werte für Inline-Elemente

#### Eltern-relative Werte

Diese Werte richten das Element relativ zu seinem Elternelement vertikal aus:

- `baseline`
  - : Richtet die Grundlinie des Elements mit der Grundlinie seines Elternteils aus. Die Grundlinie einiger [ersetzter Elemente](/de/docs/Web/CSS/Replaced_element), wie {{HTMLElement("textarea")}}, wird nicht durch die HTML-Spezifikation festgelegt, was bedeutet, dass ihr Verhalten mit diesem Schlüsselwort zwischen den Browsern variieren kann.
- `sub`
  - : Richtet die Grundlinie des Elements mit der Tiefstellung-Grundlinie seines Elternteils aus.
- `super`
  - : Richtet die Grundlinie des Elements mit der Hochstellung-Grundlinie seines Elternteils aus.
- `text-top`
  - : Richtet die Oberseite des Elements mit der Oberseite der Schrift des Elternelements aus.
- `text-bottom`
  - : Richtet die Unterseite des Elements mit der Unterseite der Schrift des Elternelements aus.
- `middle`
  - : Richtet die Mitte des Elements mit der Grundlinie plus der halben x-Höhe des Elternteils aus.
- {{cssxref("&lt;length&gt;")}}
  - : Richtet die Grundlinie des Elements auf die angegebene Länge über der Grundlinie seines Elternteils aus. Ein negativer Wert ist erlaubt.
- {{cssxref("&lt;percentage&gt;")}}
  - : Richtet die Grundlinie des Elements auf den angegebenen Prozentsatz über der Grundlinie seines Elternteils aus, wobei der Wert ein Prozentsatz der {{Cssxref("line-height")}}-Eigenschaft ist. Ein negativer Wert ist erlaubt.

#### Zeilen-relative Werte

Die folgenden Werte richten das Element relativ zur gesamten Zeile vertikal aus:

- `top`
  - : Richtet die Oberseite des Elements und seiner Nachkommen mit der Oberseite der gesamten Zeile aus.
- `bottom`
  - : Richtet die Unterseite des Elements und seiner Nachkommen mit der Unterseite der gesamten Zeile aus.

Für Elemente, die keine Grundlinie haben, wird stattdessen der untere Rand verwendet.

### Werte für Tabellenzellen

- `baseline` (und `sub`, `super`, `text-top`, `text-bottom`, `<length>`, und `<percentage>`)
  - : Richtet die Grundlinie der Zelle mit der Grundlinie aller anderen Zellen in der Zeile aus, die an der Grundlinie ausgerichtet sind.
- `top`
  - : Richtet den oberen Randabstand der Zelle mit der Oberseite der Zeile aus.
- `middle`
  - : Zentriert das Abstandsbox der Zelle innerhalb der Zeile.
- `bottom`
  - : Richtet den unteren Randabstand der Zelle mit der Unterseite der Zeile aus.

Negative Werte sind erlaubt.

## Formale Definition

{{CSSInfo}}

## Formale Syntax

{{csssyntax}}

## Beispiele

### Einfaches Beispiel

#### HTML

```html
<div>
  An <img src="frame_image.svg" alt="link" width="32" height="32" /> image with
  a default alignment.
</div>
<div>
  An
  <img class="top" src="frame_image.svg" alt="link" width="32" height="32" />
  image with a text-top alignment.
</div>
<div>
  An
  <img class="bottom" src="frame_image.svg" alt="link" width="32" height="32" />
  image with a text-bottom alignment.
</div>
<div>
  An
  <img class="middle" src="frame_image.svg" alt="link" width="32" height="32" />
  image with a middle alignment.
</div>
```

#### CSS

```css
img.top {
  vertical-align: text-top;
}
img.bottom {
  vertical-align: text-bottom;
}
img.middle {
  vertical-align: middle;
}
```

#### Ergebnis

{{EmbedLiveSample("Basic_example")}}

### Vertikale Ausrichtung in einer Zeilenbox

#### HTML

```html-nolint
<p>
top:         <img style="vertical-align: top" src="star.png" alt="star"/>
middle:      <img style="vertical-align: middle" src="star.png" alt="star"/>
bottom:      <img style="vertical-align: bottom" src="star.png" alt="star"/>
super:       <img style="vertical-align: super" src="star.png" alt="star"/>
sub:         <img style="vertical-align: sub" src="star.png" alt="star"/>
</p>

<p>
text-top:    <img style="vertical-align: text-top" src="star.png" alt="star"/>
text-bottom: <img style="vertical-align: text-bottom" src="star.png" alt="star"/>
0.2em:       <img style="vertical-align: 0.2em" src="star.png" alt="star"/>
-1em:        <img style="vertical-align: -1em" src="star.png" alt="star"/>
20%:         <img style="vertical-align: 20%" src="star.png" alt="star"/>
-100%:       <img style="vertical-align: -100%" src="star.png" alt="star"/>
</p>
```

```css hidden
#* {
  box-sizing: border-box;
}

img {
  margin-right: 0.5em;
}

p {
  height: 3em;
  padding: 0 0.5em;
  font-family: monospace;
  text-decoration: underline overline;
  margin-left: auto;
  margin-right: auto;
  width: 80%;
}
```

#### Ergebnis

{{EmbedLiveSample("Vertical_alignment_in_a_line_box", '100%', 160, "", "")}}

### Vertikale Ausrichtung in einer Tabellenzelle

In diesem Beispiel haben wir eine Tabelle mit einer einzigen Zeile, die sechs Zellen enthält. Die Zeile setzt `vertical-align` als Standardwert auf `bottom`.

- Die ersten vier Zellen setzen jeweils ihre eigenen `vertical-align`-Werte, und diese überschreiben den Wert der Zeile.
- Die fünfte Zelle setzt keinen `vertical-align`-Wert und erbt daher den Wert der Zeile.

Die sechste Zelle wird nur verwendet, um sicherzustellen, dass die Zellen hoch genug sind, um die Wirkung zu sehen.

#### HTML

```html
<table>
  <tr class="bottom">
    <td class="baseline">baseline</td>
    <td class="top">top</td>
    <td class="middle">middle</td>
    <td>bottom</td>
    <td>Row's style</td>
    <td>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse
      pretium felis eu sem mattis vulputate.
    </td>
  </tr>
</table>
```

#### CSS

```css
table {
  margin-left: auto;
  margin-right: auto;
  width: 80%;
}

table,
th,
td {
  border: 1px solid black;
}

td {
  padding: 0.5em;
  font-family: monospace;
}

.bottom {
  vertical-align: bottom;
}

.baseline {
  vertical-align: baseline;
}

.top {
  vertical-align: top;
}

.middle {
  vertical-align: middle;
}
```

#### Ergebnis

{{EmbedLiveSample("Vertical_alignment_in_a_table_cell", '100%', 230, "", "")}}

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [Typische Anwendungsfälle von Flexbox, Abschnitt "Element zentrieren"](/de/docs/Web/CSS/CSS_flexible_box_layout/Typical_use_cases_of_flexbox#center_item)
- {{Cssxref("line-height")}}, {{Cssxref("text-align")}}, {{Cssxref("margin")}}
- [Understanding `vertical-align`, oder "Wie (Nicht) Inhalte vertikal zentrieren"](https://phrogz.net/css/vertical-align/index.html)
- [Vertical-Align: Alles, was Sie wissen müssen](https://christopheraue.net/design/vertical-align)
