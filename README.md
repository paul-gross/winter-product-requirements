# ❄️ winter-product-requirements

The **Product Requirements Framework**: a [winter](https://github.com/paul-gross/winter) extension of rules for the
product side of a requirements repo — the charter, personas and jobs, initiatives, epics and milestones, product
requirements, product decisions, and mockups — so product intent stays findable, citable, and readable by anyone who
opens the repo.

📚 **Documentation:** <https://paul-gross.github.io/winter-docs/>

## ✨ Features

- **Charter** — mission, vision, and the persona and job registries every epic answers to.
- **Epics and initiatives** — one folder per epic under `work/`, optionally grouped by initiative, with the registries
  that list them and a `delivered/` archive once they finish.
- **Product requirements** — one record per `product:` id, each with acceptance bullets, kept apart from what
  engineering commits to.
- **Stable, citable ids** — `persona:`, `job:`, `initiative:`, `epic:`, `product:`, `milestone:`, and `decision:` ids
  built from slugs, never numbers, each with one canonical home.
- **Decisions** — open until the call is made, with clarifying questions inline at the end of the file they concern.
- **Mockups** — the kit a repo supplies, how mockups are authored, and how they are published.
- **Product voice** — the voice product intent is written in, and the tells it avoids.
- **Delivering an epic** — a workflow for marking an epic delivered and archiving its folder.

## 🚀 Installation

Add to the workspace's `.winter/config.toml`:

```toml
[[standalone_repository]]
name = "winter-product-requirements"
url = "git@github.com:paul-gross/winter-product-requirements.git"
path = ".winter/ext/product-requirements"
```

Then run `winter ws init`.

## 🧩 How it works

A requirements repo holds content only, organized by product work: one folder per epic under `work/`, optionally grouped
by initiative, moving to `delivered/` once finished, with program-wide files at the root. This framework governs the
product-owned files — the charter, the registries, each folder's `epic.md` or `initiative.md`, `requirements.md`, and
`mockups/` — and the product entries in the files both frameworks share: what each holds, how product ids are minted and
kept stable, how decisions are recorded open or made, where clarifying questions sit, and the voice product intent is
written in. Where the framework cannot supply something — a README, a charter, a mockup kit — it states what the repo's
own version must contain.

The framework stays out of the content. A conforming repo carries no rule text, agent instructions, or tooling
references; its README explains its own ids and statuses, so the content reads correctly without this repo at hand.

Product intent does not have to live in git. A repo may keep some or all of it in a work tracker or wiki and declare
where each kind of id lives; the framework then governs only the product files the repo holds.

Agents working in the workspace load the framework on demand through [`index.md`](./index.md) and cite its rules as
`preq:<slug>`.

## 🎯 Scope

The product side only. The engineering side of the same or another repo — engineering requirements, assumptions, specs,
and slices — is the [Engineering Requirements Framework](https://github.com/paul-gross/winter-engineering-requirements),
an optional companion. Each stands alone; neither requires the other. Both carry the same layout rule, so their files
sit side by side in one work folder.

## 🏔️ Adopting it in a requirements repo

1. In the requirements repo, add the README sections that [`repository-entry.md`](./context/repository-entry.md)
   requires.
2. Add the required root files — `charter/`, `epics.md`, `milestones.md`, `delivered.md` — and a folder under `work/`
   per epic, with its `epic.md`, in the change that names the epic, following the lifecycle in
   [`contributing.md`](./context/contributing.md).

## 🗂️ Files

| File                                                                     | Covers                                                                                                                       |
| ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| [`index.md`](./index.md)                                                 | Extension entry point; when to read the routing hub                                                                          |
| [`context/index.md`](./context/index.md)                                 | Agent routing hub                                                                                                            |
| [`repository-entry.md`](./context/repository-entry.md)                   | The README sections a repo must carry; external homes                                                                        |
| [`namespaces.md`](./context/namespaces.md)                               | Product id prefixes, slugs, stability, scopes, citation, and the engineering ids product never cites                         |
| [`layout.md`](./context/layout.md)                                       | The shared `work/` layout, file ownership, file-or-folder, front doors, epics planned in a tracker, the `delivered/` archive |
| [`structure.md`](./context/structure.md)                                 | Product areas, admission, placement, changing in place, what is deliberately absent                                          |
| [`charter.md`](./context/charter.md)                                     | Mission, vision, persona and job registries                                                                                  |
| [`registries.md`](./context/registries.md)                               | Shapes of `initiatives.md`, `epics.md`, `milestones.md`, `delivered.md`                                                      |
| [`intent.md`](./context/intent.md)                                       | Epic or initiative; `epic.md` and `initiative.md`, their frontmatter, epic status and refinement, sections                   |
| [`requirements.md`](./context/requirements.md)                           | Product vs engineering requirements; requirement records, acceptance, requirement files                                      |
| [`decisions.md`](./context/decisions.md)                                 | The bar for a decision; open and made decisions; inline clarifying questions                                                 |
| [`voice.md`](./context/voice.md)                                         | The voice product intent is written in, and the tells it avoids                                                              |
| [`mockups.md`](./context/mockups.md)                                     | Mockup kit, authoring, publishing                                                                                            |
| [`contributing.md`](./context/contributing.md)                           | The lifecycle from idea to delivered, commit messages, checklists                                                            |
| [`workflows/deliver-an-epic.md`](./context/workflows/deliver-an-epic.md) | The steps for delivering and archiving an epic                                                                               |

## License

Source-available under the Functional Source License 1.1 (FSL-1.1-ALv2). Each release converts to Apache License 2.0 two
years after it ships. See LICENSE.
