# Desert

A port of **desert.vim** — sand and khaki on charcoal, *sky-blue comments*,
pale-green functions. See [desert.vim](https://github.com/fugalh/desert.vim),
or the [[Formatting]] note. An [[unresolved link]] looks like this.

#theme #colours

## Code

```typescript
// Resolve an X11 colour name the way vim resolves it.
import { PALETTE, type Colour } from "./palette";

const CACHE = new Map<string, Colour>();

export function resolve(name: string, fallback = "#ffffff"): Colour {
  if (CACHE.has(name)) return CACHE.get(name)!;
  const hit = PALETTE[name.toLowerCase()];
  if (!hit) {
    console.warn(`unknown colour: ${name}`);   // TODO: throw in strict mode
    return fallback;
  }
  CACHE.set(name, hit);
  return hit;
}
```

Inline code reads like `--code-comment` and `#87ceeb`.

> [!note] Two accents
> Sand carries the interface chrome; sky blue carries links.

> A blockquote sits one step quieter than body text.

## Table

| Role        | Dark      | Light     |
| ----------- | --------- | --------- |
| `Comment`   | `#87ceeb` | `#1c7099` |
| `Constant`  | `#ffa0a0` | `#a63030` |
| `Statement` | `#f0e68c` | `#8a7d0f` |
| `Type`      | `#bdb76b` | `#6f6a1e` |

### Checklist

- [x] Transcribe the dark palette
- [ ] Derive light mode
- [ ] Ship it

#### Heading four
##### Heading five
###### Heading six

---

~~Struck through~~, ==highlighted==, and a footnote[^1].

[^1]: Original scheme by Hans Fugal, distributed with vim.
