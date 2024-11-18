---
title: ":where()"
slug: Web/CSS/:where
l10n:
  sourceCommit: 632289fcc10e926d166e1b49e5ba3505de182856
---

{{CSSRef}}

Die **`:where()`** [CSS](/de/docs/Web/CSS) [Pseudoklasse](/de/docs/Web/CSS/Pseudo-classes) Funktion nimmt eine Selektorliste als Argument und wählt jedes Element aus, das durch einen der Selektoren in dieser Liste ausgewählt werden kann.

Der Unterschied zwischen `:where()` und {{CSSxRef(":is", ":is()")}} besteht darin, dass `:where()` immer eine [Spezifität](/de/docs/Web/CSS/Specificity) von 0 hat, während `:is()` die Spezifität des spezifischsten Selektors in seinen Argumenten übernimmt.

{{EmbedInteractiveExample("pages/tabbed/pseudo-class-where.html", "tabbed-shorter")}}

## Syntax

Die `:where()` Pseudoklasse erfordert eine [Selektorliste](/de/docs/Web/CSS/CSS_selectors/Selector_structure#selector_list), eine kommagetrennte Liste von einem oder mehreren Selektoren, als Argument. Die Liste darf kein [Pseudoelement](/de/docs/Web/CSS/Pseudo-elements) enthalten, aber alle anderen einfachen, zusammengesetzten und komplexen Selektoren sind erlaubt.

```css-nolint
:where(<complex-selector-list>) {
  /* ... */
}
```

### Fehlertolerante Selektorparsing

Die Spezifikation definiert `:is()` und `:where()` als akzeptierend eine [fehlertolerante Selektorliste](https://drafts.csswg.org/selectors-4/#typedef-forgiving-selector-list).

In CSS wird bei Verwendung einer Selektorliste die gesamte Liste als ungültig betrachtet, wenn einer der Selektoren ungültig ist. Bei der Verwendung von `:is()` oder `:where()` wird, anstatt die gesamte Liste der Selektoren als ungültig zu betrachten, bei der einer nicht analysiert werden kann, der fehlerhafte oder nicht unterstützte Selektor ignoriert und die anderen verwendet.

```css
:where(:valid, :unsupported) {
  /* … */
}
```

Wird weiterhin korrekt analysiert und passt auf `:valid` selbst in Browsern, die `:unsupported` nicht unterstützen, während:

```css
:valid,
:unsupported {
  /* … */
}
```

In Browsern ignoriert wird, die `:unsupported` nicht unterstützen, selbst wenn sie `:valid` unterstützen.

## Beispiele

### Vergleich von :where() und :is()

Dieses Beispiel zeigt, wie `:where()` funktioniert und veranschaulicht auch den Unterschied zwischen `:where()` und `:is()`.

Betrachten Sie das folgende HTML:

```html
<article>
  <h2>:is()-styled links</h2>
  <section class="is-styling">
    <p>
      Here is my main content. This
      <a href="https://mozilla.org">contains a link</a>.
    </p>
  </section>

  <aside class="is-styling">
    <p>
      Here is my aside content. This
      <a href="https://developer.mozilla.org">also contains a link</a>.
    </p>
  </aside>

  <footer class="is-styling">
    <p>
      This is my footer, also containing
      <a href="https://github.com/mdn">a link</a>.
    </p>
  </footer>
</article>

<article>
  <h2>:where()-styled links</h2>
  <section class="where-styling">
    <p>
      Here is my main content. This
      <a href="https://mozilla.org">contains a link</a>.
    </p>
  </section>

  <aside class="where-styling">
    <p>
      Here is my aside content. This
      <a href="https://developer.mozilla.org">also contains a link</a>.
    </p>
  </aside>

  <footer class="where-styling">
    <p>
      This is my footer, also containing
      <a href="https://github.com/mdn">a link</a>.
    </p>
  </footer>
</article>
```

In diesem etwas konstruierten Beispiel haben wir zwei Artikel, die jeweils einen Abschnitt, einen Seitenrand und eine Fußzeile enthalten. Sie unterscheiden sich durch die Klassen, die verwendet werden, um die Kindelemente zu markieren.

Um die Auswahl von Links zu gruppieren und gleichzeitig die `is-styling` und `where-styling` Stile unterschiedlich zu halten, _könnten_ wir `:is()` oder `:where()` auf folgende Weise verwenden:

```css
html {
  font-family: sans-serif;
  font-size: 150%;
}

:is(section.is-styling, aside.is-styling, footer.is-styling) a {
  color: red;
}

:where(section.where-styling, aside.where-styling, footer.where-styling) a {
  color: orange;
}
```

Was aber, wenn wir später die Farbe der Links in den Fußzeilen mit einem zusammengesetzten Selektor aus Selektoren mit niedriger Spezifität überschreiben möchten?

```css
footer a {
  color: blue;
}
```

Dies wird für die roten Links nicht funktionieren, da die Selektoren innerhalb von `:is()` zur Spezifität des gesamten Selektors beitragen und Klassenselektoren eine höhere Spezifität als Elementselektoren haben.

Allerdings haben Selektoren innerhalb von `:where()` eine Spezifität von 0, so dass der orangefarbene Link in der Fußzeile durch unseren nur aus Typen bestehenden zusammengesetzten Selektor überschrieben wird.

> [!NOTE]
> Sie können dieses Beispiel auch auf GitHub finden; siehe [is-where](https://mdn.github.io/css-examples/is-where/).

{{EmbedLiveSample('Examples', '100%', 600)}}

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- {{CSSxRef(":is", ":is()")}}
- [Selektorliste](/de/docs/Web/CSS/Selector_list)
- [Webkomponenten](/de/docs/Web/API/Web_components)
