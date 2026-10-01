# How I built this with Claude Code

I built the catalog with [Claude Code](https://www.anthropic.com/claude-code), Anthropic's agentic coding tool, as my pair programmer. I owned the direction, the decisions and every approval. Claude Code did most of the hands-on work: reading the code, writing it, building prototypes, checking deploys and writing documentation. This page shows what that looked like, with numbers taken from the two private Git histories.

## How I worked

- **Plan first, then build.** For anything with more than one step I had Claude Code explore the code and write a plan before touching a file. I read the plan, changed it when I disagreed, and only then let it start.
- **One step at a time.** Claude Code stopped after each step and reported what it had done and what it had checked. Nothing went to the live site until I said "next".
- **Decisions stayed with me.** When a choice was mine to make, Claude Code asked: whether to use the owner's real photos, whether to rewrite Git history, which of two readings of a request I meant. It gave a recommendation each time; I did not always take it.
- **Project notes in a `CLAUDE.md` file.** It holds the architecture, the working rules and the open items, and Claude Code reads it at the start of every session. It is kept out of the repository. Updating it was part of the work.
- **Measure, don't eyeball.** The useful checks were the ones that produced a number: page width at three phone sizes, tap-target heights, a clean install with two versions of npm, the build result for each commit.

## By the numbers

| | |
|---|---|
| Shopify theme pulled into Git | Sep 29, 2026, late afternoon |
| Catalog proof of concept committed | Sep 29, the same evening |
| Clean repository for the catalog | Sep 30 |
| Six prototypes shown to the owner | Sep 30, evening |
| Chosen design live | Sep 30, about 50 minutes after the prototypes went up |
| First tagged release | Oct 1, just after midnight |
| Commits across both repositories | 22 |
| Co-authored with Claude | 15 |
| Made by the admin when a product or setting was saved | 6 |
| Made by hand | 1 |

Dates are Pacific time. The Shopify store itself, and the import of its 239 products, were built before the first date in this table.

## What Claude Code produced

- A proof of concept of the catalog: the site, the admin and the deployment.
- Six working design prototypes, each with three screens, and a logo for each.
- The chosen design applied to the real site, with self-hosted fonts, a logo and favicons.
- An owner's guide in English and Chinese.
- 42 full-page screenshots of the prototypes, which is where the images in this repository come from.
- The first draft of this showcase, which I then reviewed.

## What went wrong, and how it was caught

The mistakes are the most useful part of this page.

| What happened | How it was caught |
|---|---|
| One prototype, Sea Glass, scrolled sideways on every phone screen. The screenshots looked fine because they only captured the visible width. | I asked whether the designs were good at phone size. Instead of answering from the screenshots, Claude Code measured page width at 320, 360 and 390 pixels and found the overflow. |
| The category menu was in alphabetical order, although the code comment said it followed the owner's order. | Claude Code noticed while writing the owner's guide, when a sentence about menu order did not match the live site. It reported the mismatch, and I asked for the fix. |
| An edit to the owner's guide replaced the wrong words: a search for "Empty" matched two unrelated sentences. | Claude Code read the tool's reply, saw the wrong sentences had changed, restored them and told me. |
| The owner's first name appeared in code comments, commit messages and a release tag. | I asked for a review. The files and the tag were fixed, and "the shop owner" became a written project rule. I chose not to rewrite the Git history of a private repository. |
| I suggested committing the prototype folder at the top of the repository so the live site would serve it to the owner. | Claude Code pointed out that the build publishes only one folder, moved the prototypes there, and marked them so search engines would skip them, all before anything was pushed. |

Two habits made these cheap to fix. Claude Code said plainly what it had not verified, such as how the site renders on a real phone or what the admin's buttons are called. And every deploy was confirmed twice: by the build result that Cloudflare reports to GitHub, and by loading the live pages.

## What I would tell another developer

- **Give it real reference material.** Three screenshots of the shop's own listings did more for the designs than any adjectives I could have written.
- **Ask for options, not an answer.** Six prototypes cost one evening, and the owner made a choice I would not have predicted.
- **Keep the approval step.** The pause before each push is where I caught the things that mattered to me and not to the code.

---

The source code and the shop's content are kept in a private repository. Back to the [README](README.md).
