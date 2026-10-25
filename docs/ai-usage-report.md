# AI Usage Report

**Assignment 2 — Interactive Features**
**Student:** Turki Andous (s202348490) · **Course:** SWE363, KFUPM

---

## 1. Tools used

| Tool | Model | How I used it |
| --- | --- | --- |
| Claude Code (Anthropic), a terminal coding assistant that can read and edit the project files | Claude Opus 5.5 | Wrote the first version of all the Assignment 2 code changes and the drafts of the README and technical documentation, and tested the features in a browser |

I used one tool and one conversation for the whole assignment.

## 2. What the AI did

I gave Claude my Assignment 1 repository and the Assignment 2 brief, and asked
it to add what the brief requires without overdoing it. In that conversation it:

1. **Set up the project.** Copied my Assignment 1 site into a new local folder as
   the starting point.
2. **Added live project search.** Added a search box that works together with
   the existing category filter, a result counter, and an empty state with a reset
   button (`index.html`, `css/styles.css`, `js/script.js`).
3. **Added the GitHub repos section.** Fetches my latest public repos from the
   GitHub API, with loading, error, retry and empty states (same three files).
4. **Added animations.** Fade-in for cards, a shake on invalid form fields, and an
   animated success message, all disabled under reduced motion (`css/styles.css`,
   `js/script.js`).
5. **Updated content.** Added my AIAA Design/Build/Fly role to the experience
   timeline, from the details I gave it (`index.html`).
6. **Drafted documentation.** Wrote drafts of `README.md`,
   `docs/technical-documentation.md` and this report.

Decisions that came from me, not the AI:
- Keeping the scope small: three features, no frameworks.
- Building on Assignment 1 rather than starting over.
- Adding the DBF role.
- The README tone: plain and not overly polished.

## 3. How the output was checked

The AI ran the site on a local server and tested each feature in a browser before
committing it:

- **Search.** Typing "flask" leaves 2 of 7 projects. Adding the AI filter shows
  the empty state, and the reset button brings all 7 back.
- **GitHub list.** The normal load shows six repos. Replacing `fetch` with a
  network error, an HTTP 403 and an empty response each shows the right message.
- **Animations and form.** Invalid fields shake, and a valid submit shows the
  animated success message.

Testing found one real bug: the **Try again** button showed even when nothing had
failed. The `.btn` style set `display`, which overrode the `hidden` attribute.
This was fixed with a `#ghRetry[hidden] { display: none; }` rule.

I then tested it myself on multiple devices and in Chrome, Safari and Edge. The
search, filter, GitHub list, animations and form worked the same in all of them.

## 4. What I changed in the AI output

After reviewing and testing it, I kept the AI's version as it was. I did not
find anything that needed changing.

## 5. What I learned

Three things in this code were new to me. I read up on them on W3Schools until I
understood them, and they were an eye opener:

- **`response.ok`.** `fetch` only fails by itself when the network is down. If
  GitHub answers with an error like 403 or 500, the request still "succeeds", so
  the code has to check `response.ok` and throw an error itself. Otherwise the
  error message would never show.
- **`textContent` vs `innerHTML`.** `innerHTML` treats text as HTML, so if a repo
  description contained a tag or a script, it would run on my page. `textContent`
  always puts it in as plain text, which is why the repo cards are built that way.
- **Search and filter in sync.** Both the category buttons and the search box
  call the same `updateProjects()` function. A card shows only if it is in the
  active category and contains the search text, so the two can never disagree.

## 6. Usage log

| ID | Tool (model) | Date | Purpose | Files affected | What I changed and how I verified it |
| --- | --- | --- | --- | --- | --- |
| C01 | Claude Code (Claude Opus 5.5) | 2026-10-25 | Plan Assignment 2 and implement project search, GitHub API section, animations, DBF timeline entry; draft README, technical docs and this report | `index.html`, `css/styles.css`, `js/script.js`, `README.md`, `docs/technical-documentation.md`, `docs/ai-usage-report.md`, `.gitignore` | No changes after review; tested on multiple devices in Chrome, Safari and Edge |
| A01 | Claude Code (Claude Opus 5.5) | 2026-10-25 | The code as the AI first produced it, before my edits: the AI-authored commits in this repository | Same as C01 | Kept as the git commits, and exported into `artifacts/` in the evidence ZIP |

The C01 conversation also covered unrelated SWE363 lab tasks (labs 5-3 to 5-6)
before Assignment 2. It is submitted complete and unedited.

## 7. Declaration

> I declare that this report and the attached evidence document all of my AI use
> in this assignment, with complete and unedited conversations, and that I
> understand and can explain all the code I submitted. I understand that
> undeclared AI use or a false declaration will be treated as plagiarism
> according to KFUPM regulations.

**Name:** Turki Andous
**Student ID:** s202348490
**Date:** 2026-10-25
