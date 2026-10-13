---
name: tfl-setup
description: First-run setup. Builds the member's local folder, captures their Fractional Offer page (card and Snapshot Kit), their Messages tab, and their How To Find Companies instructions from their playbook, and fills their about files. Use when a member says "set me up," "get me started," when about/ is missing, or when any about file still says "needs input." Also handles updates like "my offer changed."
risk: low
---

# tfl-setup

## Summary

Everything the plugin needs about a member already exists in their playbook, graded. This skill captures it, page by page, so every other skill runs on the member's own approved material and never on a retyped version of it. About 10 minutes, no blank page, nothing technical on screen.

## Terms

- **The playbook**: the member's Google Doc from The Fractional Life, one tab per page. The pages this skill captures: Fractional Offer (the card, then the Snapshot Kit block under it), Messages, How To Find Companies, and the Strategic Partners list from Starting Company List.
- **About files**: the member's profile files in `about/`, copied from `templates/about-templates/` and filled here.

## When to Use

- "Set me up," "get me started," first run in an empty folder.
- Any skill finds `about/` missing or a file saying "needs input."
- "My offer changed," "my messages changed," "update my calendar link" (rerun that part only).

## When NOT to Use

- The files exist and are filled: ask what changed and update only that. Still run step 1 either way: the `templates/` copies and the house rules in `about/tfl-voice.md` are ours to keep current, and refreshing those is not re-interviewing.
- The member has no Fractional Offer page yet. It comes from their playbook build; say so and stop.

## Inputs

- A short conversation, one question at a time.
- The member's playbook pages, pasted word for word, or read from their playbook when they share the link and have Google Drive connected.
- `templates/about-templates/` and `templates/start-here-template.md`.

## Outputs

- The folder `the-fractional-life/` inside the folder the member opened: `about/`, `templates/`, `rules/`, `outputs/company-lists/`, `outputs/company-briefs/`, `outputs/value-adds/`, `outputs/messages/`.
- All templates installed word for word into `templates/` (keeping `about-templates/` intact), so the value-add skill can read `templates/value-add-template.md`. The review rubric installed word for word as `rules/value-add-review-rubric.md`. Every run refreshes these, so a workspace scaffolded by an older version stops serving retired rules.
- The house-owned sections of `about/tfl-voice.md` rebuilt from the current template, with the member's `## My personal notes` kept word for word.
- Filled about files, each page word for word, "needs input" marking anything the member couldn't supply.
- `START-HERE.md`, personalized.

## Process

1. **Build the folder** `the-fractional-life/` inside the folder the member opened, creating whichever of these are missing: `about/`, `templates/`, `rules/`, `outputs/company-lists/`, `outputs/company-briefs/`, `outputs/value-adds/`, `outputs/messages/`. Install all templates word for word into `templates/` (keeping the `about-templates/` folder intact) and the review rubric into `rules/`, overwriting any copy already there: everything under `templates/` and `rules/` is ours, never the member's work, so an old copy is stale, not precious. Then copy the about templates into `about/`, but only where that about file doesn't exist yet; never overwrite one that does. One exception: `about/tfl-voice.md` is part theirs and part ours. Everything under `## My personal notes`, up to the next `##` heading, is theirs, and every other section is the house standard. Rebuild it from the freshly installed `templates/about-templates/tfl-voice.md` on every run, splicing their `## My personal notes` back in word for word. If either file is missing that heading, leave it untouched and tell the member it needs a manual look; never guess at the boundary. One line to the member about what you made or refreshed.
2. **Capture the Fractional Offer page** into `about/tfl-fractional-offer.md`, word for word: the card and the Snapshot Kit under it. No page yet: stop with the named need.
3. **Capture the Messages tab** into `about/tfl-messages.md`, word for word, instructions lines included.
4. **Capture the search instructions** into `about/tfl-how-to-find-companies.md`: the How To Find Companies tab, then the Strategic Partners list from the Starting Company List tab. (An older playbook holds both in one Companies + People tab; same content, same paste.) Tabs still saying Coming Soon: write "needs input" and move on.
5. **Ask, one at a time:** their name and LinkedIn URL; their calendar booking link; anything about how they write (fine to skip); whether AI Ark is connected (if not, note "not yet" in the offer file and say everything still works).
6. **Fill the about files** from the answers. Never invent a value; "needs input" marks a blank.
7. **Write START-HERE.md** from the template with their name.
8. **Read the profile back** in 3 lines (title, wedge, target company) and ask "anything to fix?"
9. **Handoff:** "You're set. Give me a company you'd love to land and I'll build the Snapshot."

## Rules

- Every playbook page lands word for word. A retyped or summarized page drifts from the graded one; when the playbook changes, the member pastes the new page over the old.
- One question at a time; a wall of questions is a form.
- No file paths in conversation unless the member asks.

## Quality Checklist

- [ ] The offer file holds the card and the Snapshot Kit, word for word, plus the AI Ark line.
- [ ] The messages file holds the Messages tab word for word, or "needs input."
- [ ] The search-instructions file holds the tab and the partner list, or "needs input."
- [ ] Name, LinkedIn URL, and calendar link captured.
- [ ] START-HERE.md exists with their name.
- [ ] You ended by asking for a company.
