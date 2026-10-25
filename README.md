# Turki Andous — Portfolio (Assignment 2)

SWE363 Assignment 2: Interactive Features.

This is my portfolio from Assignment 1 with more interactivity added on top. It is still plain HTML, CSS and JavaScript with no frameworks, no libraries and no build step.

| | |
| --- | --- |
| **Student** | Turki Andous, s202348490 |
| **Course** | SWE363 Web Engineering & Development, KFUPM |
| **Assignment 1** | <https://github.com/quhtani-x/s202348490-TurkiAndous-assignment1> |

## What's new since Assignment 1

**Project search.** There is a search box above the projects. It filters as you type and works together with the category buttons (All, AI & Autonomy, Web & Full-stack), so you can pick "AI & Autonomy" and then search "drone". A counter shows how many projects match, for example "Showing 2 of 7 projects". If nothing matches, the page tells you what you searched for and gives you a button that clears the search and the filter.

**Live GitHub repos.** Under the projects there is a "Latest on GitHub" section that loads my six most recently updated public repositories (forks are skipped) from the GitHub API. Each card shows the description, language, stars and last update date. A spinner shows while it loads. If GitHub can't be reached, or the hourly request limit is hit, it says so in plain words and shows a "Try again" button.

**Animations.** Project cards fade back in when a filter or search brings them back, the repo cards fade in one after another, invalid form fields shake when you submit, and the success message slides in.

**Style pass.** I cleaned up the stylesheet:
- Corner sizes and animation speeds are now shared values at the top of `css/styles.css`, so every card uses the same radius and timing.
- Keyboard users get a visible focus ring on the search box and form fields.
- Cards only lift on hover on devices with a mouse, so they don't get stuck lifted after a tap on a phone.
- Project cards glow and their image zooms slightly on hover.
- The page dims behind the open mobile menu.
- The "reduce motion" setting now turns off every animation, not just some.

**Content.** I added my role as Chief Aeronautics & Propulsion Engineer on the AIAA Design/Build/Fly team at KFUPM.

### Still there from Assignment 1

- dark/light theme toggle: it follows your system setting on the first visit and remembers your choice in `localStorage`
- greeting that changes with the time of day (morning, afternoon, evening)
- typing animation that cycles through what I build in the hero
- navigation that highlights the section you are reading, and a slide-out menu on phones and tablets (closes with <kbd>Esc</kbd>)
- stats that count up when they scroll into view, and sections that fade in on scroll
- contact form validation with inline error messages (front-end only, nothing is actually sent)
- a "skip to content" link for keyboard users

## Running it locally

Clone the repo:

```bash
git clone https://github.com/quhtani-x/202348490-TurkiAndous-assignment2.git
```

```bash
cd 202348490-TurkiAndous-assignment2
```

Then start a small local server. That way the GitHub fetch behaves the same as it does online:

```bash
python3 -m http.server 8000
```

Open <http://localhost:8000>.

Opening `index.html` directly by double-clicking also works. VS Code's Live Server extension is fine too. There is nothing to install.

You need an internet connection for the "Latest on GitHub" section and the fonts. Everything else works offline.

### Trying the new features

1. Go to **Projects** and type `flask` in the search box. Two projects should stay, and the counter says "Showing 2 of 7 projects".
2. Click **AI & Autonomy** while `flask` is still typed. Nothing matches, so the empty message and reset button appear.
3. Press the reset button, then click **AI & Autonomy** and type `drone`. One project stays.
4. Scroll a bit further to see the GitHub repos load.
5. To see the error message, turn off your Wi-Fi and reload the page. Then turn it back on and press **Try again**.
6. In **Contact**, press **Send message** with the form empty to see the errors and the shake.
7. Press <kbd>Tab</kbd> to move through the page and see the focus rings.

## Folder structure

```
├── index.html
├── css/styles.css
├── js/script.js
├── assets/
│   ├── resume.pdf
│   └── images/
│       ├── profile.jpg
│       └── projects/      (one SVG per project card)
└── docs/
    ├── ai-usage-report.md
    └── technical-documentation.md
```

How each feature works, the error states and the testing I did are in [`docs/technical-documentation.md`](docs/technical-documentation.md).

## AI use

I used Claude (Anthropic) through Claude Code for this assignment. Claude added animations, helped with the wording of my content, did a CSS style pass that fixed some styling glitches, and drafted this README and the docs. I reviewed and tested everything before submitting, and changed what didn't match my site or my style. The full declaration and usage log are in [`docs/ai-usage-report.md`](docs/ai-usage-report.md).

## Deployment

The site is static, so GitHub Pages works. Go to **Settings → Pages**, set the source to `main` / root, and save. It will be at `https://quhtani-x.github.io/202348490-TurkiAndous-assignment2/`.
