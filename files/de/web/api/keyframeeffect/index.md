---
title: KeyframeEffect
slug: Web/API/KeyframeEffect
l10n:
  sourceCommit: 8c04dd43cc39e6726e3b15416d8498f8514cd071
---

{{ APIRef("Web Animations") }}

Die **`KeyframeEffect`**-Schnittstelle der [Web Animations API](/de/docs/Web/API/Web_Animations_API) ermöglicht es uns, Sätze von animierbaren Eigenschaften und Werten zu erstellen, die als **Keyframes** bezeichnet werden. Diese können dann mit dem [`Animation()`](/de/docs/Web/API/Animation/Animation)-Konstruktor abgespielt werden.

{{InheritanceDiagram}}

## Konstruktor

- [`KeyframeEffect()`](/de/docs/Web/API/KeyframeEffect/KeyframeEffect)
  - : Gibt eine neue `KeyframeEffect`-Objektinstanz zurück und ermöglicht es Ihnen auch, eine bestehende Keyframe-Effekt-Objektinstanz zu klonen.

## Instanzeigenschaften

- [`KeyframeEffect.target`](/de/docs/Web/API/KeyframeEffect/target)
  - : Ruft das Element oder das Ursprungs-Element des Pseudo-Elements ab, das von diesem Objekt animiert wird, und legt es fest. Dies kann `null` sein für Animationen, die kein bestimmtes Element oder Pseudo-Element anvisieren.
- [`KeyframeEffect.pseudoElement`](/de/docs/Web/API/KeyframeEffect/pseudoElement)
  - : Ruft den Selektor des Pseudo-Elements ab, das von diesem Objekt animiert wird, und legt diesen fest. Dies kann `null` sein für Animationen, die kein Pseudo-Element anvisieren.
- [`KeyframeEffect.iterationComposite`](/de/docs/Web/API/KeyframeEffect/iterationComposite)
  - : Ruft die Iterationskompositionsoperation ab und legt diese fest, um die Eigenschaftswertänderungen dieses Keyframe-Effekts aufzulösen.
- [`KeyframeEffect.composite`](/de/docs/Web/API/KeyframeEffect/composite)
  - : Ruft die Kompositionsoperationseigenschaft ab und legt diese fest, um die Eigenschaftswertänderungen zwischen diesem und anderen Keyframe-Effekten aufzulösen.

## Instanzmethoden

_Diese Schnittstelle erbt einige ihrer Methoden von ihrem Elternteil, [`AnimationEffect`](/de/docs/Web/API/AnimationEffect)._

- [`AnimationEffect.getComputedTiming()`](/de/docs/Web/API/AnimationEffect/getComputedTiming)
  - : Gibt die berechneten, aktuellen Zeitwerte für diesen Keyframe-Effekt zurück.
- [`KeyframeEffect.getKeyframes()`](/de/docs/Web/API/KeyframeEffect/getKeyframes)
  - : Gibt die berechneten Keyframes zurück, die diesen Effekt ausmachen, zusammen mit ihren berechneten Keyframe-Offsets.
- [`AnimationEffect.getTiming()`](/de/docs/Web/API/AnimationEffect/getTiming)
  - : Gibt das mit der Animation assoziierte Objekt zurück, das alle Zeitwerte der Animation enthält.
- [`KeyframeEffect.setKeyframes()`](/de/docs/Web/API/KeyframeEffect/setKeyframes)
  - : Ersetzt den Satz von Keyframes, die diesen Effekt ausmachen.
- [`AnimationEffect.updateTiming()`](/de/docs/Web/API/AnimationEffect/updateTiming)
  - : Aktualisiert die angegebenen Zeitgebereigenschaften.

## Beispiele

Im folgenden Beispiel wird der `KeyframeEffect`-Konstruktor verwendet, um eine Reihe von Keyframes zu erstellen, die bestimmen, wie das Rofl-Emoji über den Boden rollen soll:

```js
const emoji = document.querySelector("div"); // element to animate

const rollingKeyframes = new KeyframeEffect(
  emoji,
  [
    { transform: "translateX(0) rotate(0)" }, // keyframe
    { transform: "translateX(200px) rotate(1.3turn)" }, // keyframe
  ],
  {
    // keyframe options
    duration: 2000,
    direction: "alternate",
    easing: "ease-in-out",
    iterations: "Infinity",
  },
);

const rollingAnimation = new Animation(rollingKeyframes, document.timeline);

// play rofl animation
rollingAnimation.play();
```

```html
<div>🤣</div>
```

```css hidden
body {
  box-shadow: 0 5px 5px pink;
}

div {
  width: fit-content;
  margin-left: calc(50% - 132px);
  font-size: 64px;
  user-select: none;
  margin-top: 1rem;
}
```

{{ EmbedLiveSample("Examples", "100%", "120") }}

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [Web Animations API](/de/docs/Web/API/Web_Animations_API)
- [`Animation`](/de/docs/Web/API/Animation)
