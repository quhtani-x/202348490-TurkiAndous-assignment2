# Turki Andous — Portfolio (Assignment 2)

SWE363 Assignment 2: Interactive Features.

This is my portfolio from Assignment 1 with more interactivity added on top. It is still plain HTML, CSS and JavaScript with no frameworks and no build step.

| | |
| --- | --- |
| **Student** | Turki Andous, s202348490 |
| **Course** | SWE363 Web Engineering & Development, KFUPM |
| **Assignment 1** | <https://github.com/quhtani-x/s202348490-TurkiAndous-assignment1> |

## What's new since Assignment 1

**Project search.** There is now a search box above the projects. It filters as you type and works together with the category buttons, so you can pick "AI & Autonomy" and then search "drones". A small counter shows how many projects match. If nothing matches, the page tells you what you searched for and gives you a button to reset everything.

**Live GitHub repos.** Under the projects there is a "Latest on GitHub" section that pulls my most recently updated public repositories from the GitHub API. It shows a loading message while it waits. If GitHub can't be reached or the hourly limit is hit, it says so in plain words and shows a "Try again" button.

**Animations.** Project cards fade back in when a filter brings them back, the repo cards fade in one after another, invalid form fields shake when you submit, and the success message slides in. All of it turns off if your system has "reduce motion" enabled.

**Content.** I added my role as Chief Aeronautics & Propulsion Engineer on the AIAA Design/Build/Fly team at KFUPM.

These features are still there from Assignment 1:
- dark/light theme, saved in `localStorage`
- time-of-day greeting
- contact form validation with inline errors
- scroll reveal and animated stats
- mobile menu

## Running it locally

Clone the repo:

```bash
git clone https://github.com/quhtani-x/s202348490-TurkiAndous-assignment2.git
cd s202348490-TurkiAndous-assignment2
```

Then start a small local server. That way the GitHub fetch behaves the same as it does online:

```bash
python3 -m http.server 8000
```

Open <http://localhost:8000>.

Opening `index.html` directly by double-clicking also works. VS Code's Live Server extension is fine too. There is nothing to install.

You need an internet connection for the "Latest on GitHub" section and the fonts. Everything else works offline.

### Trying the new features

1. Go to **Projects**, type `flask` in the search box, and two projects should stay.
2. Click **AI & Autonomy** while `flask` is still typed. Nothing matches, so the empty message and reset button appear.
3. Scroll a bit further to see the GitHub repos load.
4. To see the error message, turn off your Wi-Fi and reload the page. Then turn it back on and press **Try again**.
5. In **Contact**, press **Send message** with the form empty to see the errors.

## Folder structure

```
├── index.html
├── css/styles.css
├── js/script.js
├── assets/
│   ├── resume.pdf
│   └── images/
└── docs/
    ├── ai-usage-report.md
    └── technical-documentation.md
```

How each feature works, the error states and the testing I did are in [`docs/technical-documentation.md`](docs/technical-documentation.md).

## AI use

I used Claude (Anthropic) through Claude Code for this assignment. It wrote the first version of the project search, the GitHub repos section, the new animations, and drafts of these docs. I reviewed and tested the result before submitting. The full declaration and usage log are in [`docs/ai-usage-report.md`](docs/ai-usage-report.md).

## Deployment

The site is static, so GitHub Pages works. Go to **Settings → Pages**, set the source to `main` / root, and save. It will be at `https://quhtani-x.github.io/s202348490-TurkiAndous-assignment2/`.
