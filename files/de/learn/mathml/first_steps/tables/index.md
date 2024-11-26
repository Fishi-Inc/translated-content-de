---
title: MathML-Tabellen
slug: Learn/MathML/First_steps/Tables
l10n:
  sourceCommit: d4ea77f1c9e15e472e484d9561319597c5cce716
---

{{LearnSidebar}}{{PreviousMenuNext("Learn/MathML/First_steps/Scripts", "Learn/MathML/First_steps/Three_famous_mathematical_formulas", "Learn/MathML/First_steps")}}

Sobald alle grundlegenden mathematischen Notationen bekannt sind, bleibt die Betrachtung des tabellarischen Layouts, das für matrixartige Ausdrücke und andere erweiterte mathematische Layouts verwendet werden kann.

<table>
  <tbody>
    <tr>
      <th scope="row">Voraussetzungen:</th>
      <td>
        <a
          href="/de/docs/Learn/Getting_started_with_the_web/Installing_basic_software"
          >Grundlegende Software installiert</a
        >, Grundkenntnisse im
        <a
          href="/de/docs/Learn/Getting_started_with_the_web/Dealing_with_files"
          >Umgang mit Dateien</a
        > und HTML-Grundlagen (siehe
        <a href="/de/docs/Learn/HTML/Introduction_to_HTML"
          >Einführung in HTML</a
        > und <a href="/de/docs/Learn/HTML/Tables"
          >HTML-Tabellen</a
        >)
      </td>
    </tr>
    <tr>
      <th scope="row">Zielsetzung:</th>
      <td>
        Vertrautheit mit MathML-Tabellenelementen erlangen und auf einige Anwendungsfälle aufmerksam werden.
      </td>
    </tr>
  </tbody>
</table>

## MathML-Tabellenelemente

Die MathML-Tabellenelemente sind ähnlich wie die für [HTML-Tabellen](/de/docs/Learn/HTML/Tables): Das `<mtable>`-Element stellt eine mathematische Tabelle dar, es hat `<mtr>`-Elemente als Kinder (die Zeilen darstellen), von denen jedes `<mtd>`-Elemente als Kinder hat (die Zellen darstellen). Ein `<mtable>`-Element kann überall in einer MathML-Formel eingefügt werden. Das `<mtd>`-Element kann eine beliebige Anzahl von MathML-Kindern enthalten und wird diese als `<mrow>`-Container anordnen.

Tabellen werden typischerweise für matrixartige Ausdrücke (einschließlich Vektoren) verwendet. Hier ist ein einfaches Beispiel aus dem [Artikel über die CSS `matrix()` Funktion](/de/docs/Web/CSS/transform-function/matrix):

```html hidden
<link
  rel="stylesheet"
  href="https://fred-wang.github.io/MathFonts/LatinModern/mathfonts.css" />
```

```html
<math display="block">
  <mrow>
    <mo>(</mo>
    <mtable>
      <mtr>
        <mtd>
          <mi>a</mi>
        </mtd>
        <mtd>
          <mi>c</mi>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <msub>
            <mi>t</mi>
            <mi>x</mi>
          </msub>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mi>b</mi>
        </mtd>
        <mtd>
          <mi>d</mi>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <msub>
            <mi>t</mi>
            <mi>y</mi>
          </msub>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
      </mtr>
      <mtr>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>0</mn>
        </mtd>
        <mtd>
          <mn>1</mn>
        </mtd>
      </mtr>
    </mtable>
    <mo>)</mo>
  </mrow>
</math>
```

{{ EmbedLiveSample('MathML_tabular_elements', 700, 200, "", "") }}

## Ermöglichung, dass Zellen mehrere Zeilen und Spalten überspannen

