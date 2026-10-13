# tfl

The Fractional Lever — workspace bootstrap + methodology skills for TFL Beta.

**Version 0.7.0 is TFL v4** (our numbering; Katie's side calls this drop "v3"). It is a
breaking, member-facing release.

**Update the plugin, then rerun `tfl-setup`.** A plugin update alone changes nothing in your
folder. Your `templates/` and `rules/` are refreshed, and your Messages tab is captured,
only when you rerun `tfl-setup` on 0.7.0.

## What this plugin does

Installing this plugin gives a member the workspace root, `about/`, `templates/`, `rules/`
and `outputs/` scaffold (all created under a named `the-fractional-life/` root — see
Deviations below), plus:

- `tfl-setup` — first-run setup, built around the **card-paste flow**: no offer
  interview. The member pastes their Fractional Offer page from their playbook word for
  word, including the Snapshot Kit, the Messages tab, and their playbook's "How To Find
  Your Target Companies" page, then answers a few short questions. Installs the bundled
  templates (`templates/`) and the review rubric (`rules/`) word for word and fills their
  `about/` profile files. Personalizes `START-HERE.md`. Safe to rerun: it fills gaps without
  clobbering populated files.
- `tfl-record-decisions` — **deprecated.** Still shipped and still works exactly as
  before — deleting it would break any member who has it wired into a habit — but its
  body now opens with a deprecation notice, and it is no longer read by any hosted
  prompt. Removal is a later spec, once nobody is invoking it.
- `tfl-build-value-add` — a **pointer skill** for the hosted workflow (see below).

## What a Snapshot run looks like in v4

"Build a Snapshot for [company]" runs the hosted `tfl_build_value_add` workflow:

1. **The brief.** Research lands as a pre-call brief in `outputs/company-briefs/`, replacing
   the old company profile. Old `outputs/company-profiles/` work is not read by v4.
2. **The kit and the Messages tab.** The Snapshot is built from the member's Snapshot Kit
   (the `## Snapshot Kit` section of `about/tfl-fractional-offer.md`), and the messages from
   the Messages tab pasted into `about/tfl-messages.md`.
3. **The one-page Snapshot.** The page is written from the kit's lines; `[Function]` comes
   from the kit's `**Snapshot name:**` line, and the file is `[Company] - [Function]
   Snapshot.docx`. A placeholder or missing booking link holds the page with no docx.
4. **The review at stop 2.** The page is shown, then `tfl_review_value_add` checks the
   page's kit lines against the kit and the page is graded against Katie's rubric. The
   review is a report: it never blocks "send it".

Katie's rubric ships under `rules/value-add-review-rubric.md`. It is Katie's text, with the
member names scrubbed (D12).

Two named stops protect members who are not yet on v4:

- **D10 — no kit, no Snapshot.** If the offer file has no Snapshot Kit, the workflow stops
  with a message to update the plugin and rerun `tfl-setup`. It never makes up a kit.
- **D11 — no Messages tab, no messages.** If `about/tfl-messages.md` is missing, the
  message step and the workflow stop the same way.

Research, recipient-finding and "find me companies" keep working without a kit.

## Layout

```text
plugins/tfl/
  .claude-plugin/plugin.json                    # plugin manifest
  skills/tfl-setup/SKILL.md                     # first-run setup skill
  skills/tfl-record-decisions/SKILL.md           # deprecated local decisions log
  skills/tfl-build-value-add/SKILL.md            # pointer skill -> hosted tfl_build_value_add
  templates/                                     # the bundled templates, incl. about-templates/
  rules/value-add-review-rubric.md               # Katie's review rubric, read at stop 2
  .mcp.json                                      # TFL MCP connector, wired to the production endpoint
  .mcp.json.example                              # template showing the connector shape
```

## Connecting to the hosted TFL methodology tools

The hosted methodology tools and the hosted workflow are served over MCP. The catalog is
10 tools: `tfl_research_company`, `tfl_identify_prospect_challenges`,
`tfl_write_value_add`, `tfl_identify_decision_makers`, `tfl_format_value_add`,
`tfl_write_message`, `tfl_build_value_add`, `tfl_find_companies`,
`tfl_review_value_add`, and `tfl_value_add_create_docx`. The plugin ships a ready-to-use `.mcp.json` pointing at the
production connector
(`https://ktazhzplyhpqayjaghur.supabase.co/functions/v1/tfl-mcp/mcp`), so installing the
plugin connects the tools automatically. The server uses OAuth — clients authorize on
first use. `.mcp.json.example` documents the config shape if you need to point at a
different endpoint.

`tfl_review_value_add` takes the page and the kit and returns the kit-line check ("all kit
lines identical", or the lines that differ by one character or more). The server logs only
lengths and counts, never the page or the kit.

`tfl_value_add_create_docx` takes the finished Snapshot page (and, optionally, up to two
brand colors) and renders the one-page Word file on the server. It returns `ok` with a
download link that works for one hour, `hold` with the reasons the page cannot be rendered,
or `not_enabled` for members who are not on the server render yet. It sits behind its own
`tfl-snapshot-docx` flag, and the server logs only codes and counts, never the page, the
link, the filename or the colors.

## Pointer-skill-per-workflow convention

Every hosted **workflow** (as opposed to a single methodology skill) gets a matching
plugin **pointer skill** under `skills/<workflow-name>/SKILL.md`. The pointer skill carries
no methodology of its own — its only job is to give the member slash completion (e.g.
`/tfl:tfl-build-value-add`) and tell Claude to call the hosted tool by name. The hosted
tool's server-side prompt (sourced verbatim from `forKatie/TFL Skill Repo v4/`)
remains the single source of truth for the workflow's process; the pointer skill must never
duplicate or paraphrase it. `tfl-build-value-add` is the first instance of this convention;
apply it to every future hosted workflow.

## Deviations from Katie's vendored v4 source

This plugin ships from Katie's pristine vendored source
(`forKatie/TFL Skill Repo v4/`), which is never edited in place. Every place
a shipped artifact differs from that source by even one character is recorded as a find/
replace entry in `tests/unit/tfl-plugin/vendor-deviations.ts` and machine-checked for
byte-equality (spec 133 D7); that ledger, closed at 23 entries, is the source of truth.
These change how this plugin behaves for a member:

- **D1 — workspace root stays `the-fractional-life/`.** v4's `tfl-setup` names no path. We
  insert the `the-fractional-life/` root, resolved under the folder the member opened,
  because a `Desktop/` path doesn't exist in a Cowork/cloud session and every hosted
  `fileContract` is relative to the named root.
- **D2 — `templates/` stays installed into the scaffold, and `rules/` joins it.** We keep
  the install (with `about-templates/` intact) because the hosted prompts read
  `templates/value-add-template.md` and `rules/value-add-review-rubric.md` by path.
- **D3 — `tfl-record-decisions` is deprecated in place.** It gains a deprecation notice and
  is no longer read by any hosted prompt.
- **D8 — a run refreshes the assets we own.** Every `tfl-setup` run overwrites `templates/`
  and `rules/` outright (they are ours, never the member's work) and rebuilds the
  house-owned sections of `about/tfl-voice.md` from the current template, splicing the
  member's `## My personal notes` back in word for word. Their other about files and
  `START-HERE.md` are still never overwritten. If the voice file is missing that heading on
  either side, the run leaves it alone and flags it rather than guessing at the boundary.
- **D9 — stale-voice stop.** Research, the page writer and the build workflow stop when
  `about/tfl-voice.md` has no `**Idioms and insider slang:**` entry, meaning it predates the
  current house standard. They send the member to `tfl-setup`; D8 is what makes that run
  repair the voice file.
- **D10 — no kit, no Snapshot** (see above). Added to the prospect-challenges picker, the
  page writer and the workflow preflight.
- **D11 — no Messages tab, no messages** (see above). Added to the message writer and the
  workflow preflight.
- **D12 — member names are scrubbed from shipped artifacts.** The template, the picker and
  page-writer prompts, and the shipped rubric (four entries) use synthetic names or card
  titles. Nothing under `plugins/` names a member.
- **D13 — a review step at stop 2.** Step 7 of the workflow gains the review through
  `tfl_review_value_add` and the shipped rubric. It reports only and never holds the page.

D4 (the Title-line guard) is retired: a v2-shaped card has no kit, so D10 catches it.

## Versioning

`.claude-plugin/plugin.json` `version` is the single source of truth for the packaged release
artifact name (`tfl-plugin-v<version>.zip`, built by CI). Bump it to publish a new release.
The release is published by pushing the `tfl-plugin-v0.7.0` tag, which the owner does after
the `tfl-mcp` deploy, never before.
