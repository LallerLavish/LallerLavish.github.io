# Portfolio — Lavish Laller

Single-file static site. No build step, no dependencies. Open `index.html` in a browser to preview.

```
Portfolio/
├── index.html          ← everything (HTML + CSS + JS + cover art)
├── README.md
└── assets/
    └── Lavish_Laller_Resume.pdf   ✓ already in place
```

Project covers are generated in the page as SVG — there are no image files to manage.

## 1. Media — nothing required

Project covers are **drawn by the page itself** — a designed cover per project carrying its
name, category and a motif (a breached wall for mcp-wall, cited pages for PaperMind, an agent
graph for AlgoForge). No screenshots to take, nothing to export, and they stay crisp at any size.
Demo videos live on GitHub, which the **View Source** button links to.

Your hero portrait is a real photo: `assets/profile.*` — **any of** `.jpg`, `.jpeg`, `.png`
or `.webp` works, the page tries each in turn. If none is present you get a designed `LL`
monogram card instead of a broken image. The frame is square, so a square headshot is used
uncropped; a taller photo is centre-cropped to a square.

### If you ever want a real image instead

| What | How |
|---|---|
| Swap the hero photo | replace `assets/profile.jpeg` (square works best, 800×800+) |
| A project cover | set `cover: 'assets/whatever.png'` on that project — it overrides the drawn art |
| A demo video | set `video: 'assets/whatever.mp4'` — it overrides both |
| Social preview | drop `assets/og-cover.png` (1200×630) |

### Restyling a drawn cover

Edit the `ART` map in the `<script>` block — two gradient stops and an accent per project:

```js
const ART = {
  'mcp-wall':  { c1:'#F9F5EA', c2:'#F0D5C0', accent:'#E1603A', motif:'shield' },
  'papermind': { c1:'#F6F7F1', c2:'#D7E1F2', accent:'#3D6FC4', motif:'pages'  },
  'algoforge': { c1:'#FAF7E6', c2:'#F4E198', accent:'#C9A21B', motif:'nodes'  }
};
```

`motif` can be `shield`, `pages` or `nodes` — swap them between projects freely.

## 2. Edit your content

- **Page text** — edit the HTML directly. Sections are commented and numbered.
- **Project write-ups** — edit the `PROJECTS` array in the `<script>` block at the bottom. Cards and expanded views both rebuild from it, so you only edit in one place.
- **Live demo buttons** — set `demo: 'https://...'` on a project. Leave it as `''` and the button stays hidden.
- **Colors** — every color is a CSS variable in the `:root` block at the very top.

## 3. Deploy

### GitHub Pages
```bash
git init
git add .
git commit -m "Portfolio"
git branch -M main
git remote add origin https://github.com/LallerLavish/LallerLavish.github.io.git
git push -u origin main
```
Repo → **Settings → Pages → Source: main / root**. Live at `https://lallerlavish.github.io` in a minute or two.

### Netlify / Vercel / Cloudflare Pages
Drag the whole folder onto their dashboard. No build command, no output directory.

## Notes

- Fonts load from Google Fonts (Fraunces, Inter, JetBrains Mono) with system fallbacks if offline.
- Works down to ~360px wide; tested for horizontal overflow.
- Keyboard accessible: project cards are buttons, `Esc` closes the expanded view.
- The scrollbar is custom-drawn so it floats over the page with no track strip; native scrolling is untouched.
