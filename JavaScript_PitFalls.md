## Pitfalls

---

### Costly Freedom

1. Because Js provides no restrictions to how one structures the code, this freedom could be damaging as more files start to increase.

```js
function paintPainting(painter, painting) {
	return painter.prepare().paint(painting, painter.ownMaterials).finish();
}
```

2. Reading the above code without context could give only vague ideas. Moreover, it could be understood only if the surrounding code is provided. Even with that, there are high chances for misconception which leads to wrong usage and errors. For eg: From the above code one might interpret `Painting` as a string but later point in time the type could be changed from string to another data structure in such a case it will be left unnoticed by the developer.

3. To sum up, javascript's freedom can be a pain in the ass when we want safety in running the code.

### Loose Documentation

1. Nothing exists in the Js language specification to formalize describing what function parameters, function returns, variables or other constructs in code are meant to be.
2. However, developers tend to mitigate this issue by adopting a standard called JsDoc. like in the below example

```js
/**
 * Performs a painter painting a particular painting.
 *
 * @param {Painting} painter
 * @param {string} painting
 * @returns {boolean} Whether the painter painted the painting.
 */
function paintPainting(painter, painting) {
	/* ... */
}
```

3. There are certain key issues with JSDoc
   1. Nothing stops JSDoc descriptions from being wrong about the code.
   2. Even if they were valid previously, due to code refactors and other code changes. It will be difficult to find all the invalid JSDoc comments and update them.
   3. Describing complex objects is unwieldy and verbose.

### Weaker Developer Tooling

1. Since Js is a dynamically typed language, it is difficult to automate large changes or gain insights about a code base.
