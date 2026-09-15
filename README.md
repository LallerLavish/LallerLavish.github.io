# lallerlavish.github.io

Personal portfolio — **[lallerlavish.github.io](https://lallerlavish.github.io)**

Backend & Systems Engineer. Rust, Java, Spring Boot. Previously Samsung R&D Institute (SRI-D),
where I built an on-device AI daemon for edge system recovery.

## Built with

Plain HTML, CSS and JavaScript in a single file — no framework, no build step, no dependencies.
Project cover art is generated in-page as SVG, so the site ships with one photo and a PDF and
nothing else. Deployed on GitHub Pages.

**Dark and light themes.** Dark is near-black warmed with red; light is warm ivory through
dusty rose. Both share the burgundy→rose accent. The toggle sits in the nav (and in the
mobile menu). A first visit follows the OS setting; after that the visitor's choice is remembered in
`localStorage`, and an inline `<head>` script applies it before paint so there's no flash.

The hero runs a canvas code animation behind the whole section, repainting in the active
theme's palette. It pauses when off-screen or when the tab is hidden, and falls back to a
single static frame under `prefers-reduced-motion`.

- Responsive down to 360px, no horizontal overflow
- Keyboard accessible — project cards are buttons, `Esc` closes the expanded view
- Custom floating scrollbar; native scrolling untouched
- Circular portrait with a conic gradient ring
- Fonts: Fraunces (display), Plus Jakarta Sans (body), JetBrains Mono (labels), with system fallbacks

## Projects featured

| Project | What it is |
|---|---|
| [mcp-wall](https://github.com/LallerLavish/mcp-wall) | Kernel-enforced sandbox runtime for untrusted MCP servers — Rust, Landlock, seccomp |
| [PaperMind](https://github.com/LallerLavish/papermind) | Multi-tenant RAG document Q&A backend — Java 21, Spring AI, pgvector |
| [AlgoForge](https://github.com/LallerLavish/AlgoForge-Open) | Multi-agent problem-solving system — Python, FastAPI, AutoGen |

## Contact

[Email](mailto:lallerlavish2023@gmail.com) · [LinkedIn](https://www.linkedin.com/in/lavish-laller-650453362/) · [LeetCode](https://leetcode.com/u/LavishLaller/)

---

<details>
<summary><b>Maintenance notes</b></summary>

### Structure

```
index.html    everything — markup, styles, scripts, generated cover art
assets/       profile photo + résumé PDF
```

### Editing

- **Page text** — edit the HTML. Sections are commented and numbered.
- **Projects** — edit the `PROJECTS` array in the `<script>` block. Cards and expanded views
  both build from it, so each project is defined once.
- **Live demo buttons** — set `demo: 'https://...'` on a project; `''` hides the button.
- **Cover art** — the `ART` map holds two gradient stops, an accent and a motif
  (`shield`, `pages`, `nodes`) per project.
- **Colors** — CSS variables in the `:root` block at the top; the `:root[data-theme="light"]`
  block right below it overrides the same names for light mode. Translucent accents all read
  from `--accent-rgb` / `--glow-rgb` / `--rose-rgb`, so changing the brand hue is a one-line edit.
  The hue variables are `--wine`, `--wine-deep`, `--rose`, `--rose-deep`, plus `--coral`,
  `--cyan`, `--amber` and `--pink` for the category dots.
- **Cover palettes** — `ART_SETS.dark` and `ART_SETS.light` in the `<script>` block.
- **Animation** — `DENSITY` (how busy) and `SPEED_MS` (how fast) in the hero animation block.

### Media

The hero photo is `assets/profile.*` — `.jpeg`, `.jpg`, `.png` and `.webp` all work, tried in
order, falling back to a drawn monogram if none is found. The frame is square, so a square
headshot shows uncropped.

To use a real image for a project instead of the generated art, set `cover: 'assets/x.png'`
on that project; `video: 'assets/x.mp4'` overrides both.

### Deploying

Push to `main` — GitHub Pages rebuilds in about a minute.

```bash
git add -A && git commit -m "update" && git push
```

</details>
