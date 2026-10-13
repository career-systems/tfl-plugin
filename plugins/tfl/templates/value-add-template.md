# Snapshot template

The one page a member sends a founder to earn a 20-minute call. The member's outreach messages promise it and the first follow up delivers it.

Two inputs feed every bracket below but one (the calendar link, from the member's about file). *The brief* is the one-page pre-call brief tfl-research-company writes for the company: who they are, what they do, fit, and a list of research lines with sources. *The kit* is the member's Snapshot Kit, the block under their Fractional Offer card: a bank of bottleneck patterns (each one or two sentences, with a clue tag and its questions), the cost line, the three What I'd do lines, the byline, and the close. Everything on the page except the company's name, the 3 facts, and the calendar link comes from the kit; the name and the 3 facts come from the brief.

Section order, headings, the byline, and the close never change. Headings are Heading 3. "What I'd do" is a numbered list with no labels in front of the lines; every other section is bullets. No bullet section has to reach three: the facts are at least 1 and up to 3, the patterns at least 1 and up to 3, the questions one per pattern. A section is never padded to fill its brackets. Nothing comes after the close. No fact carries a date or a time word ("this month," "recently," "today"); the brief holds the dates. The kit's lines go on the page as the member wrote them, even when one carries a word like "today."

```
# {Company} - {Function} Snapshot

Built by [{Member name}]({member LinkedIn URL}), Fractional {Title}. I put this together based on limited public info.

### What I can see from the outside
- {fact 1}
- {fact 2}
- {fact 3}

### Bottlenecks I've seen at companies this size
- {pattern 1}
- {pattern 2}
- {pattern 3}

### What these bottlenecks typically cost
- {cost line}

### What I'd do in a {wedge}
1. {do 1}
2. {do 2}
3. {do 3}

### What I can't see from outside
- {question 1}
- {question 2}
- {question 3}

If 70-80% of this feels right, [you can book 20 minutes here]({calendar link}). We'll fix what I got wrong and see if a {wedge} would pay for itself.
```

## Where each bracket comes from

| Bracket | Source |
| --- | --- |
| {Company} | The company's name as it writes it, from the brief. |
| {Function} | The kit's Snapshot name line (the word before "Snapshot"). |
| {Title}, {Member name}, {member LinkedIn URL} | The kit's byline line. |
| {calendar link} | `about/tfl-about-me.md`, filled at setup. |
| {fact 1}, {fact 2}, {fact 3} | One to three research lines from the brief, switched to "you" by tfl-write-value-add and otherwise unchanged. Picked by type, in this order, skipping a type the brief lacks: the trigger (the raise, product, or owner, with its stated use in the same sentence); the credit (customers, growth, scale); then the picked patterns' clue lines that the page can carry (the company's own words about the problem with the posting or page named, the posting stated plainly, the count of open roles), in pick order, until the page has three. A fact is only the fact: nothing added about what it means, no criticism, no absence ("has no head of sales"), no loss. |
| {pattern 1}, {pattern 2}, {pattern 3} | Kit patterns picked by tfl-identify-prospect-challenges, every sentence the kit line has, word for word. A pattern goes on the page when the brief holds a clue for it, a research line of any type including an absence or a loss; the clue need not be one of the facts on the page, because this section says "companies this size" and never "you." Patterns whose clue is a fact on the page go first. As many as have a clue, one to three; the rest of the bullets are left out, never padded; three that put the page over 335 words become two. |
| {cost line} | The kit's cost line, word for word. The kit holds one version; which one was set at the member's card review. |
| {wedge} | The kit's wedge phrase, like "2-week Delivery Audit". |
| {do 1 to 3} | The kit's three What I'd do lines, word for word, numbered, no labels. |
| {question 1 to 3} | One per pattern on the page, from that pattern's bank in the kit, in pattern order. The one change allowed: the kit's generic word for a launch ("launch," "project," "initiative") becomes the word the company itself uses, from the brief ("go-live," "rollout"). Every other word stays. |

## Member review notes (under the page, never sent)

- Source and date for each of the 3 facts, copied from the brief.
- The fit line from the brief.
- The clue each picked pattern rests on.
- The member's honesty check: "Have I seen each bottleneck at a company I worked with? Could I tell a story about it on the call?" A no means cut it.

## Example

The locked standard (Katie, 2026-10-08): a real company, Footprint, researched October 2026, the member a Fractional Program Manager. Every page is graded against it (rules/value-add-review-rubric.md until that file moves to rules/). Copy the shape, never the content. The calendar link is a placeholder because the page is not formatted until the member's real link is in it.

```
# Footprint - Delivery Snapshot

Built by [Sam Rivera](https://www.linkedin.com/in/your-profile/), Fractional Program Manager. I put this together based on limited public info.

### What I can see from the outside
- You raised a $25M Series B, and you're planning to double engineering and sales.
- Regulated banks, Bilt, Nuvei and MoonPay all use Percy for their compliance work.
- Your Forward Deployed Engineer posting says you're signing customers fast enough that getting each one live is someone's entire job.

### Bottlenecks I've seen at companies this size
- Customer go-lives pull product engineers off the roadmap. When customers sign faster than the team grows, the product plan slips one rollout at a time.
- Status lives in people's heads and a few different tools, so leaders book a meeting to find out where anything stands.

### What these bottlenecks typically cost
- Teams this size usually lose 1 to 2 days a week per product engineer to handoffs and status meetings.

### What I'd do in a 2-week Delivery Audit
1. Inventory how each team ships today: tools, pipelines, release cadence, and how much engineering time goes to new features versus fixing what's already built.
2. Put every in-flight initiative on one list with a real status and an owner, so you only need to ask one person where it stands.
3. Build a delivery playbook so your team can maintain 1 tracker with 1 weekly review.

### What I can't see from outside
- How many customer go-lives are running at once right now?
- Who do you ask today to find out where a go-live stands, and how many answers do you get?

If 70-80% of this feels right, [you can book 20 minutes here](https://calendar-link-placeholder). We'll fix what I got wrong and see if a 2-week Delivery Audit would pay for itself.
```
