---
title: additive-symbole
slug: Web/CSS/@counter-style/additive-symbols
l10n:
  sourceCommit: 4cb569f768ec9529724f8fb06539f2903a583a41
---

{{CSSRef}}

Der **`additive-symbols`** Deskriptor der {{cssxref('@counter-style')}} at-rule wird verwendet, um Zählersymbole anzugeben, wenn der `@counter-style` {{cssxref('@counter-style/system', 'system')}} Deskriptorwert auf `additive` gesetzt ist. Das additive System wird verwendet, um [Sign-Value Nummerierung](https://de.wikipedia.org/wiki/Signvalue_Notation) Systeme wie römische Zahlen zu konstruieren.

## Syntax

```css
/* Einfaches Tupel */
additive-symbols: 3 "*";

/* Kommagetrennte Liste von Tupeln */
additive-symbols:
  3 "0",
  2 "\2E\20",
  1 url(symbol.png);

/* Binärer Zähler */
additive-symbols:
  2 "1",
  1 "0";

/* Etruskischer (eine Zivilisation im alten Italien) Zähler */
additive-symbols:
  100 "𐌟",
  50 "𐌣",
  10 "𐌢",
  5 "𐌡",
  1 "𐌠";
```

### Werte

Der Deskriptor akzeptiert eine kommagetrennte Liste von _additiven Tupeln_, wobei jedes Tupel aus den folgenden zwei Werten besteht, die durch ein Leerzeichen getrennt sind:

- {{cssxref("integer")}}

  - : Ein nicht-negativer Ganzzahlwert, der das Ganzzahlgewicht des zugehörigen Symbolwerts des Tupels angibt.

- [`<symbol>`](/de/docs/Web/CSS/@counter-style/symbols#symbol)
  - : Gibt das Zählersymbol an, das für den durch das zugehörige `<integer>`-Gewicht definierte Wert verwendet werden soll.

> [!NOTE]
> Die additiven Tupel müssen in absteigender Gewichtungsreihenfolge angegeben werden; andernfalls ist die Deskriptordeklaration nicht gültig und wird ignoriert.

## Beschreibung

Der `additive-symbols` Deskriptor definiert eine kommagetrennte Liste von _additiven Tupeln_. Jedes _additive Tupel_ enthält eine durch Leerzeichen getrennte nicht-negative ganze Zahl und ein Zählersymbol. Um gültig zu sein, muss die Liste in absteigender Reihenfolge der Ganzzahl sein. Die Ganzzahl und das Symbol werden zusammengefügt, um das Zählersymbol zu bilden.

Wenn der `system` Deskriptorwert `cyclic`, `numeric`, `alphabetic`, `symbolic` oder `fixed` ist, verwenden Sie den {{cssxref('symbols')}} Deskriptor anstelle von `additive-symbols`.

## Formale Definition

{{cssinfo}}

## Formale Syntax

{{csssyntax}}

## Beispiele

### Angabe von additiven Symbolen

#### HTML

In diesem Beispiel spezifizieren {{cssxref("@counter-style/system","system: additive")}} zusammen mit den Werten des `additive-symbols` Deskriptors, wie Zahlen als römische Ziffern dargestellt werden sollen. Der Wert jedes {{HTMLElement("li")}}-Elements in der Liste wird gemäß den in {{cssxref("@counter-style")}} definierten Regeln in eine römische Zahl umgewandelt.

```html
<ul>
  <li>Eins</li>
  <li>Zwei</li>
  <li>Drei</li>
  <li>Vier</li>
  <li>Fünf</li>
  <li value="109">109</li>
  <li>110</li>
</ul>
```

#### CSS

```css
@counter-style uppercase-roman {
  system: additive;
  additive-symbols:
    1000 M,
    900 CM,
    500 D,
    400 CD,
    100 C,
    90 XC,
    50 L,
    40 XL,
    10 X,
    9 IX,
    5 V,
    4 IV,
    1 I;
}

ul {
  list-style: uppercase-roman;
  padding-left: 5em;
}
```

#### Ergebnis

{{ EmbedLiveSample('Specifying_additive_symbols') }}

Für das Listenelement mit dem Wert `109` steht das Zahlzeichen `C` für `100` und `IX` für `9`. Dies erzeugt das `CIX`-Zähler für das Listenelement `109`. Das nächste Listenelement erhält automatisch den Wert `110`. Die römische Zahl `CX` ergibt sich aus `C` für `100` und `X` für `10`.

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- {{cssxref("@counter-style")}} Deskriptoren: {{cssxref("@counter-style/system","system")}}, {{cssxref("@counter-style/symbols", "symbols")}}, {{cssxref("@counter-style/negative", "negative")}}, {{cssxref("@counter-style/prefix", "prefix")}}, {{cssxref("@counter-style/suffix", "suffix")}}, {{cssxref("@counter-style/range", "range")}}, {{cssxref("@counter-style/pad", "pad")}}, {{cssxref("@counter-style/speak-as", "speak-as")}}, {{cssxref("@counter-style/fallback", "fallback")}}
- Listendarstellungs-Eigenschaften: {{Cssxref("list-style")}}, {{Cssxref("list-style-image")}}, {{Cssxref("list-style-position")}}
- {{cssxref("symbols", "symbols()")}} Funktion zur Erstellung anonymer Zählerstile
- [CSS-Zählerstile](/de/docs/Web/CSS/CSS_counter_styles) Modul
