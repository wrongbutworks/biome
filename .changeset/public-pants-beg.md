---
"@biomejs/biome": patch
---

Fixed [#10727](https://github.com/biomejs/biome/issues/10727): Biome now breaks the arguments of curried `test.each`, `it.each`, `describe.each`, and `test.for` calls when they exceed the configured line width.

```diff
- test.each([[1, 2]])("long description", (a, b) => {
-   expect(a).toBe(b);
- });
+ test.each([[1, 2]])(
+   "long description",
+   (a, b) => {
+     expect(a).toBe(b);
+   },
+ );
```
