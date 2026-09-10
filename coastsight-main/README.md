# CoastSight website

A static 3-page site for the CoastSight project, ready to host on GitHub Pages.

```
coastsight/
├── index.html              # Home — links to the pages below
├── project/
│   └── index.html          # Project overview (from the presentation)
├── people/
│   └── index.html          # Faculty leads + student team composition + full 16-person roster
├── dashboard/
│   └── index.html          # VIP action-plan dashboard (tracker + timeline + budget)
├── assets/
│   ├── style.css           # Shared design tokens, nav, and footer used by all pages
│   ├── logo.png            # CoastSight logo (large, used on the homepage)
│   ├── logo-small.png       # CoastSight logo (small, used in the nav bar / favicon)
│   ├── pipeline-diagram.jpg # Pipeline figure from the presentation
│   └── team/                # One placeholder photo per team member (16 files)
└── README.md
```

## Adding real team photos

Every one of the 16 team members already has an image slot on the People page, currently
filled with a generic placeholder graphic. To add a real photo, just **replace the file** in
`assets/team/` — keep the same filename and the page updates automatically, no HTML edits needed.

| File | Person |
|---|---|
| `assets/team/imteaj.jpg` | Dr. Ahmed Imteaj |
| `assets/team/hallstrom.jpg` | Dr. Jason Hallstrom |
| `assets/team/wakefield.jpg` | Dr. Stephanie Wakefield |
| `assets/team/student-fs-1.jpg` … `student-fs-7.jpg` | Freshman/sophomore researchers (7) |
| `assets/team/student-jr-1.jpg`, `student-jr-2.jpg` | Junior researchers (2) |
| `assets/team/student-sr-1.jpg` | Senior researcher (1) |
| `assets/team/student-grad-1.jpg` … `student-grad-3.jpg` | Graduate researchers (3) |

Square photos around 500×500px work best (the page crops to a square automatically).
If you'd rather label the student photos with real names, edit the `<div class="cap">` caption
text next to each `<img>` in `people/index.html`.

## Publish with GitHub Pages

1. Create a new repository named **`coastsight`** (or any name you like) on GitHub.
2. Push everything in this folder to the repo root:
   ```bash
   cd coastsight
   git init
   git add .
   git commit -m "Initial CoastSight site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/coastsight.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, then pick `main` and `/ (root)`. Save.
4. After a minute your site is live at:
   - `https://<your-username>.github.io/coastsight/` — home
   - `https://<your-username>.github.io/coastsight/project/` — project overview
   - `https://<your-username>.github.io/coastsight/people/` — people
   - `https://<your-username>.github.io/coastsight/dashboard/` — dashboard

No build step is required — it's plain HTML/CSS/JS, so it also works by just double-clicking `index.html` locally.

## Notes

- The dashboard keeps all the original tracker functionality (search, filters, editable tasks, status dropdowns, and the funding snapshot). Edits are saved in each visitor's own browser via `localStorage`, exactly as in the original file.
- All pages share `assets/style.css` for the navigation bar, footer, and color palette (navy `#0A2F52` / teal `#007480` on a soft aqua `#EFF6F8` background, pulled from the CoastSight logo and darkened for AA text contrast) — edit that one file to restyle the whole site.
