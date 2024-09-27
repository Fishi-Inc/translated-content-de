---
title: "WebGL2RenderingContext: getTransformFeedbackVarying() Methode"
short-title: getTransformFeedbackVarying()
slug: Web/API/WebGL2RenderingContext/getTransformFeedbackVarying
l10n:
  sourceCommit: bb48907e64eb4bf60f17efd7d39b46c771d220a0
---

{{APIRef("WebGL")}}

Die **`WebGL2RenderingContext.getTransformFeedbackVarying()`** Methode der [WebGL 2 API](/de/docs/Web/API/WebGL_API) gibt Informationen über variierende Variablen von [`WebGLTransformFeedback`](/de/docs/Web/API/WebGLTransformFeedback) Puffern zurück.

## Syntax

```js-nolint
getTransformFeedbackVarying(program, index)
```

### Parameter

- `program`
  - : Ein [`WebGLProgram`](/de/docs/Web/API/WebGLProgram).
- `index`
  - : Ein [`GLuint`](/de/docs/Web/API/WebGL_API/Types), der den Index der variierenden Variablen angibt, deren Informationen abgerufen werden sollen.

### Rückgabewert

Ein [`WebGLActiveInfo`](/de/docs/Web/API/WebGLActiveInfo) Objekt.

## Beispiele

```js
activeInfo = gl.getTransformFeedbackVarying(program, 0);
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [`WebGLTransformFeedback`](/de/docs/Web/API/WebGLTransformFeedback)
