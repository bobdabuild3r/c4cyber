# Cert IV Cyber Security: student schedule

A static site for GitHub Pages. Students see the week-by-week schedule and due dates.
All content lives in `schedule.json`. The page (`index.html`) never needs editing.

## Publish on GitHub Pages (one time)

1. Create a new repository on github.com (Public, so Pages works on a free account).
2. Click **Add file → Upload files**, drag in `index.html`, `schedule.json` and `README.md`, then **Commit changes**.
3. Open **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, Branch to **main** and folder to **/(root)**, then **Save**.
4. After a minute or two the site address appears at the top of that page: `https://<your-username>.github.io/<repo-name>/`.

## Change a due date

1. In the repository, open `schedule.json` and click the pencil icon (**Edit this file**).
2. Find the assessment under `"assessments"` and change its date. Dates are always `YYYY-MM-DD`:

   ```json
   { "title": "Cyber Project: Project and Quiz", "unit": "project", "due": "2027-06-13" }
   ```

3. Click **Commit changes**. The site updates within about a minute (refresh the page).

## Other edits

| To change | Edit in `schedule.json` |
|---|---|
| A class's date or content | `"sessions"`: `date`, `topics`, `activities`, `homework` |
| Which unit a class belongs to | `"unit"`: one of `fund`, `pentest`, `nsda`, `automate`, `project`, `wit`, `general` |
| Public holidays | `"holidays"` |
| Holiday breaks (no teaching week) | `"breaks"` |
| Course start/end, reminder text, platform link | `"course"` |
| OneDrive folder for a unit | `"units"` → `"folder"` |
| "Last updated" note at the bottom | `"updated"` |

- An optional `"note"` on an assessment shows under the due date.
- In text, use `\n` for a new line. The file already does this, so copy an existing line's style.
- Week numbers, the "this week" highlight, countdowns and holiday rows are worked out automatically from the dates.

## Add the OneDrive folder links

Each unit in `schedule.json` has a `"folder"` line. Paste the unit's OneDrive folder link between the quotes:

```json
{ "id": "nsda", "name": "Network Security and Data Analysis", "codes": "VU23216, VU23218", "folder": "https://..." }
```

Once a link is set, students see:
- **Unit files ↗** on every class of that unit
- **Documents ↗** on that unit's due-date row, and **Assessment documents ↗** in the Due dates tab
- **Open <unit> folder ↗** next to the filter buttons when they filter to that unit

A unit with an empty `"folder"` shows no button. The link must start with `https://`.
Only students you have shared the folder with in OneDrive can open it.

## If the page says "formatting mistake"

The site shows the line number where `schedule.json` broke. Usually it is a missing comma between items, a missing `"` quote, or a comma after the last item in a list. Open the file's **History** in GitHub to compare with the previous working version.

## Preview a different date

Add `?today=2027-03-24` to the end of the site address to see how the page looks on that day.
