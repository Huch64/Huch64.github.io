# huch's index — project document

A personal portfolio site for **Wang Haocheng (Haocheng Wang)** — architect turned AI/ML.
Static site, hosted on GitHub Pages (`Huch64.github.io`). This file is the design archive:
positioning, principles, conventions. (Working notes also live in Claude memory.)

---

## 1. Positioning

- **Audience:** product / AI / research / CS roles (recruiters, technical reviewers, collaborators).
- **One-line:** *Architect turned AI/ML — systems at the edge of space, data & intelligence.*
- **The hook:** the architecture → AI arc is the differentiator. Architecture appears as a *bridge*
  that reinforces the AI/data/research story — not as a full architecture portfolio.
- It is a **portfolio**, not a blog. No long-form articles; depth lives one click away (report/code).

## 2. Project lineup (10) & categories

Legend categories: **AI / ML** · **Data & Space** · **Built**

| # | Project | asset key | category | source / `_src` |
|---|---|---|---|---|
| 01 | PRISM (sentence-level citation agents) | `prism` | AI | CA6123_PRISM |
| 02 | My Little Bedroom (RL furniture layout) | `bedroom` | AI | CA6126_myLittleBedroom |
| 03 | Fairness Audit ("Marriage Trap") | `fairness` | AI | CA6003_dataGovernance |
| 04 | Energy Fingerprints (household clustering) | `energy` | Data & Space | CA6002_unfoldingLondon |
| 05 | Depression Screening (knowledge distillation) | `depression` | AI | CA6001_theUnasked |
| 06 | Traffic Forecast (SimpleRNN) | `traffic` | AI | CA6000_rushHour |
| 07 | 河滩研究 · Riverbank (GIS data mining) | `riverbank` | Data & Space | Focusing_the_Familiar.pdf |
| 08 | 住宅类型学 · Residential (quant. viz) | `residential` | Data & Space | Focusing_the_Familiar.pdf |
| 09 | 南京仙林学校 · Xianlin (built school) | `xianlin` | Built | Portfolio.pdf |
| 10 | 上海滑雪塔 · Skitower (form-finding) | `skitower` | Built | Portfolio.pdf |

**Deliberately excluded:** Aranya (interior/furniture) — reads as interior design, dilutes the AI/research message.

## 3. Layout — the "organic concept board"

Rejected along the way: dense image-wall homepage, bento grid, invisible-coordinate scatter,
uniform overview-grid, separate per-project detail pages, full data tables on the board.

**Chosen:** one **organic concept board** — all images out at once, scattered & overlapping,
sizes varied by information content, same-project items clustered by **proximity** (not boxes).
Cards (profile, project, images) sit staggered across the whole board; use all the space.

- Click any image / project card → opens that **project's gallery** (lightbox): project header
  (logo, title, intro, role, tech stack, links) + all its images, each with a one-line caption.
- Animations (extracted as mp4) are interleaved among the static page-images in the gallery.
- Mobile: scales down / reflows (to refine).

## 4. Card vocabulary (only three)

- **Text card** (incl. profile card & project card) — title, one-line intro, **role**, bold tech stack, links.
- **Image card** — full-saturation image, rotated, overlapping.
- **Video/gif card** — muted, plays on hover.

No "stat chip", no table cards on the board. A project's **headline number is stated once**, in
the project card's one-line copy (never repeated across figure + chip + text). Full numbers/tables
live in the linked report/code.

## 5. Visual design

- **Background:** pure white `#fff` + a faint grid (`#F4F4F2`, 30px).
- **Wordmark:** `huch's index` in **Fraunces** (serif, `'s` italic), black, no colour.
- **Colour comes only from:** the colourful **pixel logos** + the **images themselves** (full saturation, vivid — never desaturated).
- **No per-project theme colour.** Category is shown via a top **legend** with three bright dots:
  AI `#2D7FF9` · Data & Space `#10B981` · Built `#F5A623` (each card carries a small category dot).
- **Type:** Fraunces (display) · DM Sans (body) · DM Mono (metadata, tags, captions).
- **Pixel logos:** 16×16, literal/skeuomorphic, project-specific (prism = splitting spectrum, bed = bed + plant, scale, bolt, heart, car, map, grid, building, ski-peak; plus contact icons: github / mail / camera).

## 6. Content principles

- **Show, don't narrate.** Rigor is shown via curated figures + a tight caption, not paragraphs.
- **De-emphasize slides.** Prefer neutral matplotlib/notebook figures, photos, renders, video.
  Avoid branded "screenshot-of-a-PowerPoint" look; where a slide is essential, recreate neutrally
  or crop/grayscale to strip presentation chrome.
- **Role / contribution:** state factual contributions, not titles. e.g. `Did · agent pipeline, guardrails, UI & eval · team of 4`. Add team size for group work. Never overclaim (e.g. Energy: visual/data-viz lead — modeling was a teammate).
- **Photography:** no on-site gallery; a quiet contact link to Xiaohongshu (camera icon, "小红书").

## 7. Naming conventions

- **No Chinese in file/folder names.** (Display titles may keep Chinese, e.g. "河滩研究 · Riverbank".)
- **assets / _assets_src keys:** short, descriptive English (`prism`, `traffic`, …).
- **_src / docs:** course-code form matching the original folders (`CA6000_rushHour`, …).
- **docs/ PDFs:** one per project, named like the `_src` folder (`CA6123_PRISM.pdf`).
- All asset filenames ascii, no spaces.

## 8. File structure

```
Huch64.github.io/
│ ── committed & served by GitHub Pages ──
├── index.html          (currently concept.html; rename on launch)
├── assets/<key>/        web-optimized webp / mp4 (built)
├── docs/                final, scrubbed PDFs (linked by the site)
├── build-assets.sh
│ ── local only (gitignored) ──
├── _assets_src/<key>/   full-res originals  → build → assets/
├── _src/                original pptx / ipynb / reports / big PDFs / _ref
└── _proto/              experimental html prototypes
```

## 9. Asset pipeline

- Drop originals into `_assets_src/<key>/`, run `./build-assets.sh`.
- Images → WebP (max 1500px, q82, no upscale); gif/mov/mp4 → muted H.264 mp4 (max 960px).
- Prune via a per-project `archive/` subfolder (build skips nested dirs).
- Tools: cwebp, ffmpeg, sips, pdftocairo/pdfimages (poppler). **PPTX → slides: use Keynote** (PowerPoint AppleScript export is broken) → export PDF → render.

## 10. Documents & hosting

- Projects **with a public repo** (prism, bedroom, depression): link `↳ Code`; a good deck/report
  also earns a `↳ Slides` link (different reader). Keep README presentable. One doc per project, not both report+ppt.
- Projects **without a repo** (traffic report, fairness, energy, architecture): host the doc, or link external (ArchDaily, Portfolio).
- **PDF only** (not .pptx). Group assignments: strip the cover slide + footer member info before hosting.
- Big files (Portfolio 82MB) → GitHub Release / external, never in the repo.
- Public repos that already contain group-member info should be scrubbed too.

## 11. Open / to-do

- Layout arrangement algorithm (organic scatter, every image visible, fill space).
- Finalize per-project image picks, captions, and verified headline numbers.
- Rework fairness & energy decks (in progress); then host scrubbed PDFs in `docs/`.
- Confirm role wording per project + team sizes; bedroom/depression solo-vs-group.
- Connect to GitHub & deploy (no SSH key / gh yet; git identity = Wang Haocheng / wanghaocheng9304@gmail.com).
- Rename concept.html → index.html on launch.
```
