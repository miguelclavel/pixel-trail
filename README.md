# Pixel Trail

A pixel trail behind the hero, from [miguelclavel.com](https://miguelclavel.com/?utm_source=github&utm_medium=pixel-trail).

<img src="assets/demo.gif" width="720" alt="A pixel trail behind the hero: a screen recording">

**[Try it live](https://miguelclavel.github.io/pixel-trail/)** · one file, `index.html`, no libraries, no build step.

Move your mouse across the top of my site and you leave a trail of coloured pixels behind you.

It took three tries to stop it looking cheap.

The space around my name was dead space. I wanted it to answer you without competing with the words sitting on top of it.

So it's a grid, not a cursor. The page is split into 102 columns of small squares. Your pointer charges up whichever squares it passes near, and each one remembers the brightest it's ever been. That single rule is what makes the trail hold its shape instead of flickering out behind you.

The brightest squares paint in the page's own colour, white on dark and near black on light. The dimmer ones scatter into colour around the edges.

Here's what I got wrong twice. Squares kept lighting up underneath my name. I blocked the charge where the text sits and they still lit up, because the radius reaches in from outside it. The fix was to stop drawing there at all, not to stop charging.

Fair warning, you'll lose ten minutes drawing circles with your own mouse.

## Use it on your site

It needs three things on your page: a hero section (`#hero`), a canvas inside it (`#grid`), and the text block it should stay off (`#copy`). Copy the `<style>` and `<script>` from `index.html`, keep those three ids, and tune `COLS` and `RADIUS` at the top of the script. It works with a finger on touch screens too, and stays off for reduced motion.

## Or build your own from the prompt

Copy it as it is and paste it into Claude, or any AI coding tool.

```text
Add a full width canvas behind my hero, split into a grid about 100 columns wide. As the pointer moves, raise an energy value on every cell within 60 pixels of it, and let each cell keep the highest energy it has reached rather than following the pointer back down. Fade energy slowly, twice as fast once the pointer has been still for half a second. Draw the highest energy cells as solid squares in the page text colour and lower ones in random accent colours, skipping the faintest. Never draw over the rectangle where my hero text sits.
```

More like this in [interaction-recipes](https://github.com/miguelclavel/interaction-recipes).

---

MIT licensed. Made by [Miguel Clavel](https://miguelclavel.com/?utm_source=github&utm_medium=pixel-trail) with Claude Code. If you build one of these, send it to me. I'd genuinely like to see it.
