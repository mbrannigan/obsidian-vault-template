# Vault Structure Guide

*Created: 2026-04-16*

## The Big Picture

The vault uses a simplified PARA-inspired structure. Everything has a home based on what kind of thing it is, not what topic it's about.

| Folder | What goes here |
|--------|----------------|
| `Areas/` | Ongoing responsibilities with no end date (flat, one note per area) |
| `Resources/` | Reference notes on topics, books, articles, concepts (flat) |
| `Projects/` | Active work with a defined outcome (folder per project) |
| `Learning/` | In-progress learning — courses, books, structured study |
| `Daily/` | Daily notes |
| `Documents/` | One-off reference docs (like this one) |
| `Templates/` | Note templates |

---

## What is an Area?

An Area is the answer to "what part of my work is this?"

Each area is a **single note** in `Areas/`. It's an index card, not a filing cabinet — it captures purpose, standards, and links out to related projects and resources.

The actual work product (projects, docs, meeting notes) lives in its proper top-level home and **links back** to the area.

**Example: Observability**

```
Areas/Observability.md            <- single area note, links out

Projects/TracingRollout/          <- links back to [[Observability]]
Resources/OpenTelemetry.md        <- links back to [[Observability]]
```

If an area starts accumulating a lot of working notes that don't belong anywhere else, it can graduate to a folder. The index note stays; the folder holds area-specific working material.

**Example after graduating:**
```
Areas/Python/
├── Python.md          <- area index, unchanged
├── Build Tools.md     <- working notes internal to this area
└── Security Scanning.md
```

Resources linked from an area always stay flat in `Resources/` — they don't move into the area folder.

---

## What is a Resource?

A flat reference note on a single topic, book, article, or concept. Lives directly in `Resources/` — no subfolders.

Good candidates: books you've read, articles worth keeping, frameworks, concepts, tools.

**Resources use `#Type/` tags** to describe what kind of note they are (`#Type/clipping`, `#Type/book`, `#Type/tool`, `#Type/concept`, `#Type/reference`). See `[[Tags]]` for the full taxonomy.

---

## What is a Project?

Active work with a defined outcome and an eventual end. Each project gets its own folder under `Projects/`. When done, move it to an archive.

---

## What is Learning?

In-progress structured learning — courses, books being actively read, platforms like Codecademy, Coursera, HackTheBox, or AI-generated curricula.

Each learning effort gets a folder under `Learning/` with an index and running notes. When you're done, the knowledge worth keeping graduates to `Resources/` as a permanent reference note. The `Learning/` folder is the workspace; `Resources/` is what survives it.

**Learning sources and where they go:**

| Source | Where |
|---|---|
| Coursera, Codecademy, HackTheBox | `Learning/<Course>/` folder |
| AI-generated course | `Learning/<Topic>/` folder |
| Book (active reading) | `Learning/<Book Title>/` folder |
| YouTube video (one-off) | `Resources/` clipping directly |
| Article / tutorial | `Resources/` clipping directly |

**Standard learning folder structure:**
```
Learning/<Course or Book>/
├── Index.md     <- what it is, why you're doing it, status, links to resources produced
└── Notes.md     <- running notes as you go through it
```

When finished: distilled notes graduate to a `Resources/` note. The `Learning/` folder can be archived or deleted.

---

## The Key Mental Model

- **Area** = a responsibility you maintain indefinitely (single note)
- **Project** = a finite piece of work under an area (folder)
- **Resource** = reference material that informs one or more areas (single note)
- **Learning** = in-progress study workspace (folder); graduates to Resources when done
- **Document** = a one-off reference doc that doesn't fit the above

When you're unsure where something goes, ask: *is this a thing I'm doing (project), a responsibility I'm maintaining (area), something I want to reference later (resource), or something I'm actively learning right now (learning)?*

---

## Tags vs. Wikilinks — How They Divide the Work

| Use | For | Example |
|---|---|---|
| **Tags** | Operational classification — what is it, what area owns it, what's its status | `#Type/clipping`, `#Area/Python`, `#Status/Focus` |
| **Wikilinks** | Topical connections — what is it about, what relates to it | `[[Pandas]]`, `[[Observability]]` |

**Don't create tags for topics.** If you clip an article about Kafka, don't tag it `#kafka`. Instead, link to `[[Kafka]]` in the note body.

**`#Type/` and `#Area/` stack naturally.** A Pandas article is both `#Type/clipping` (what it is) and `#Area/Python` (what responsibility it informs).

**Example: capturing an article**
```
---
tags:
  - resource
  - "#Type/clipping"
  - "#Area/Observability"
source: https://...
created: 2026-04-16
---

# How OpenTelemetry handles context propagation

## Related Areas
- [[Observability]]

## Links
- [[OpenTelemetry]]
```

---

## Linking Convention

- Area notes link out to related Projects and Resources
- Project and Resource notes link back to their Area
- Learning index notes link to the Resource note produced when finished
