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
7. **CSS style pass.** On a separate branch
   (`style/css-refresh`), it reviewed `css/styles.css`, explained eight proposed
   improvements, and only made them after I approved the plan: shared tokens for
   radius and timing, one shared card style, visible focus rings on inputs, hover
   lift only on devices with a mouse, removing both `!important` rules, small
   layout fixes, hover polish and a dimmed background behind the mobile menu, and
   a complete reduced-motion rule. It also found and fixed a bug where the
   scroll-reveal transition made project cards take 0.7s instead of 0.3s to lift
   on hover. It then updated `README.md`, including fixing a wrong example
   ("drones" finds nothing, "drone" does).

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

ive built mostly everything since phase 1 and before that myself for my portfolio but enhanced the wording and animations using AI , i changed some animation timing in the animations he added , also the wordings of my achievemnts as well , mostly styling was proof read by ai , and i changed some colors to match my style.

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
1- Claude Opus 5.5 , 10-25-2206 | readme.md | i read everything he wrote and changed some things and features he said the web app had but i didnt implement it yet, i asked him to check my previous readmd.md and write me a similar one based on this assignemnt , and he did write it , but added some parts that were not true, as i checked back the code ad actaully verified that he made my site better by lying in the readmd.

2- claude Opus 5.5 , 10-25-2026  | CSS file | i reviwed all the colors and anmiations he made , and changed them based on my prefernces. and made sure that what i changed was actually reflected in the site by testing it.  

3- Claude Opus 5.5 (Claude Code) , 10-25-2026 | `css/styles.css`, `README.md`, `docs/ai-usage-report.md` | Asked it to improve my CSS on a new branch and update my outdated README. It explained the 8 changes first and only edited the files after I approved. It tested the result in a browser at desktop and phone sizes, in dark and light themes (hover, focus rings, mobile menu, search and filter). It also added this entry and item 7 in section 2. The changes are in commits on the `style/css-refresh` branch so I can review them before merging.



## 7. Declaration

> I declare that this report and the attached evidence document all of my AI use
> in this assignment, with complete and unedited conversations, and that I
> understand and can explain all the code I submitted. I understand that
> undeclared AI use or a false declaration will be treated as plagiarism
> according to KFUPM regulations.

**Name:** Turki Andous
**Student ID:** s202348490
**Date:** 2026-10-25
