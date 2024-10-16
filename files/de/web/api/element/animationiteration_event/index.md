---
title: "Element: animationiteration event"
short-title: animationiteration
slug: Web/API/Element/animationiteration_event
l10n:
  sourceCommit: f216422c99b6c7014e398803b70600501bce8a48
---

{{APIRef}}

Das **`animationiteration`**-Ereignis wird ausgelöst, wenn eine Iteration einer [CSS-Animation](/de/docs/Web/CSS/CSS_animations) endet und eine neue beginnt. Dieses Ereignis tritt nicht gleichzeitig mit dem [`animationend`](/de/docs/Web/API/Element/animationend_event)-Ereignis auf und daher nicht bei Animationen mit einem `animation-iteration-count` von eins.

## Syntax

Verwenden Sie den Ereignisnamen in Methoden wie [`addEventListener()`](/de/docs/Web/API/EventTarget/addEventListener), oder setzen Sie eine Ereignishandlereigenschaft.

```js
addEventListener("animationiteration", (event) => {});

onanimationiteration = (event) => {};
```

## Ereignistyp

Ein [`AnimationEvent`](/de/docs/Web/API/AnimationEvent). Erbt von [`Event`](/de/docs/Web/API/Event).

{{InheritanceDiagram("AnimationEvent")}}

## Ereigniseigenschaften

_Erbt auch Eigenschaften von seinem übergeordneten [`Event`](/de/docs/Web/API/Event)_.

- [`AnimationEvent.animationName`](/de/docs/Web/API/AnimationEvent/animationName) {{ReadOnlyInline}}
  - : Ein String, der den Wert des {{cssxref("animation-name")}} enthält, der die Animation erzeugt hat.
- [`AnimationEvent.elapsedTime`](/de/docs/Web/API/AnimationEvent/elapsedTime) {{ReadOnlyInline}}
  - : Ein `float`, der die Zeit in Sekunden angibt, die die Animation lief, als dieses Ereignis ausgelöst wurde, ohne die Zeiten zu berücksichtigen, in denen die Animation angehalten war. Für ein `animationstart`-Ereignis ist `elapsedTime` `0.0`, es sei denn, es gab einen negativen Wert für {{cssxref("animation-delay")}}, in welchem Fall das Ereignis mit `elapsedTime`, das `(-1 * delay)` enthält, ausgelöst wird.
- [`AnimationEvent.pseudoElement`](/de/docs/Web/API/AnimationEvent/pseudoElement) {{ReadOnlyInline}}
  - : Ein String, beginnend mit `'::'`, der den Namen des [Pseudo-Elements](/de/docs/Web/CSS/Pseudo-elements) enthält, auf dem die Animation ausgeführt wird. Wenn die Animation nicht auf einem Pseudo-Element, sondern auf dem Element ausgeführt wird, ein leerer String: `''`.

## Beispiele

Dieser Code verwendet `animationiteration`, um die Anzahl der abgeschlossenen Iterationen einer Animation zu verfolgen:

```js
const animated = document.querySelector(".animated");

let iterationCount = 0;

animated.addEventListener("animationiteration", () => {
  iterationCount++;
  console.log(`Animation iteration count: ${iterationCount}`);
});
```

Dasselbe, aber mit der `onanimationiteration`-Ereignishandlereigenschaft:

```js
const animated = document.querySelector(".animated");

let iterationCount = 0;

animated.onanimationiteration = () => {
  iterationCount++;
  console.log(`Animation iteration count: ${iterationCount}`);
};
```

### Live-Beispiel

#### HTML

```html
<div class="animation-example">
  <div class="container">
    <p class="animation">You chose a cold night to visit our planet.</p>
  </div>
  <button class="activate" type="button">Activate animation</button>
  <div class="event-log"></div>
</div>
```

#### CSS

```css
.container {
  height: 3rem;
}

.event-log {
  width: 25rem;
  height: 2rem;
  border: 1px solid black;
  margin: 0.2rem;
  padding: 0.2rem;
}

.animation.active {
  animation-duration: 2s;
  animation-name: slide-in;
  animation-iteration-count: 2;
}

@keyframes slide-in {
  from {
    transform: translateX(100%) scaleX(3);
  }
  to {
    transform: translateX(0) scaleX(1);
  }
}
```

#### JavaScript

```js
const animation = document.querySelector("p.animation");
const animationEventLog = document.querySelector(
  ".animation-example>.event-log",
);
const applyAnimation = document.querySelector(
  ".animation-example>button.activate",
);
let iterationCount = 0;

animation.addEventListener("animationstart", () => {
  animationEventLog.textContent = `${animationEventLog.textContent}'animation started' `;
});

animation.addEventListener("animationiteration", () => {
  iterationCount++;
  animationEventLog.textContent = `${animationEventLog.textContent}'animation iterations: ${iterationCount}' `;
});

animation.addEventListener("animationend", () => {
  animationEventLog.textContent = `${animationEventLog.textContent}'animation ended'`;
  animation.classList.remove("active");
  applyAnimation.textContent = "Activate animation";
});

animation.addEventListener("animationcancel", () => {
  animationEventLog.textContent = `${animationEventLog.textContent}'animation canceled'`;
});

applyAnimation.addEventListener("click", () => {
  animation.classList.toggle("active");
  animationEventLog.textContent = "";
  iterationCount = 0;
  const active = animation.classList.contains("active");
  applyAnimation.textContent = active
    ? "Cancel animation"
    : "Activate animation";
});
```

#### Ergebnis

{{ EmbedLiveSample('Live_example', '100%', '150px') }}

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [CSS-Animationen](/de/docs/Web/CSS/CSS_animations)
- [Verwendung von CSS-Animationen](/de/docs/Web/CSS/CSS_animations/Using_CSS_animations)
- [`AnimationEvent`](/de/docs/Web/API/AnimationEvent)
- Verwandte Ereignisse: [`animationstart`](/de/docs/Web/API/Element/animationstart_event), [`animationend`](/de/docs/Web/API/Element/animationend_event), [`animationcancel`](/de/docs/Web/API/Element/animationcancel_event)
