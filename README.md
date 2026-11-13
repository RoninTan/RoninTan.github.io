# Song Tan · 谭松

Personal homepage: https://ronintan.github.io/

One self-contained `index.html` (styles, scripts and the two display fonts are inline). Nothing is fetched from outside, so it loads quickly in mainland China. GitHub Pages publishes the `main` branch from the repository root.

## Editing

- **Text.** Every piece of copy exists twice, as `<span class="zh">…</span>` and `<span class="en">…</span>` (or two paragraphs with those classes). Edit both. The page shows one language at a time; visitors switch with 中文 / English at the top left, and `?lang=en` or `?lang=zh` in the URL forces one.
- **Photo.** Put a portrait named `photo.jpg` in the repository root (roughly square works best, e.g. 800 × 700). It replaces the placeholder figure on the badge automatically.
- **Papers, education, links.** Plain HTML lists in the `#papers`, `#path` and `#contact` sections. The links also appear on the back of the badge and in the first screen.

## The first screen

- **The badge** hangs from a lanyard simulated in script (a chain of points with Verlet integration, the card as a heavy point at the end). Drag it, throw it, click it to flip it over.
- **SONG TAN** is set in a variable font: each letter's width and weight follow the pointer, and a slow wave runs through the name when no pointer is around.
- `?still` (or the system "reduce motion" setting) shows everything at rest.

## Fonts

Both display fonts are subsets under the SIL Open Font License 1.1, inlined as base64 in the `<style id="fonts">` block:

- **Tan Latin**: ASCII subset of [Anybody](https://github.com/Etcetera-Type-Co/Anybody) (© The Anybody Project Authors), variable in width (50–150) and weight (100–900).
- **Tan Hei**: about 50 characters of Noto Sans CJK SC Black (© Google and Adobe), covering the name, the badge and the section headings. A heading character outside the subset falls back to the system's bold Hei; to add characters, regenerate the subset:

```
pyftsubset NotoSansCJK-Black.ttc --font-number=2 --flavor=woff2 \
  --text-file=chars.txt --output-file=tan-hei.woff2
base64 -w0 tan-hei.woff2
```