Dies ist wieder ähnlich wie bei [HTML-Tabellen](/de/docs/Learn/HTML/Tables/Basics#allowing_cells_to_span_multiple_rows_and_columns). Das `<mtd>`-Element akzeptiert die Attribute `columnspan` und `rowspan`, um anzuzeigen, dass die Zelle mehrere Zeilen und Spalten überspannt. Unten überspannt die innere Matrix zwei Spalten der äußeren Matrix:

```html hidden
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>My matrix with columnspan</title>
    <link
      rel="stylesheet"
      href="https://fred-wang.github.io/MathFonts/LatinModern/mathfonts.css" />
  </head>
  <body>
    <math display="block">
      <mrow>
        <mo>(</mo>
        <mtable>
          <mtr>
            <mtd columnspan="2">
              <mrow>
                <mo>(</mo>
                <mtable>
                  <mtr>
                    <mtd>
                      <mi>a</mi>
                    </mtd>
                    <mtd>
                      <mi>c</mi>
                    </mtd>
                  </mtr>
                  <mtr>
                    <mtd>
                      <mi>b</mi>
                    </mtd>
                    <mtd>
                      <mi>d</mi>
                    </mtd>
                  </mtr>
                </mtable>
                <mo>)</mo>
              </mrow>
            </mtd>
            <mtd>
              <mn>0</mn>
            </mtd>
            <mtd>
              <mi>T</mi>
            </mtd>
          </mtr>
          <mtr>
            <mtd>
              <mn>0</mn>
            </mtd>
            <mtd>
              <mn>0</mn>
            </mtd>
            <mtd>
              <mn>1</mn>
            </mtd>
            <mtd>
              <mn>0</mn>
            </mtd>
          </mtr>
          <mtr>
            <mtd>
              <mn>0</mn>
            </mtd>
            <mtd>
              <mn>0</mn>
            </mtd>
            <mtd>
              <mn>0</mn>
            </mtd>
            <mtd>
              <mn>1</mn>
            </mtd>
          </mtr>
        </mtable>
        <mo>)</mo>
      </mrow>
    </math>
  </body>
</html>
```

{{ EmbedLiveSample('allowing_cells_to_span_multiple_rows_and_columns', 700, 200, "", "") }}

> [!NOTE]
> Aus historischen Gründen heißt das MathML-Attribut für das Überspannen von Spalten `columnspan` und nicht `colspan`.

## Verwendung für erweiterte Layouts

Neben der Darstellung matrixartiger Objekte werden MathML-Tabellen manchmal für erweiterte Layouts in mathematischen Formeln verwendet, beispielsweise in [Wikipedias Definition des Legendre-Symbols](https://en.wikipedia.org/wiki/Legendre_symbol). Hier sind die verschiedenen Fälle auf drei unterschiedlichen Zeilen geschrieben, während die Werte und Bedingungen in zwei unterschiedlichen Spalten platziert sind.

```html hidden
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>My first matrix</title>
    <link
      rel="stylesheet"
      href="https://fred-wang.github.io/MathFonts/LatinModern/mathfonts.css" />
  </head>
  <body>
    <math display="block">
      <mrow>
        <mrow>
          <mo>(</mo>
          <mfrac>
            <mi>a</mi>
            <mi>b</mi>
          </mfrac>
          <mo>)</mo>
        </mrow>
        <mo>=</mo>
        <mrow>
          <mo>{</mo>
          <mtable>
            <mtr>
              <mtd>
                <mn>1</mn>
              </mtd>
              <mtd>
                <mtext>if&nbsp;</mtext>
                <mi>a</mi>
                <mtext>&nbsp;is a quadratic residue modulo&nbsp;</mtext>
                <mi>p</mi>
                <mtext>&nbsp;and&nbsp;</mtext>
                <mi>a</mi>
                <mtext>&nbsp;is not a multiple of&nbsp;</mtext>
                <mi>p</mi>
                <mo>;</mo>
              </mtd>
            </mtr>
            <mtr>
              <mtd>
                <mo>−</mo>
                <mn>1</mn>
              </mtd>
              <mtd>
                <mtext>if&nbsp;</mtext>
                <mi>a</mi>
                <mtext>&nbsp;is a non-quadratic residue modulo&nbsp;</mtext>
                <mi>p</mi>
                <mo>;</mo>
              </mtd>
            </mtr>
            <mtr>
              <mtd>
                <mn>0</mn>
              </mtd>
              <mtd>
                <mtext>if&nbsp;</mtext>
                <mi>a</mi>
                <mtext>&nbsp;is a multiple of&nbsp;</mtext>
                <mi>p</mi>
                <mo>.</mo>
              </mtd>
            </mtr>
          </mtable>
        </mrow>
      </mrow>
    </math>
  </body>
</html>
```

{{ EmbedLiveSample('Usage_for_advanced_layout', 700, 200, "", "") }}

> [!WARNING]
> Der [`<mtable>`-Artikel](/de/docs/Web/MathML/Element/mtable) bietet über spezielle Attribute wie Ausrichtung oder Abstand fortgeschrittene Layout-Optionen. Diese entstanden vor den entsprechenden CSS-Äquivalenten und wurden ursprünglich für Renderer entwickelt, die nicht CSS-bewusst waren. Diese Attribute sind jedoch möglicherweise nicht in allen Browsern implementiert. In Zukunft ist es wahrscheinlich, dass die Verwendung von `<mtable>` für reine Layout-Zwecke (d.h. keine tatsächlichen matrixartigen Objekte) durch CSS-basierte Alternativen ersetzt werden kann.

## Zusammenfassung

In diesem Artikel haben wir die `<mtable>`, `<mtr>` und `<mtd>`-Elemente besprochen, die die Entsprechungen der HTML-Elemente für Tabellen sind. Wir haben gesehen, wie man sie zur Darstellung matrixartiger Objekte verwenden kann und wie sie manchmal für erweiterte Layouts verwendet werden.

Sie haben dieses Modul fast abgeschlossen — es gibt nur noch eine Sache zu tun. In der [Bewertung der drei berühmten mathematischen Formeln](/de/docs/Learn/MathML/First_steps/Three_famous_mathematical_formulas) werden Sie Ihr neues Wissen einsetzen, um einen kleinen mathematischen Artikel mit HTML und MathML neu zu schreiben.

{{LearnSidebar}}{{PreviousMenuNext("Learn/MathML/First_steps/Scripts", "Learn/MathML/First_steps/Three_famous_mathematical_formulas", "Learn/MathML/First_steps")}}

## Siehe auch

- [Informationen zu HTML-Tabellen](/de/docs/Learn/HTML/Tables)
- [Das `<mtable>`-Element](/de/docs/Web/MathML/Element/mtable)
- [Das `<mtr>`-Element](/de/docs/Web/MathML/Element/mtr)
- [Das `<mtd>`-Element](/de/docs/Web/MathML/Element/mtd)
