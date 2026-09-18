# Aha!

*Adding the aha to ref - aha - ing*

A library of design references and resources you navigate as a coordinate space
rather than a list.

Four quadrants: **references** up, **resources** down, **creative** left,
**technical** right. Every book is scored on both axes. You drag the yellow **Aha!**
handle and the whole crosshair moves with it — its position *is* the query. A shelf
of spines stands on the horizontal axis and restocks live as you drag, best match in
the middle, so the skyline peaks over wherever you're pointing. The `‹ ›` arrows page
deeper at the same coordinate and riffle the shelf. Click a spine and the book leaves
the shelf, stands up, and opens flat.

Live at **https://redtanjiro.github.io/aha/**

---

## Running it

It's one file with no build step and no dependencies. Open `index.html`, or:

```
python3 -m http.server 8000
```

The only external request is Google Fonts (Inter and Inter Tight). Everything else —
markup, styles, the sixty-four references, every diagram and animation — is inline.

## Editing the library

The references live in the `RAW` array near the top of the script:

```js
["Fonts In Use","https://fontsinuse.com","index",
 "Typography indexed by typeface, industry and era.", -0.30, 0.82],
//  title          url                    kind        note                x      y
```

- `x` runs from `-1` (creative) to `+1` (technical)
- `y` runs from `-1` (resources) to `+1` (references)
- `kind` decides the book's paper stock through `TYPE_OF` → `STOCK`

Adding an entry needs nothing else — ranking, call number, colour and the shelf all
fall out of those six values.

You can also add books from inside the page with **+ shelve a book**, which places
them with two axis sliders. On a static host those are saved in your browser only
(`localStorage`), so they don't follow you between machines and they aren't shared
with anyone else opening the site. Anything you want to keep belongs in `RAW`.

## Structure

`index.html` is the whole thing — head, styles, markup, the library and the script.
Edit it directly. `og.png` is the share card, `.nojekyll` tells GitHub Pages not to
run Jekyll over the folder.

## Design

Warm linen canvas, black hairline structure, flat surfaces. Sun Yellow `#ffde3b` is
the only filled action colour in the system — it's the Aha handle and the visit
button, and nothing else. Accent colours are paper stock assigned by book type and
weighted by how common that type is, so the quiet neutrals carry the bulk and a
saturated spine means the book is unusual. Inter and Inter Tight at 400 only;
hierarchy comes from scale and tight negative tracking, never from weight.

Built by [Neel Parikh](https://neel-parikh.com).
