# lallerlavish.github.io

Personal portfolio — **[lallerlavish.github.io](https://lallerlavish.github.io)**

Backend & Systems Engineer. Rust, Java, Spring Boot. Previously Samsung R&D Institute (SRI-D),
where I built an on-device AI daemon for edge system recovery.

## Built with

Plain HTML, CSS and JavaScript in a single file — no framework, no build step, no dependencies.
Project cover art is generated in-page as SVG, so the site ships with one photo and a PDF and
nothing else. Deployed on GitHub Pages.

Dark theme — black through deep indigo, purple into blue. The hero runs a canvas code
animation behind the whole section; it pauses when off-screen or when the tab is hidden, and
falls back to a single static frame under `prefers-reduced-motion`.

- Responsive down to 360px, no horizontal overflow
- Keyboard accessible — project cards are buttons, `Esc` closes the expanded view
- Custom floating scrollbar; native scrolling untouched
- Circular portrait with a conic gradient ring
- Fonts: Fraunces, Inter, JetBrains Mono, with system fallbacks

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
- **Colors** — CSS variables in the `:root` block at the top.

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
