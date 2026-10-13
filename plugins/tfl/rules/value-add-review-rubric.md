# Value Add grading (2026-10-08, from the locked Footprint page)

This file grades one Snapshot page produced by the client-plugin chain (v3, live since 2026-10-10). The standard it grades against is the perfect example: the Footprint page, locked by Katie on 2026-10-08. Every rule below comes from a line on that page. The file moves to rules/value-add-review-rubric.md when Katie approves it.

It is written so that a model or a person with none of the conversation behind it can read any one rule, look at a page, and grade that page by it. Each rule says what is being checked, what passes, and what fails, with an example from the locked page where that helps. A rule that would only ever apply to one company does not belong here; that is a fix for the research skill.

## Terms

- **The page**: the one-page Snapshot a member sends a founder to earn a 20-minute call. Six sections, in this order: What I can see from the outside; Bottlenecks I've seen at companies this size; What these bottlenecks typically cost; What I'd do in a [wedge]; What I can't see from outside; then the closing line with the calendar link.
- **The brief**: the one-page pre-call brief that tfl-research-company writes about the company before the page is built. It holds every researched fact as a numbered, dated, sourced line.
- **The kit**: the member's Snapshot Kit, the block under their Fractional Offer card in their playbook. It holds the member's bottleneck patterns, the cost line, the three What I'd do lines, the byline, and the close. The kit is written once, at the member's card review, and every page copies from it.
- **A pattern**: one bottleneck in the kit, written as one or two sentences, for example "Customer go-lives pull product engineers off the roadmap. When customers sign faster than the team grows, the product plan slips one rollout at a time."
- **A clue tag**: the line under each pattern in the kit that says what a company must show before that pattern can go on its page. For the go-lives pattern above, the clue tag says: a forward-deployed, implementation, or onboarding engineer role posted; "signing customers faster than" language in a job post; a client much bigger than their usual one.

## The standard

A page the machine outputs is sent by the member with zero edits. The machine is allowed to stop and hold a company instead of producing a page. It is never allowed to produce a page that needs a human to fix something before it can go out. No section has to be filled to three bullets; two good lines are better than three with a weak one added.

## Verdict

Grade the sections in the order below. Stop at the first section that fails, because a wrong pick in an early section makes every later section look wrong, and fix that section's owner before grading further.

- **SEND**: every rule passes. The member can send the page as it is.
- **HOLD**: the machine stopped before producing a page and said why. The reasons it may hold are: no fact that passes section A; no pattern with a clue in the brief (section B); the cost line counts a kind of person the company doesn't have (section C); the member's calendar link is still a placeholder (section F). A HOLD counts as the machine doing its job. Count holds separately from fails; many holds mean the company list, the research, or the kit needs work, not the page.
- **FAIL**: the machine produced a page and at least one rule below fails on it. Each fail is written down with the rule it failed and the skill that owns that rule, and it becomes one edit to that skill. The page itself is never hand-edited to fix a fail.

## T. Title and byline (owner: the template and the kit)

- T1. The title is the company's name, a hyphen, and the kit's Snapshot name: "Footprint - Delivery Snapshot." The company's name is spelled the way the company spells it on its own site. The byline under the title is the kit's byline copied exactly, and it ends at "limited public info." Nothing is added after that.

## A. What I can see from the outside (line quality: tfl-research-company; the pick: tfl-write-value-add)

The bullets under the first heading. At least 1 and up to 3. If no fact passes the rules below, the machine holds the company and says the brief didn't have enough.

