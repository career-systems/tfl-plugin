# tfl

The Fractional Lever — workspace bootstrap + methodology skills for TFL Beta.

## What this plugin does

Installing this plugin gives a member the workspace root, `about/`, `templates/`, and
`outputs/` scaffold (all created under a named `the-fractional-life/` root — see
Deviations below), plus:

- `tfl-setup` — first-run setup, rebuilt around the **card-paste flow**: no offer
  interview. The member pastes their Fractional Offer page from their playbook word for
  word (their title, wedge, pricing, targets, and outcome), and their playbook's "How To
  Find Your Target Companies" page (their weekly search instructions), then answers a
  few short questions, and every other skill can run from it. Installs the 6 bundled
  templates (`templates/`) word for word and fills their `about/` profile files.
  Personalizes `START-HERE.md`. Safe to rerun: it fills gaps without clobbering
  populated files.
- `tfl-record-decisions` — **deprecated.** Still shipped and still works exactly as
  before — deleting it would break any member who has it wired into a habit — but its
  body now opens with a deprecation notice, and it is no longer read by any hosted
  prompt. It used to keep a local log at `about/decisions.md` of what the member had
  already decided (corrected facts, recipient choice, voice preferences, things they
  rejected). Removal is a later spec, once nobody is invoking it.
- `tfl-build-value-add` — a **pointer skill** for the hosted workflow (see below).

## Layout

```text
plugins/tfl/
  .claude-plugin/plugin.json                    # plugin manifest
  skills/tfl-setup/SKILL.md                     # first-run setup skill (verbatim)
  skills/tfl-record-decisions/SKILL.md           # deprecated local decisions log (verbatim from source)
  skills/tfl-build-value-add/SKILL.md            # pointer skill -> hosted tfl_build_value_add
  templates/                                     # the bundled templates (verbatim), incl. about-templates/
  .mcp.json                                      # TFL MCP connector, wired to the production endpoint
  .mcp.json.example                              # template showing the connector shape
```

## Connecting to the hosted TFL methodology tools

The hosted methodology tools and the hosted workflow are served over MCP. The catalog is
7 tools: `tfl_research_company`, `tfl_identify_prospect_challenges`,
`tfl_write_value_add`, `tfl_identify_decision_makers`, `tfl_format_value_add`,
`tfl_write_message`, and `tfl_build_value_add`. The plugin ships a
ready-to-use `.mcp.json` pointing at the production connector
(`https://ktazhzplyhpqayjaghur.supabase.co/functions/v1/tfl-mcp/mcp`), so installing the
plugin connects the tools automatically. The server uses OAuth — clients authorize on
first use. `.mcp.json.example` documents the config shape if you need to point at a
different endpoint.

The document `tfl_write_value_add` and `tfl_format_value_add` produce is now called the
**Snapshot**: `[Company] - [Function] Snapshot`. "Fractional" moved off the title into a
fixed from-line underneath it, and the docx filename follows the title (old files on a
member's disk keep their old names; nothing reads them back by path).

## Pointer-skill-per-workflow convention

Every hosted **workflow** (as opposed to a single methodology skill) gets a matching
plugin **pointer skill** under `skills/<workflow-name>/SKILL.md`. The pointer skill carries
no methodology of its own — its only job is to give the member slash completion (e.g.
`/tfl:tfl-build-value-add`) and tell Claude to call the hosted tool by name. The hosted
tool's server-side prompt (sourced verbatim from `forKatie/TFL Skill Repo v3.5/`)
remains the single source of truth for the workflow's process; the pointer skill must never
duplicate or paraphrase it. `tfl-build-value-add` is the first instance of this convention;
apply it to every future hosted workflow.

## Deviations from Katie's vendored v3.5 source

This plugin ships from Katie's pristine vendored source
(`forKatie/TFL Skill Repo v3.5/`), which is never edited in place. Every place
a shipped artifact differs from that source by even one character is recorded as a find/
replace entry in `tests/unit/tfl-plugin/vendor-deviations.ts` and machine-checked for
byte-equality (spec 133 D7); that ledger is the source of truth. These change how this
plugin behaves for a member:

- **D1 — workspace root stays `the-fractional-life/`.** v3.5's `tfl-setup` scaffolds at
  `Desktop/fractional-life/`. We keep `the-fractional-life/`, resolved under the folder
  the member opened, because a `Desktop/` path doesn't exist in a Cowork/cloud session
  and every hosted `fileContract` is relative to the named root.
- **D2 — `templates/` stays installed into the scaffold.** v3.5's `tfl-setup` no longer
  copies `templates/` into the member's workspace. We keep the install (all 6 files, with
  `about-templates/` intact) because `tfl_write_value_add` still reads
  `templates/value-add-template.md` by path.

- **D8 — a run refreshes the assets we own.** Katie's `tfl-setup` installs templates only
  when they're absent, so a member scaffolded by an older plugin version keeps whatever
  they were first given — and when Katie revises the methodology, they keep drafting
  against the old rules. Every run now overwrites `templates/` outright (all 6 files; they
  are ours, never the member's work) and rebuilds the house-owned sections of
  `about/tfl-voice.md` from the current template, splicing the member's
  `## My personal notes` back in word for word. Their other about files and `START-HERE.md`
  are still never overwritten. If the voice file is missing that heading on either side,
  the run leaves it alone and flags it rather than guessing at the boundary.

One entry changes what ships, not what runs: **D3** is the `tfl-record-decisions`
deprecation notice described above.

The hosted prompts carry two matching guards, recorded in the same ledger: **D4** stops the
value-add and message skills when the offer file has no `**Title:**` line (a v2-shaped card
with no wedge data), and **D9** stops them — and the `tfl_build_value_add` workflow, at its
preflight — when `about/tfl-voice.md` has no `**Idioms and insider slang:**` entry, meaning
it predates the current house standard. Both send the member to `tfl-setup`; D8 is what
makes that run repair the voice file.

## Versioning

`.claude-plugin/plugin.json` `version` is the single source of truth for the packaged release
artifact name (`tfl-plugin-v<version>.zip`, built by CI). Bump it to publish a new release.
