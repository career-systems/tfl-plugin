---
name: tfl-setup
description: First-run setup. Builds the member's local folder at the-fractional-life/, captures their Fractional Offer card and their how-to-find-companies page from their playbook, and fills their about files. Use when a member says "set me up," "get me started," when about/ is missing, or when any about file still says "needs input." Also handles updates like "my offer changed" or "update my wins."
risk: low
---

# tfl-setup

## Summary

Get a member from "just added the connector" to "profile filled, first company
named" in about 10 minutes, without a blank page or a technical step. The
member's offer already exists in their playbook, so this is capture, not
creation: they paste their Fractional Offer page, answer a few short
questions, and every other skill can run.

## Problem Solved

Every other skill in this repo depends on the member's profile: their offer
card, wins, and voice. Left to fill templates alone, members stall at the
blank page or abandon anything that looks technical. And an offer retyped from
memory drifts from the graded card in their playbook. This skill captures the
card exactly, and the rest in one short conversation, so the chain never runs
on empty or drifted files.

## When to Use

- "Set me up," "get me started," first run in an empty folder.
- Any skill finds `about/` missing or a file still saying "needs input."
- "My offer changed," "update my wins," "change my voice notes" (rerun just
  that part).

## When NOT to Use

- The files exist and are filled. Don't re-interview; ask what changed and
  update only that.
- The member has no Fractional Offer card yet. The card comes from their
  playbook build. Say that plainly and stop; this skill captures an existing
  offer, it doesn't create one.
- The member names a company to pursue and their profile is already complete.
  Go straight to the prospecting skills.

## Inputs

- A short conversation. One question at a time, never a form.
- The member's Fractional Offer page, pasted from their playbook (or the
  playbook link, if they'd rather you read it there).
- The "How To Find Your Target Companies" section of their playbook's
  Companies + People tab (Steps 1 to 4, the creative moves, and their
  Strategic Partners list), pasted the same way. These are their custom
  weekly search instructions; the weekly list build runs on them.
- `templates/about-templates/` and `templates/start-here-template.md` from
  this repo.

## Outputs

- The folder scaffold at `the-fractional-life/`: `about/`, `templates/`,
  `outputs/company-lists/`, `outputs/company-profiles/`,
  `outputs/value-adds/`, `outputs/messages/`.
- All templates installed word for word into `templates/` (keeping
  `about-templates/` intact), so the value-add skill can read
  `templates/value-add-template.md`.
- Filled about files in `about/`, with the offer card word for word and
  "needs input" marking any blank the member couldn't fill.
- `START-HERE.md` in their folder, personalized with their name.

## Process

1. **Build the scaffold** at `the-fractional-life/` if it doesn't exist:
   `about/`, `templates/`, `outputs/company-lists/`, `outputs/company-profiles/`,
   `outputs/value-adds/`, `outputs/messages/`. Install all templates word for
   word into `templates/` (keeping the `about-templates/` folder intact).
   Then copy the about templates into `about/`. Say one line about what you
   made, no tech talk.
2. **Capture the offer card.** Ask them to paste their Fractional Offer page
   from their playbook, or drop the playbook link for you to read. It carries
   their title, wedge, pricing, targets, and outcome, so it replaces a dozen
   questions. Save it into the offer file exactly as pasted, word for word.
   No card yet? Stop with the named need: the card comes from their playbook
   first.
3. **Capture their search instructions.** Ask them to paste the "How To Find
   Your Target Companies" section of their playbook's Companies + People tab:
   Steps 1 to 4, the creative moves, and their Strategic Partners list. Save
   it word for word into `about/tfl-how-to-find-companies.md`. This is the
   recipe their weekly target list runs on. Not built yet (their playbook's
   Companies tab still says Coming Soon)? Write "needs input" and move on;
   the weekly routine will ask again when it's ready.
4. **Interview, one question at a time.**
   1. Your name and LinkedIn URL.
   2. At least 3 career wins, each with a real number. Big brand names are
      welcome here; they're useful context. (The value-add skill retells each
      win about the kind of business when it goes on a page.) More than 3 is
      good: each value-add uses the 3 that fit that company best.
   3. Anything about how you write? Formality, phrases you use, anything
      you'd never say. (Fine to skip; house rules cover them.)
   4. Do you have AI Ark connected yet? (If not: point them to where to get
      it, note "not yet" in the offer file, and reassure them everything
      still works; they'll just confirm more org facts by hand.)
5. **Fill the about files** from their answers. If they don't have a number
   for a win, write "needs input" in that slot. Never invent one.
6. **Write START-HERE.md** into their folder from the template, personalized
   with their name.
7. **Read their profile back** in 3-4 lines: title, wedge, target company,
   wins count. Ask "anything to fix?"
8. **The handoff:** "You're set. Want to see it work? Give me a company you'd
   love to land." If they name one, kick off the tfl-build-value-add
   workflow.

## Rules

- One question at a time. A wall of questions is a form, and forms get
  abandoned.
- **The offer card lands word for word.** Retyping or summarizing it creates
  a second version that drifts from the playbook. When the playbook's offer
  changes, the member pastes the new page over the old one.
- Never invent a number, a win, or a target detail. Marked blanks beat
  guesses.
- Nothing technical on screen: no file paths in conversation unless they ask.
  "I saved your offer" beats naming a file path.
- If they've clearly done this before (files exist and are filled), don't
  re-interview. Ask what changed.

## Quality Checklist

- [ ] The offer file holds the member's Fractional Offer card, word for word,
      plus the AI Ark line.
- [ ] Every about file is filled or has a clearly marked "needs input."
- [ ] The how-to-find-companies file holds their playbook's search
      instructions word for word, or a marked "needs input."
- [ ] At least 3 wins with real numbers captured.
- [ ] AI Ark status recorded.
- [ ] START-HERE.md exists with their name in it.
- [ ] You ended by asking for a company they'd love to land.
