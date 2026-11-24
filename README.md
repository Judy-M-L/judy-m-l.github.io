# judy-m-l.github.io

Jekyll study blog on GitHub Pages. No local build needed; push to `main` and it's live in about a minute.

## Write a study note
1. Copy `_drafts/study-note-template.md` to `_posts/YYYY-MM-DD-short-title.md` (files in `_drafts/` are not published).
2. Top of file:
   ```
   ---
   layout: post
   title: "Post title"
   summary: "One line shown in the list."
   tags: [study, scm]
   ---
   ```
   - `study` puts the post under **Study notes**. Without it the post goes under **Essays**.
   - Add a topic tag after it: `scm`, `sql`, `ascm`.
3. Markdown below. Push.

## Pages
- `index.html` home · `writing.html` all notes and essays · `work.md` case studies · `about.md`
- "Studying now" on the home page is a plain list in `index.html`; edit it by hand.
- `assets/Jiyoung-Min-Resume.pdf` — replace to update the resume (keep the phone number out).
- `_layouts/default.html` holds all CSS.
