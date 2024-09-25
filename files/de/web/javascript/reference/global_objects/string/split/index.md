---
title: String.prototype.split()
slug: Web/JavaScript/Reference/Global_Objects/String/split
l10n:
  sourceCommit: 8421c0cd94fa5aa237c833ac6d24885edbc7d721
---

{{JSRef}}

Die **`split()`**-Methode von {{jsxref("String")}}-Werten nimmt ein Muster, teilt diesen String in eine geordnete Liste von Substrings, indem sie nach dem Muster sucht, platziert diese Substrings in ein Array und gibt das Array zurück.

{{EmbedInteractiveExample("pages/js/string-split.html", "taller")}}

## Syntax

```js-nolint
split(separator)
split(separator, limit)
```

### Parameter

- `separator`
  - : Das Muster, das beschreibt, wo jede Teilung erfolgen soll. Kann `undefined`, ein String oder ein Objekt mit einer [`Symbol.split`](/de/docs/Web/JavaScript/Reference/Global_Objects/Symbol/split)-Methode sein — das typische Beispiel ist ein {{jsxref("RegExp", "regulärer Ausdruck", "", 1)}}. Das Weglassen von `separator` oder das Übergeben von `undefined` führt dazu, dass `split()` ein Array mit dem aufrufenden String als einziges Element zurückgibt. Alle Werte, die nicht `undefined` oder Objekte mit einer `[Symbol.split]()`-Methode sind, werden [in Strings umgewandelt](/de/docs/Web/JavaScript/Reference/Global_Objects/String#string_coercion).
- `limit` {{optional_inline}}
  - : Eine nicht-negative Ganzzahl, die ein Limit für die Anzahl der Substrings angibt, die im Array enthalten sein sollen. Wenn angegeben, teilt die Methode den String bei jedem Auftreten des angegebenen `separator`, stoppt jedoch, wenn `limit`-Einträge im Array platziert worden sind. Jeglicher Text, der übrig bleibt, wird im Array überhaupt nicht berücksichtigt.
    - Das Array kann weniger Einträge als `limit` enthalten, wenn das Ende des Strings erreicht wird, bevor das Limit erreicht ist.
    - Wenn `limit` `0` ist, wird `[]` zurückgegeben.

### Rückgabewert

Ein {{jsxref("Array")}} von Strings, die an jedem Punkt geteilt wurden, wo der `separator` im gegebenen String auftritt.

## Beschreibung

Wenn `separator` ein nicht-leerer String ist, wird der Zielstring durch alle Vorkommen des `separator` geteilt, ohne dass `separator` in die Ergebnisse übernommen wird. Beispielsweise könnte ein String mit tabulatorgetrennten Werten (TSV) durch Übergeben eines Tabulatorzeichens als Trennzeichen geparst werden, wie `myString.split("\t")`. Wenn `separator` mehrere Zeichen enthält, muss diese gesamte Zeichenfolge gefunden werden, um eine Teilung vorzunehmen. Wenn `separator` am Anfang (oder Ende) des Strings auftritt, hat es dennoch die Wirkung der Teilung, was dazu führt, dass ein leerer (d.h. null Länge) String an der ersten (oder letzten) Position des zurückgegebenen Arrays erscheint. Wenn `separator` nicht in `str` vorkommt, enthält das zurückgegebene Array ein Element, das aus dem gesamten String besteht.

Wenn `separator` ein leerer String (`""`) ist, wird `str` in ein Array mit jedem seiner UTF-16-"Zeichen" umgewandelt, ohne leere Strings an beiden Enden des resultierenden Strings.

> **Hinweis:** `"".split("")` ist daher der einzige Weg, ein leeres Array zu erzeugen, wenn ein String als `separator` übergeben wird und `limit` nicht `0` ist.

> [!WARNING]
> Wenn der leere String (`""`) als Trennzeichen verwendet wird, wird der String **nicht** durch _vom Benutzer wahrgenommene Zeichen_ ([Grapheme-Cluster](https://unicode.org/reports/tr29/#Grapheme_Cluster_Boundaries)) oder Unicode-Zeichen (Codepunkte) geteilt, sondern durch UTF-16-Codeeinheiten. Dies zerstört [Surrogat-Paare](https://unicode.org/faq/utf_bom.html#utf16-2). Siehe ["Wie konvertiert man einen String in ein Zeichen-Array in JavaScript?" auf StackOverflow](https://stackoverflow.com/questions/4547609/how-to-get-character-array-from-a-string/34717402#34717402).

Wenn `separator` ein regulärer Ausdruck ist, der leere Strings trifft, hängt es davon ab, ob das Match durch UTF-16-Codeeinheiten oder Unicode-Codepunkte geteilt wird, ob der Regexp [Unicode-fähig](/de/docs/Web/JavaScript/Reference/Global_Objects/RegExp/unicode#unicode-aware_mode) ist oder nicht.

```js
"😄😄".split(/(?:)/); // [ "\ud83d", "\ude04", "\ud83d", "\ude04" ]
"😄😄".split(/(?:)/u); // [ "😄", "😄" ]
```

Wenn `separator` ein regulärer Ausdruck mit Erfassungsgruppen ist, werden jedes Mal, wenn `separator` übereinstimmt, die erfassten Gruppen (einschließlich aller `undefined`-Ergebnisse) in das Ausgabe-Array eingefügt. Dieses Verhalten wird durch die Methode [`Symbol.split`](/de/docs/Web/JavaScript/Reference/Global_Objects/Symbol/split) des Regexp spezifiziert.

Wenn `separator` ein Objekt mit einer [`Symbol.split`](/de/docs/Web/JavaScript/Reference/Global_Objects/Symbol/split)-Methode ist, wird diese Methode mit dem Zielstring und `limit` als Argumente aufgerufen, und `this` auf das Objekt gesetzt. Ihr Rückgabewert wird der Rückgabewert von `split`.

Jeder andere Wert wird vor der Verwendung als Separator in einen String umgewandelt.

## Beispiele

### Verwendung von split()

Wenn der String leer ist und ein nicht-leeres Trennzeichen angegeben wird, gibt `split()` `[""]` zurück. Wenn sowohl der String als auch das Trennzeichen leere Strings sind, wird ein leeres Array zurückgegeben.

```js
const emptyString = "";

// String ist leer und Trennzeichen ist nicht leer
console.log(emptyString.split("a"));
// [""]

// String und Trennzeichen sind beide leere Strings
console.log(emptyString.split(emptyString));
// []
```

Das folgende Beispiel definiert eine Funktion, die einen String in ein Array von Strings aufteilt,
unter Verwendung des `separator`. Nach dem Teilen des Strings gibt die Funktion
Meldungen aus, die den ursprünglichen String (vor der Teilung), das verwendete Trennzeichen,
die Anzahl der Elemente im Array und die einzelnen Array-Elemente anzeigen.

```js
function splitString(stringToSplit, separator) {
  const arrayOfStrings = stringToSplit.split(separator);

  console.log("The original string is:", stringToSplit);
  console.log("The separator is:", separator);
  console.log(
    "The array has",
    arrayOfStrings.length,
    "elements:",
    arrayOfStrings.join(" / "),
  );
}

const tempestString = "Oh brave new world that has such people in it.";
const monthString = "Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec";

const space = " ";
const comma = ",";

splitString(tempestString, space);
splitString(tempestString);
splitString(monthString, comma);
```

Dieses Beispiel erzeugt die folgende Ausgabe:

```plain
The original string is: "Oh brave new world that has such people in it."
The separator is: " "
The array has 10 elements: Oh / brave / new / world / that / has / such / people / in / it.

The original string is: "Oh brave new world that has such people in it."
The separator is: "undefined"
The array has 1 elements: Oh brave new world that has such people in it.

The original string is: "Jan,Feb,Mar,Apr,May,Jun,Jul,Aug,Sep,Oct,Nov,Dec"
The separator is: ","
The array has 12 elements: Jan / Feb / Mar / Apr / May / Jun / Jul / Aug / Sep / Oct / Nov / Dec
```

### Entfernung von Leerzeichen aus einem String

Im folgenden Beispiel sucht `split()` nach null oder mehr Leerzeichen, gefolgt von einem Semikolon, gefolgt von null oder mehr Leerzeichen — und entfernt, wenn gefunden, die Leerzeichen und
das Semikolon aus dem String. `nameList` ist das Array, das als Ergebnis
von `split()` zurückgegeben wird.

```js
const names = "Harry Trump ;Fred Barney; Helen Rigby ; Bill Abel ;Chris Hand ";

console.log(names);

const re = /\s*(?:;|$)\s*/;
const nameList = names.split(re);

console.log(nameList);
```

Dies protokolliert zwei Zeilen; die erste Zeile protokolliert den Originalstring, und die zweite Zeile protokolliert
das resultierende Array.

```plain
Harry Trump ;Fred Barney; Helen Rigby ; Bill Abel ;Chris Hand
[ "Harry Trump", "Fred Barney", "Helen Rigby", "Bill Abel", "Chris Hand", "" ]
```

### Zurückgeben einer begrenzten Anzahl von Teilen

Im folgenden Beispiel sucht `split()` nach Leerzeichen in einem String und gibt
die ersten 3 Funde zurück.

```js
const myString = "Hello World. How are you doing?";
const splits = myString.split(" ", 3);

console.log(splits); // [ "Hello", "World.", "How" ]
```

### Aufteilung mit einem `RegExp`, um Teile des Trennzeichens im Ergebnis zu inkludieren

Wenn `separator` ein regulärer Ausdruck ist, der Erfassungsklammern `( )` enthält, werden die übereinstimmenden Ergebnisse in das Array aufgenommen.

```js
const myString = "Hello 1 word. Sentence number 2.";
const splits = myString.split(/(\d)/);

console.log(splits);
// [ "Hello ", "1", " word. Sentence number ", "2", "." ]
```

> **Hinweis:** `\d` entspricht der [Zeichenklasse](/de/docs/Web/JavaScript/Guide/Regular_expressions/Character_classes) für Ziffern zwischen 0 und 9.

### Verwendung eines benutzerdefinierten Splitters

Ein Objekt mit einer `Symbol.split`-Methode kann als Splitter mit benutzerdefiniertem Verhalten verwendet werden.

Das folgende Beispiel teilt einen String unter Verwendung eines internen Zustands, der aus einer inkrementierenden Zahl besteht:

```js
const splitByNumber = {
  [Symbol.split](str) {
    let num = 1;
    let pos = 0;
    const result = [];
    while (pos < str.length) {
      const matchPos = str.indexOf(num, pos);
      if (matchPos === -1) {
        result.push(str.substring(pos));
        break;
      }
      result.push(str.substring(pos, matchPos));
      pos = matchPos + String(num).length;
      num++;
    }
    return result;
  },
};

const myString = "a1bc2c5d3e4f";
console.log(myString.split(splitByNumber)); // [ "a", "bc", "c5d", "e", "f" ]
```

Das folgende Beispiel verwendet einen internen Zustand, um bestimmtes Verhalten zu erzwingen und ein "gültiges" Ergebnis sicherzustellen.

```js
const DELIMITER = ";";

// Die Befehle teilen, aber alle ungültigen oder unnötigen Werte entfernen.
const splitCommands = {
  [Symbol.split](str, lim) {
    const results = [];
    const state = {
      on: false,
      brightness: {
        current: 2,
        min: 1,
        max: 3,
      },
    };
    let pos = 0;
    let matchPos = str.indexOf(DELIMITER, pos);

    while (matchPos !== -1) {
      const subString = str.slice(pos, matchPos).trim();

      switch (subString) {
        case "light on":
          // Wenn der `on`-Zustand bereits true ist, nichts tun.
          if (!state.on) {
            state.on = true;
            results.push(subString);
          }
          break;

        case "light off":
          // Wenn der `on`-Zustand bereits false ist, nichts tun.
          if (state.on) {
            state.on = false;
            results.push(subString);
          }
          break;

        case "brightness up":
          // Helligkeitsmaximum erzwingen.
          if (state.brightness.current < state.brightness.max) {
            state.brightness.current += 1;
            results.push(subString);
          }
          break;

        case "brightness down":
          // Helligkeitsminimum erzwingen.
          if (state.brightness.current > state.brightness.min) {
            state.brightness.current -= 1;
            results.push(subString);
          }
          break;
      }

      if (results.length === lim) {
        break;
      }

      pos = matchPos + DELIMITER.length;
      matchPos = str.indexOf(DELIMITER, pos);
    }

    // Wenn wir früh aufgrund der Erreichung des Teilungs-`lim` unterbrochen haben, keine verbleibenden Befehle hinzufügen.
    if (results.length < lim) {
      results.push(str.slice(pos).trim());
    }

    return results;
  },
};

const commands =
  "light on; brightness up; brightness up; brightness up; light on; brightness down; brightness down; light off";
console.log(commands.split(splitCommands, 3)); // ["light on", "brightness up", "brightness down"]
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [Polyfill von `String.prototype.split` in `core-js` mit Fixes und Implementierung moderner Verhaltensweisen wie `Symbol.split` Unterstützung](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
- {{jsxref("String.prototype.charAt()")}}
- {{jsxref("String.prototype.indexOf()")}}
- {{jsxref("String.prototype.lastIndexOf()")}}
- {{jsxref("Array.prototype.join()")}}
- [Reguläre Ausdrücke](/de/docs/Web/JavaScript/Guide/Regular_expressions)-Anleitung
