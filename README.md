<p align="center">
  <img src="icon-512.png" width="96" alt="Catalog logo">
</p>

<h1 align="center">Catalog</h1>
<p align="center">A spaced-repetition app that imports your Anki decks — installable, offline, and built for the phone in your hand.</p>

---

## What it is

Catalog is a flashcard app for spaced-repetition study. It reads decks
exported from Anki (`.apkg` files) and reviews them with a cleaner,
card-catalog-inspired interface designed for one-handed phone use — no
account, no server, no ads. Everything runs and stays on your own device.

- **Bring your own decks** — drop in a `.apkg` exported from Anki and it's
  parsed and imported right in the browser, images included. Decks that
  are organized into subdecks in Anki (e.g. `HSK::HSK 1`, `HSK::HSK 2`)
  come in grouped the same way, collapsible in the library view.
- **Or start from scratch** — add cards by hand, front and back, into any
  deck, at any time, no import required.
- **Study across decks, or leave some out** — tap the checkbox icon in the
  library to select any combination of decks (or a whole group, like all of
  HSK, with one tap) and study them together in a single session, in random
  or sequential order.
- **Remove decks** — the same selection mode lets you delete decks (and all
  their cards) you no longer need.
- **A real spaced-repetition schedule** — new cards move through short
  learning steps, then graduate into a day-scale review cycle (the same
  family of algorithm Anki itself uses), adjusting per card based on how
  you rate it: Again / Hard / Good / Easy.
- **Built for a thumb, not a mouse** — double-tap a card to flip it, no
  button to reach for. The four grading buttons sit in a bar pinned to the
  bottom of the screen so they're always in reach.
- **Works offline, installs like an app** — once loaded, Catalog runs
  without an internet connection and can be added to your phone's home
  screen or your desktop, opening full-screen like a native app.
- **Private by default** — decks, cards, and review history are stored
  locally on your device (IndexedDB). Nothing is uploaded anywhere.

## Get the app

Catalog is a set of static files — there's nothing to build or run on a
server. The easiest way to use it:

1. Open this repo's published link in Chrome, Safari, or Edge.
2. Tap the browser's **Add to Home Screen** / **Install** option.
3. Open it from your home screen from then on — it behaves like any other
   installed app, including working offline.

You can also just use it directly in a browser tab without installing —
everything works the same either way, you just won't get the offline
home-screen icon.

### Publishing your own copy

Because installability requires the app to be served over HTTPS, these
files need to be hosted somewhere rather than opened straight from a
folder. Two free, no-server options:

- **[Netlify Drop](https://app.netlify.com/drop)** — drag this folder onto
  the page and get a live URL in seconds.
- **GitHub Pages** — in this repo, go to **Settings → Pages**, set
  **Branch** to `main` and folder to `/ (root)`, save, and GitHub will
  publish the files at `https://<username>.github.io/<repo-name>`.

## Importing a deck

In Anki: **File → Export → Anki Deck Package**, and make sure **"Support
older Anki versions"** is checked — that's what makes the file readable by
Catalog. Then in the app, drop the `.apkg` onto the import screen.

A couple of things that don't carry over from Anki: audio clips
(`[sound:...]`) are stripped rather than played, and some of Anki's more
elaborate card-template syntax isn't rendered — plain fields, images, and
basic conditional sections all work fine, which covers the vast majority
of decks.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire app — UI and logic |
| `manifest.json` | Makes the app installable |
| `sw.js` | Service worker — caches everything for offline use |
| `icon-192.png`, `icon-512.png` | App icon |

## License

Personal project — use, modify, and host your own copy freely.
