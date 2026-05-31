# Pokémon Coloring Book 🎨

My first app! Click any Pokémon and paint it. It's part of
[Claire's website](https://github.com/clairehjx/claire-website) and uses the same
dreamy watercolour-blue style.

🔗 **Live app:** _(add your Vercel link here after you deploy)_

## What you can do

- 🖌️ **Click to paint** — pick a colour, then click any region of the Pokémon.
- 🌊 **Watercolour mode** — turn it on for a soft, see-through paint effect.
- ↩️ **Undo** — made a mistake? Step back up to 20 times.
- 🔄 **Reset** — start the picture over.
- 💾 **Save PNG** — download your finished artwork.
- 🐾 Choose from **9 Eeveelutions**.

## The clever part: the flood-fill algorithm 🧠

When you click, how does the app know *exactly* which area to colour? It uses a
**flood-fill algorithm** — the same idea as the paint-bucket tool in art programs.

Here's the recipe, broken into steps:

1. Look at the colour of the pixel I clicked.
2. Add it to a "to-do list" (called a **queue**).
3. Take a pixel off the list, colour it, then check its 4 neighbours
   (up, down, left, right).
4. If a neighbour is a *similar* colour — and not a dark outline — add it to the list too.
5. Keep going until the list is empty.

This is called a **breadth-first search (BFS)**. The dark outlines act like walls
that stop the paint from leaking out. I also keep a `visited` list so I never
check the same pixel twice — that makes it fast!

The watercolour effect is a fun twist: instead of a solid colour, each pixel is
*blended* with white by a slightly random amount, and pixels near the edges are
painted a little darker — just like real watercolour pooling at the edges. 🌊

## How to run it

**Double-click `index.html`** — it opens straight in your browser. No setup needed.

## Built by Claire (with Chloe) — Primary 5
