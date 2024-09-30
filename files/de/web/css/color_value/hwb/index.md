---
title: hwb()
slug: Web/CSS/color_value/hwb
l10n:
  sourceCommit: 4e508e2f543c0d77c9c04f406ebc8e9db7e965be
---

{{CSSRef}}

Die **`hwb()`** funktionale Notation drückt eine Farbe im [sRGB](/de/docs/Glossary/RGB) [Farbraum](/de/docs/Glossary/color_space) gemäß ihrem Farbton, der Weißheit und der Schwärze aus. Ein optionaler Alpha-Wert repräsentiert die Transparenz der Farbe.

{{EmbedInteractiveExample("pages/css/function-hwb.html")}}

## Syntax

```css
/* Absolute values */
hwb(194 0% 0%)
hwb(194 0% 0% / .5)

/* Relative values */
hwb(from green h w b / 0.5)
hwb(from #0000FF h calc(w + 30) b)
hwb(from lch(40% 70 240deg) h w calc(b - 30))
```

## Beschreibung

Diese Farb-Funktion im [`sRGB` Farbraum](/de/docs/Glossary/Color_space#srgb) wird durch einen {{CSSXref("&lt;hue&gt;")}} Winkelwert, einen Wert für die Weißheit, einen Wert für die Schwärze und optional einen Alpha-Wert definiert, der die Transparenz der Farbe repräsentiert.

Die Winkel, die bestimmten Farbtönen entsprechen, unterscheiden sich im sRGB (verwendet von {{CSSXref("color_value/hsl", "hsl()")}} und `hwb()`), CIELAB (verwendet von {{CSSXref("color_value/lch", "lch()")}}) und Oklab (verwendet von {{CSSXref("color_value/oklch", "oklch()")}}) Farbräumen. `hwb()` befindet sich im gleichen Farbraum wie `hsl()` und hat daher die gleichen Farbton-Winkel. Weitere Details und Beispiele finden Sie auf der {{CSSXref("&lt;hue&gt;")}} Referenzseite, oder probieren Sie, die Farbtöne im [Farbwähler](/de/docs/Web/CSS/CSS_colors#colors_in_action) zu ändern, um es in Aktion zu sehen.

Eine `hwb()` Farbe ist vollständig gesättigt, wenn sowohl der Weißheits- (`W`) als auch der Schwärze-Wert (`B`) `0` sind. Für jeden Farbwert `H` entspricht `hwb(H 0% 0%)` derselben Farbe wie `hsl(H 100% 50%)`. Ein erhöhter Weißheitswert hellt die Farbe auf. Ein erhöhter Schwärzewert verdunkelt die Farbe.

Wenn sowohl der Schwärze- als auch der Weißheitswert größer als 0 sind, wird die Farbe gedämpft und tendiert zu Grau. Wenn die Summe der Weißheits- und Schwärzewerte gleich oder größer als 100% ist — also, wenn `W + B >= 100%`, definiert die Farbfunktion einen Grauton. Wenn die Summe beider Werte größer als 100% ist (`W + B > 100%`), werden die Weißheits- und Schwärzewerte der Graufarbe effektiv als `W / (W + B)` und `B / (W + B)` normalisiert.

## Werte

Im Folgenden finden Sie Beschreibungen der zulässigen Werte für absolute und [relative Farben](/de/docs/Web/CSS/CSS_colors/Relative_colors).

### Absolute Wert-Syntax

```plain
hwb(H W B[ / A])
```

Die Parameter sind wie folgt:

- `H`

  - : Eine {{CSSXref("&lt;number&gt;")}}, ein {{CSSXref("&lt;angle&gt;")}}, oder das Schlüsselwort `none` (entspricht in diesem Fall `0deg`), das den {{CSSXref("&lt;hue&gt;")}} Winkel der Farbe repräsentiert.

- `W`

  - : Ein {{CSSXref("&lt;percentage&gt;")}}, das die Weißheit der Farbe repräsentiert oder das Schlüsselwort `none` (entspricht in diesem Fall `0%`), um es zu mischen. `0%` repräsentiert keine Weißheit. `100%` repräsentiert volle Weißheit, wenn `B` `0` ist, andernfalls werden sowohl die `W` als auch die `B` Werte normalisiert.

- `B`

  - : Ein {{CSSXref("&lt;percentage&gt;")}}, das die Schwärze der Farbe repräsentiert oder das Schlüsselwort `none` (entspricht in diesem Fall `0%`), um es zu mischen. `0%` repräsentiert keine Schwärze. `100%` repräsentiert volle Schwärze, wenn `W` `0` ist, andernfalls werden sowohl die `W` als auch die `B` Werte normalisiert.

- `A` {{optional_inline}}

  - : Ein {{CSSXref("&lt;alpha-value&gt;")}}, das den Alpha-Kanal-Wert der Farbe repräsentiert, wobei die Zahl `0` `0%` (vollständig transparent) und `1` `100%` (vollständig deckend) entspricht. Zusätzlich kann das Schlüsselwort `none` verwendet werden, um explizit keinen Alpha-Kanal anzugeben. Wenn der `A` Kanalwert nicht explizit angegeben wird, beträgt er standardmäßig 100%. Wenn er enthalten ist, wird der Wert von einem Schrägstrich (`/`) vorangestellt.

> [!NOTE]
> Weitere Informationen über die Auswirkungen von `none` finden Sie unter [Fehlende Farbkomponenten](/de/docs/Web/CSS/color_value#missing_color_components).

> [!NOTE]
> Absolute `hwb()` Farben werden zu {{CSSXref("color_value/rgb", "rgb()")}} Werten serialisiert. Die Werte der Komponenten Rot, Grün und Blau können bei der Serialisierung gerundet werden.

### Relative Wert-Syntax

```plain
hwb(from <color> H W B[ / A])
```

Die Parameter sind wie folgt:

- `from <color>`

  - : Das Schlüsselwort `from` ist immer enthalten, wenn eine relative Farbe definiert wird, gefolgt von einem {{cssxref("&lt;color&gt;")}} Wert, der die **Ursprungsfarbe** darstellt. Dies ist die ursprüngliche Farbe, auf der die relative Farbe basiert. Die Ursprungsfarbe kann _jede_ gültige {{cssxref("&lt;color&gt;")}} Syntax sein, einschließlich einer anderen relativen Farbe.

- `H`

  - : Eine {{CSSXref("&lt;number&gt;")}}, ein {{CSSXref("&lt;angle&gt;")}}, oder das Schlüsselwort `none` (entspricht in diesem Fall `0deg`), das den {{CSSXref("&lt;hue&gt;")}} Winkel der Ausgabefarbe repräsentiert.

- `W`

  - : Ein {{CSSXref("&lt;percentage&gt;")}}, das die Weißheit der Farbe repräsentiert oder das Schlüsselwort `none` (entspricht in diesem Fall `0%`), um es zu mischen. `0%` repräsentiert keine Weißheit. `100%` repräsentiert volle Weißheit, wenn `B` `0` ist, andernfalls werden sowohl die `W` als auch die `B` Werte normalisiert.

- `B`

  - : Ein {{CSSXref("&lt;percentage&gt;")}}, das die Schwärze der Farbe repräsentiert oder das Schlüsselwort `none` (entspricht in diesem Fall `0%`), um es zu mischen. `0%` repräsentiert keine Schwärze. `100%` repräsentiert volle Schwärze, wenn `W` `0` ist, andernfalls werden sowohl die `W` als auch die `B` Werte normalisiert.

- `A` {{optional_inline}}
  - : Ein {{CSSXref("&lt;alpha-value&gt;")}}, das den Alpha-Kanal-Wert der Ausgabefarbe repräsentiert, wobei die Zahl `0` `0%` (vollständig transparent) und `1` `100%` (vollständig deckend) entspricht. Zusätzlich kann das Schlüsselwort `none` verwendet werden, um explizit keinen Alpha-Kanal anzugeben. Wenn der `A` Kanalwert nicht explizit angegeben wird, entspricht er standardmäßig dem Alpha-Kanalwert der Ursprungsfarbe. Wenn er enthalten ist, wird der Wert von einem Schrägstrich (`/`) vorangestellt.

> [!NOTE]
> Um die vollständige Darstellung des sichtbaren Farbspektrums zu ermöglichen, wird die Ausgabe der relativen `hwb()` Farb-Funktionen zu `color(srgb)` serialisiert. Das bedeutet, dass die Abfrage des Ausgabefarbwerts über die [`HTMLElement.style`](/de/docs/Web/API/HTMLElement/style) Eigenschaft oder die [`CSSStyleDeclaration.getPropertyValue()`](/de/docs/Web/API/CSSStyleDeclaration/getPropertyValue) Methode den Ausgabefarbwert als [`color(srgb ...)`](/de/docs/Web/CSS/color_value/color) Wert zurückgibt.

### Definition der Ausgabe der relativen Farbkanal-Komponenten

Bei der Verwendung der relativen Farbsyntax innerhalb einer `hwb()` Funktion konvertiert der Browser die Ursprungsfarbe in eine äquivalente HWB-Farbe (wenn sie nicht bereits als solche spezifiziert ist). Die Farbe wird als drei unterscheidbare Farbkanalwerte definiert — `h` (Farbton), `w` (Weiß) und `b` (Schwarz) — plus einen Alpha-Kanalwert (`alpha`). Diese Kanalwerte sind innerhalb der Funktion verfügbar, um sie bei der Definition der Ausgabefarbkanalwerte zu verwenden:

- Der `h` Kanalwert wird auf eine `<number>` zwischen `0` und `360` aufgelöst, inklusiv.
- Die `w` und `b` Kanäle werden jeweils auf eine `<number>` zwischen `0` und `100` aufgelöst, inklusiv.
- Der `alpha` Kanal wird auf eine `<number>` zwischen `0` und `1` aufgelöst, inklusiv.

Bei der Definition einer relativen Farbe können die verschiedenen Kanäle der Ausgabefarbe auf unterschiedliche Weise ausgedrückt werden. Im Folgenden werden einige Beispiele betrachtet, um diese zu veranschaulichen.

In den ersten beiden Beispielen unten verwenden wir relative Farbsyntax. Jedoch gibt das erste Beispiel die gleiche Farbe wie die Ursprungsfarbe aus, und das zweite gibt eine Farbe aus, die überhaupt nicht auf der Ursprungsfarbe basiert. Sie erzeugen eigentlich keine relativen Farben! Sie würden diese Fälle wahrscheinlich nie in einem echten Codebase verwenden und stattdessen einfach einen absoluten Farbwert verwenden. Wir haben diese Beispiele als Ausgangspunkt für das Lernen über die relative `hwb()` Syntax eingeschlossen.

Lassen Sie uns mit einer Ursprungsfarbe von `hsl(0 100% 50%)` (äquivalent zu `hwb(0 0% 0%)`) beginnen. Die folgende Funktion gibt die gleiche Farbe wie die Ursprungsfarbe aus — sie verwendet die `h`, `w` und `b` Kanalwerte (`0`, `0%` und `0%`) der Ursprungsfarbe als die Ausgabekanalwerte:

```css
hwb(from hsl(0 100% 50%) h w b)
```

Die Ausgabe dieser Funktion ist das sRGB `color()` Äquivalent von `hwb(0 0% 0%)`: `color(srgb 1 0 0)`.

Die nächste Funktion verwendet absolute Werte für die Ausgabefarbkanalwerte und gibt eine vollständig andere Farbe aus, die nicht auf der Ursprungsfarbe basiert:

```css
hwb(from hsl(0 100% 50%) 240 52% 12%)
```

Im obigen Fall ist die Ausgabefarbe das sRGB `color()` Äquivalent von `hwb(240 52% 12%)`: `color(srgb 0.52 0.52 0.88)`.

Die folgende Funktion erstellt eine relative Farbe basierend auf der Ursprungsfarbe:

```css
hwb(from hsl(0 100% 50%) h 30% b)
```

Dieses Beispiel:

- Konvertiert die Ursprungsfarbe (`hsl(0 100% 50%)`) in ein äquivalentes `hwb()` (`hwb(0 0% 0%)`).
- Setzt die `H` und `B` Kanalwerte für die Ausgabefarbe zu denen der Ursprungsfarbe `hwb()` äquivalenten `H` und `B` Kanalwerte — diese Werte sind `0` und `0%`, jeweils.
- Setzt den `W` Kanalwert der Ausgabefarbe auf einen neuen Wert, der nicht auf der Ursprungsfarbe basiert: `30%`.

Die endgültige Ausgabefarbe ist das Äquivalent von `hwb(0 30% 0%)` im sRGB Farbraum — `color(srgb 1 0.3 0.3)`.

> [!NOTE]
> Wie oben erwähnt, wenn die Ausgabefarbe ein anderes Farbmodell als die Ursprungsfarbe verwendet, wird die Ursprungsfarbe im Hintergrund in das gleiche Modell oder den gleichen Raum wie die Ausgabefarbe konvertiert, damit sie auf eine Weise dargestellt werden kann, die kompatibel ist (d. h. unter Verwendung derselben Kanäle).

In den Beispielen, die wir bisher in diesem Abschnitt gesehen haben, wurden die Alpha-Kanäle weder für die Ursprungs- noch für die Ausgabefarben explizit angegeben. Wenn der Alpha-Kanal der Ausgabefarbe nicht angegeben wird, entspricht er standardmäßig demselben Wert wie der Alpha-Kanal der Ursprungsfarbe. Wenn der Alpha-Kanal der Ursprungsfarbe nicht angegeben wird (und es sich nicht um eine relative Farbe handelt), ist er standardmäßig `1`. Daher sind die Ursprungs- und Ausgabewerte des Alpha-Kanals für die obigen Beispiele `1`.

Lassen Sie uns einige Beispiele ansehen, die Origin- und Ausgabe-Alpha-Kanal-Werte spezifizieren. Das erste spezifiziert den Ausgabe-Alpha-Kanal-Wert als gleich dem Ursprungs-Alpha-Kanal-Wert, während das zweite einen anderen Ausgabe-Alpha-Kanal-Wert spezifiziert, der nicht mit dem Ursprungs-Alpha-Kanal-Wert verwandt ist.

```css
hwb(from hsl(0 100% 50% / 0.8) h w b / alpha)
/* Computed output color: color(srgb 1 0 0 / 0.8) */

hwb(from hsl(0 100% 50% / 0.8) h w b / 0.5)
/* Computed output color: color(srgb 1 0 0 / 0.5) */
```

Im folgenden Beispiel wird die `hsl()` Ursprungsfarbe erneut in eine `hwb()` Darstellung konvertiert — `hwb(0 0% 0%)`. {{cssxref("calc")}} Berechnungen werden auf die `H`, `W`, `B`, und `A` Werte angewendet, und die finale Ausgabefarbe ist das Äquivalent von `hwb(120 25% 10% / 0.9` im sRGB Farbraum: `color(srgb 0.25 0.9 0.25 / 0.9)`.

```css
hwb(from hsl(0 100% 50%) calc(h + 120) calc(w + 25) calc(b + 10) / calc(alpha - 0.1))
```

> [!NOTE]
> Da die Ursprungsfarbkanalwerte auf `<number>` Werte aufgelöst werden, müssen Sie Zahlen hinzufügen, wenn Sie sie in Berechnungen verwenden, selbst in Fällen, in denen ein Kanal normalerweise `<percentage>`, `<angle>` oder andere Werttypen akzeptieren würde. Das Hinzufügen eines `<percentage>` zu einer `<number>` funktioniert beispielsweise nicht.

## Formale Syntax

{{csssyntax}}

## Beispiele

### Verwendung relativer Farben mit hwb()

Dieses Beispiel stylt drei {{htmlelement("div")}} Elemente mit unterschiedlichen Hintergrundfarben. Das mittlere erhält die unmodifizierte `--base-color`, während die linken und rechten aufgehellte und abgedunkelte Varianten dieser `--base-color` erhalten.

Diese Varianten werden unter Verwendung relativer Farben definiert — die `--base-color` [benutzerdefinierte Eigenschaft](/de/docs/Web/CSS/--*) wird in eine `hwb()` Funktion übergeben, und die Ausgabefarben haben ihre Weiß- und Schwarzkanäle modifiziert, um den gewünschten Effekt über eine `calc()` Funktion zu erzielen. Die aufgehellte Farbe hat 30% zum Weißkanal hinzugefügt, und die abgedunkelte Farbe hat 30% zum Schwarzk kanal hinzugefügt.

```html hidden
<div id="container">
  <div class="item" id="one"></div>
  <div class="item" id="two"></div>
  <div class="item" id="three"></div>
</div>
```

#### CSS

```css hidden
#container {
  display: flex;
  width: 100vw;
  height: 100vh;
  box-sizing: border-box;
}

.item {
  flex: 1;
  margin: 20px;
}
```

```css
:root {
  --base-color: orange;
}

/* As per the spec, w and b values should resolve to a number between 0-100
   However, Chrome 121+ incorrectly resolves them to numbers between 0-1
   hence currently using calculations like w + 0.3 instead of w + 30 */

#one {
  background-color: hwb(from var(--base-color) h calc(w + 0.3) b);
}

#two {
  background-color: var(--base-color);
}

#three {
  background-color: hwb(from var(--base-color) h w calc(b + 0.3));
}

/* Use @supports to add in support for old syntax that requires % units to
   be specified in w and b calculations. This is required for Safari 16.4+. */
@supports (color: hwb(from red h w calc(b + 30%))) {
  #one {
    background-color: hwb(from var(--base-color) h calc(w + 30%) b);
  }

  #three {
    background-color: hwb(from var(--base-color) h w calc(b + 30%));
  }
}
```

#### Ergebnis

Die Ausgabe ist wie folgt:

{{ EmbedLiveSample("Using relative colors with hwb()", "100%", "200") }}

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- {{CSSXref("&lt;color&gt;")}}: Für eine Liste aller Farbnotationen
- [Farbwähler und Konvertierungswerkzeug](/de/docs/Web/CSS/CSS_colors/Color_picker_tool)
- [Verwendung relativer Farben](/de/docs/Web/CSS/CSS_colors/Relative_colors)
- [CSS-Farben](/de/docs/Web/CSS/CSS_colors) Modul
- {{CSSXref("&lt;hue&gt;")}}: der Datentyp, der einen Farbtonwinkel einer Farbe darstellt
