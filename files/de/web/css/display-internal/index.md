---
title: <display-intern>
slug: Web/CSS/display-internal
l10n:
  sourceCommit: 0b0064888cb364d442e92d6a850db9b53ed1c470
---

{{CSSRef}}

Einige Layoutmodelle wie `table` und `ruby` haben eine komplexe interne Struktur mit mehreren verschiedenen Rollen, die ihre Kinder und Nachkommen ausfüllen können. Diese Seite definiert jene "internen" Anzeige-Werte, die nur innerhalb dieses bestimmten Layoutmodus von Bedeutung sind.

## Syntax

Gültige `<display-internal>` Werte:

- `table-row-group`
  - : Diese Elemente verhalten sich wie {{HTMLElement("tbody")}} HTML-Elemente.
- `table-header-group`
  - : Diese Elemente verhalten sich wie {{HTMLElement("thead")}} HTML-Elemente.
- `table-footer-group`
  - : Diese Elemente verhalten sich wie {{HTMLElement("tfoot")}} HTML-Elemente.
- `table-row`
  - : Diese Elemente verhalten sich wie {{HTMLElement("tr")}} HTML-Elemente.
- `table-cell`
  - : Diese Elemente verhalten sich wie {{HTMLElement("td")}} HTML-Elemente.
- `table-column-group`
  - : Diese Elemente verhalten sich wie {{HTMLElement("colgroup")}} HTML-Elemente.
- `table-column`
  - : Diese Elemente verhalten sich wie {{HTMLElement("col")}} HTML-Elemente.
- `table-caption`
  - : Diese Elemente verhalten sich wie {{HTMLElement("caption")}} HTML-Elemente.
- `ruby-base`
  - : Diese Elemente verhalten sich wie {{HTMLElement("rb")}} HTML-Elemente.
- `ruby-text`
  - : Diese Elemente verhalten sich wie {{HTMLElement("rt")}} HTML-Elemente.
- `ruby-base-container`
  - : Diese Elemente werden als anonyme Boxen generiert.
- `ruby-text-container`
  - : Diese Elemente verhalten sich wie {{HTMLElement("rtc")}} HTML-Elemente.

## Formale Syntax

{{csssyntax}}

## Beispiele

### Beispiel für CSS-Tabellen

Das folgende Beispiel demonstriert das Layout eines einfachen Formulars unter Verwendung des CSS-Tabellenlayouts.

#### HTML

```html
<main>
  <div>
    <label for="name">Name</label>
    <input type="text" id="name" name="name" />
  </div>
  <div>
    <label for="age">Age</label>
    <input type="text" id="age" name="age" />
  </div>
</main>
```

#### CSS

```css
main {
  display: table;
}

div {
  display: table-row;
}

label,
input {
  display: table-cell;
  margin: 5px;
}
```

#### Ergebnis

{{EmbedLiveSample('CSS_tables_example', '100%', 100)}}

## Spezifikationen

{{Specifications}}

## Browserkompatibilität

{{Compat}}

## Siehe auch

- {{CSSxRef("display")}}

  - {{CSSxRef("&lt;display-outside&gt;")}}
  - {{CSSxRef("&lt;display-inside&gt;")}}
  - {{CSSxRef("&lt;display-listitem&gt;")}}
  - {{CSSxRef("&lt;display-box&gt;")}}
  - {{CSSxRef("&lt;display-legacy&gt;")}}
