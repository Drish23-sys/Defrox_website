# DEFROX website

Static site: no build step. `index.html` + `events.json` + `img/` + `video/`.

## Add or change an event
1. Upload the event photo to `img/` (JPG/WebP, about 1200 px wide).
2. Open `events.json` and copy one `{ ... }` block. Paste it inside the list, **add a comma between blocks**, edit, and commit.

| Field | What to put |
|---|---|
| `name` | Event title |
| `type` | `WORKSHOP`, `TECH SESSION`, `BUILD CHALLENGE` or any new word (e.g. `HACKATHON`, `TALK`). A filter button appears automatically. |
| `field` | Short topic line under the title |
| `image` | File name in `img/` (or a full https link) |
| `date` | `YYYY-MM-DD`, e.g. `2026-11-15`. Leave `""` for "DATE TBA". |
| `time`, `venue` | Optional, e.g. `"4:00 PM"`, `"Seminar Hall"` |
| `register` | Optional link. Adds a **Register** button in the popup. |
| `description` | 1–2 sentences shown in the popup |
| `details` | Optional extra line. Clear it once you set a real date and venue. |

Upcoming events are listed first (soonest first), then date TBA, then completed ones, which are labelled **COMPLETED** automatically. Delete an event to remove it.

If the site shows the old events after an edit, the JSON probably has a typo (missing comma or quote). Check it at jsonlint.com.

## Join form
Already connected to Web3Forms (the access key is in `const FORM` in `index.html`; it is meant to be public). Submissions arrive in the email on your Web3Forms account. To use a different form, change the key there. In the Web3Forms dashboard you can restrict the key to your live domain.

## Deploy
GitHub repo (files at the top level) -> Vercel -> Framework preset **Other**, no build command. Every commit redeploys automatically.