- A1. **Each fact is something the founder could confirm or deny in a few seconds.** That means a number, a name, a count, or something the company itself said, with the posting or page it said it on named. Passes: "Your Forward Deployed Engineer posting says you're signing customers fast enough that getting each one live is someone's entire job." Fails: "You're growing fast" (nothing to check).
- A2. **The brief dates every fact inside the last 12 months; no fact on the page carries a date or a time word.** The brief is where currency is checked. The page says the fact without "in September," "this month," "recently," "just," or "today." This rule is about the facts: a kit line (a pattern, a question, the cost line) goes on the page as the member wrote it, even when it carries a word like "today." Passes: "You raised a $25M Series B, and you're planning to double engineering and sales." Fails: "You raised a $25M Series B this month" (a time word, and wrong by the time the page is sent).
- A3. **A fact is only the fact. The machine adds nothing about what it means.** No "so," "which means," or "because" half written by the machine. Fails: "Henry has no head of sales today, so the CEO runs the sales team" (the "so" half is the machine's reading). Also fails: any fact that reads as a criticism, or that states something the company lacks ("You have no head of sales"). Criticism belongs in the patterns section, which says "companies this size" and never "you." Passes: the company's own description of its problem, quoted or paraphrased with the posting or page named, because then the company said it, not the machine.
- A4. **Facts are picked by type, in this order. A type the brief doesn't have is skipped, not filled with a weaker line.**
  1. The trigger: the event that makes this company worth writing to now (a raise, a new product, a new owner), with what the company says it will do with it in the same sentence. On Footprint: "You raised a $25M Series B, and you're planning to double engineering and sales."
  2. The credit: what the company has built, as named customers, growth, or scale. On Footprint: "Regulated banks, Bilt, Nuvei and MoonPay all use Percy for their compliance work."
  3. The setup: the fact that shows the first pattern on the page is real at this company. Pick it in this order of preference: the company's own words about the problem, from a posting or its site; if the brief has none, the job posting itself stated plainly ("You're hiring your first Forward Deployed Engineer"); if none, the count of open roles by function ("You have 7 roles open, and 5 of them are in sales or account work"). On Footprint: the Forward Deployed Engineer posting line, which is the company's own words.
- A5. **No two facts say the same thing in different words, and every fact is a line from the brief with nothing changed except "they" and the company's name becoming "you" and "your."** No person at the company is named on the page; the page talks to "you."

## B. Bottlenecks I've seen at companies this size (owner: tfl-identify-prospect-challenges)

The bullets under the second heading. Each one is a pattern copied from the kit. Up to 3. At least 1, otherwise the machine holds the company and says no pattern's clue appeared.

- B1. **A pattern goes on the page only if the brief holds a clue for it: a research line that states what the pattern's clue tag describes, of any type, including an [absence] or [loss] line.** The clue does not have to be one of the facts on the page. The page's facts are chosen by section A and never carry an absence or a loss; the patterns section says "companies this size" and never "you," so a pattern clued by what the company lacks or lost is honest on the page while the fact of it stays off. A pattern with no clue in the brief never goes on; a hunch is never a clue. Patterns whose clue is one of the facts on the page go first, so the founder reads the fact and then the pattern it sets up. On Footprint: the go-lives pattern's clue is the Forward Deployed Engineer fact and the status pattern's clue is the Series B fact (that pattern's clue tag includes "a raise with plans to grow more than one team at once"), so both are on the page and the go-lives pattern, clued by the setup fact (A4, type 3), goes first. On Alloy.ai, on a Fractional VP of Sales' kit: the brief's absence line "no sales leader role posted and names no one who leads sales" clues the founder-runs-every-deal patterns, which go on the page while the absence does not.
- B2. **The number of patterns is the number that have a clue in the brief, up to three.** The machine never adds a pattern to fill the section. When three patterns put the page over the word cap (F2), the third comes off with its question; two patterns is the locked page's shape.
- B3. **Each pattern is copied from the kit word for word, both sentences when the kit has two.** If a pattern's wording should change, the change is made in the kit at the member's card review, so every later page gets it. The page is never edited on its own.

## C. What these bottlenecks typically cost (owner: the kit; the gate is in tfl-write-value-add)

- C1. **The one bullet under this heading is the kit's cost line copied word for word, in the version the member chose at card review.** The kit's cost line counts a kind of person ("per product engineer," "per rep"). If the brief shows the company has none of those people, the machine holds the company and says so, rather than printing a cost that can't apply to them.

## D. What I'd do in a [wedge] (owner: the kit and the template)

- D1. **The three numbered lines under this heading are the kit's three What I'd do lines copied word for word, numbered 1 to 3.** No labels in front of them ("First," "Then," "By the end"), and nothing about this particular company inside them. They describe the member's offer, which is the same on every page.

## E. What I can't see from outside (owner: tfl-identify-prospect-challenges)

The bullets under the fifth heading. One question for each pattern on the page, in the same order as the patterns.

- E1. **Each question comes from its own pattern's question bank in the kit.** If a pattern is not on the page, none of its questions are on the page either.
- E2. **The one change the machine may make to a question: where the kit's question uses a generic word for a launch ("launch," "project," "initiative"), the page uses the word the company itself uses, taken from the brief.** At Footprint that word is "go-live," because it is the word in their postings. Every other word in the question stays as the kit has it. Passes: "Who do you ask today to find out where a go-live stands, and how many answers do you get?" (the kit's version says "where a launch stands").
- E3. **No two questions ask the same thing, and no question is already answered by a fact on the page.**

## F. Close and mechanics (owner: tfl-write-value-add; the docx: tfl-format-value-add)

- F1. **The last line of the page is the kit's close copied exactly, with the member's real calendar link in it, and nothing after it.** If the calendar link is still a placeholder, the page is held, not formatted.
- F2. **The headings are the five on the locked page, in that order, with nothing added, removed, or renamed.** The page is under 335 words (the locked page is 305).
- F3. **No word from the banned list in tfl-voice.md appears on the page, and the docx is one page.**

## G. The whole page (owner: Katie, and later the member)

- G1. **The send test.** Katie answers one question: would I send this exactly as it is? If no, she names the rule above that the page fails. If every rule passes and she still would not send it, this file is missing a rule; the fix is a new rule here, never an edit to the page.
- G2. **The founder test.** Reading only the facts, the founder can tell that the page was built about their company recently, by someone who read their job postings and not only their press.
- G3. **The machine test.** No line on the page repeats another line in different words, and nothing on it reads like a template with the company's name dropped in.

## Calibration (done 2026-10-08; rerun only if a rule changes)

1. The locked Footprint page: graded 2026-10-08, every rule passes (change-log entry 75). Two kit lines were changed for the voice canon's rule of three and the kit now matches the page (entry 76).
2. The machine's Footprint page of 7 Oct: graded 2026-10-08 (entry 77) and then retired to the delete pile. It failed A2, A3, A4, B1, B3, D1, E2 and F3, and every fail matched an edit Katie had made to reach the locked page, so this file and her judgment agree on every rule. If a rule here changes, grade the first clean-chat run of the chain the same way: it must fail where the page differs from the standard and nowhere else.
3. Henry, the Henry draft (Katie's 7 Oct edit): not yet graded. Expected fails: A4 (its third fact is the count when the brief had the company's own words) and F1 (placeholder link). Write down anything else that fails, and change nothing because of it until that kit is rebuilt on the recipe.

A grading file that cannot tell the machine's page from the locked page measures nothing.

## How a grade becomes an edit

- One run of the chain, then one grading session with this file, then one editing session on the skills. Never two runs between gradings.
- Every edit to a skill names the rule here that it fixes and the page that failed it. No edit is made because a page "reads off" without a rule to point at.
- An edit replaces a rule in a skill; it never adds one, so no skill gets longer over time.
- Three edits for the same rule means the skill that owns it is rewritten from scratch at half its current length.
- Each run and each grading session is an entry in client-plugin/value-add-change-log.md, numbered on from 75.
