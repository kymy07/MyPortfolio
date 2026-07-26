# MyPortfolio — Adlishah Hakimi

Personal portfolio website. Live at **https://kymy07.github.io/MyPortfolio/**

Static site — plain HTML, CSS and JavaScript. No build step, no framework, no
dependencies to install. Open `index.html` and it runs.

## Pages

| File | What's on it |
|---|---|
| `index.html` | Home — hero, about, skills, education, work, experience, contact |
| `events.html` | Events & activities — exhibitions, competitions, activities |
| `gallery.html` | Full gallery — apps, websites, animation, games, AR, video |

## Things worth knowing before editing

**The cartoon avatar** is an inline `<svg>` inside `index.html` (search for
`id="avatar"`). It has to be inline rather than an external file because the
eyes track the cursor, which needs script access to the pupils.

- Eyes follow the cursor — `.pupil` groups, moved on `mousemove`.
- The hand waves — `#waveArm` and `#waveHand` are rotated on a sine curve, so
  the swing is fastest through the middle and eases at the turnarounds.
- Both stop when the visitor has "reduce motion" enabled.

**Adding a gallery item** — copy an existing `.masonry-item` block in
`gallery.html`. `data-cat` sets the filter category, `data-video` points at an
`.mp4`, `data-pages` is a `|`-separated list of images for the slideshow.

**Adding an event** — there's a commented-out template at the bottom of the
grid in `events.html`. Copy it and fill in the photo, title, location and text.

**Contact form** runs on EmailJS; the keys are in the script block at the
bottom of `index.html`.

## Deploying

GitHub Pages serves the `main` branch from the repository root. Push to `main`
and the live site updates on its own.

## Local preview

Any static server works, e.g.

```
python -m http.server 8000
```

then open http://127.0.0.1:8000/. Serving over HTTP rather than opening the
file directly matters — the contact form and some gallery behaviour don't work
the same way from a `file://` URL.
