# Math Adventures Levels 1–4 — Tutor Training

Short ID: `mathbr14` · Languages: `pt` (default) and `en` · Published on GitHub Pages, opened inside the Kodland LMS (iframe).

Three modules: **Module 1** Math at Kodland and the technical side · **Module 2** Teaching math for the first time (one real lesson as the example) · **Module 3** the level cards and the final survey.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The page. `?lang=pt` or `?lang=en` picks the language (default `pt`). |
| `assets/content-pt.js` | All Portuguese texts (modules, levels, quizzes, surveys, buttons). |
| `assets/content-en.js` | All English texts. |
| `assets/engine.js` | The logic: modules, level cards, checks, surveys, simulations, LMS bridge, dev mode. |
| `assets/course.css` | Styles. |
| `assets/img/` | Marker icons, and the pictures in `img/pt/`, `img/en/` (same names, text translated). |
| `apps-script.gs` | The Google Sheet code (not needed on GitHub). |

## Developer mode

Add `?dev=1` to the link (code `MATHDEV`, or Shift+D three times): it unlocks every module and simulation, skips the surveys and sends nothing to the LMS.

## Videos

In **both** `assets/content-pt.js` and `assets/content-en.js`, find `"videos"` near the end of the file and paste each link between the quotes (YouTube, Google Drive shared as "Anyone with the link", or Loom). While a link is empty, the page shows a dashed box that says what to record.

| Slot | Where | What to record |
| --- | --- | --- |
| `teach` | Module 2, end | A full 60-minute lesson (ideally Level 1, Lesson 1) |
| `clip-opening` | Module 2, "How a 60-minute lesson runs" | The first 5 minutes: greeting, mic and camera, warm-up, Foxy |
| `clip-explain` | Module 2, "How to explain a math idea" | Explaining zero from a real object to the slide to 0 |
| `clip-mistake` | Module 2, "Questions" | Handling a wrong count with "No problem!" |
| `clip-individual` | Module 2, end | The individual part with the green button |

## Google Sheet

**Already connected:** `SURVEY_URL` in `assets/engine.js` (line 11) points to the Math Brazil survey Sheet.

`apps-script.gs` is the code of that Sheet (Extensions → Apps Script). It writes every answer into two tabs — **Start survey** and **Final survey**, with a `training` column (`mathbr14`, `mathbr57`) — and rebuilds a **Summary** tab after every answer: start vs. final ratings per training, feelings, and the list of tutors who need follow-up.

To update the code: paste the new `apps-script.gs` over the old one, click **Save**, then **Deploy → Manage deployments → ✏️ → Version: New version → Deploy** (the `/exec` URL stays the same). Reload the Sheet: a **📊 Surveys** menu appears. Run **Merge old tabs into the main tabs** once to move the rows of the old split tabs (for example "Lvl 1-4 Start survey") into the two main tabs.
