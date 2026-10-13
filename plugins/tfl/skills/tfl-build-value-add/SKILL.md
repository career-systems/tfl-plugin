---
name: tfl-build-value-add
description: Workflow. The full chain for one company, from research to the send: the pre-call brief, the fit decision, the recipient, the picks, the Snapshot, the branded file, and the messages, with three member review stops. Use when the member says "build a Snapshot for [company]," "build a value-add for [company]," or picks a company off their approved list.
risk: high
---

# tfl-build-value-add

This is a **pointer skill**. It exists so members get slash completion
(`/tfl:tfl-build-value-add`) for the hosted workflow — it carries no methodology of its
own. All of the actual process, inputs, outputs, rules, and review stops live server-side
in the hosted `tfl_build_value_add` MCP tool (served by `tfl-mcp`).

## What to do

Call the hosted `tfl_build_value_add` tool and run whatever prompt it returns. Do not
paraphrase or reconstruct the workflow locally — the hosted tool is the single source of
truth for this workflow's process, and this file must never duplicate it.

## When to use

- The member says "build a Snapshot for [company]," "run the whole thing on
  [company]," or picks a company off their approved list.

## Prerequisite

`about/` must already be filled in (run `tfl-setup` first if any about file still says
"needs input" — the hosted tool's preload depends on it).
