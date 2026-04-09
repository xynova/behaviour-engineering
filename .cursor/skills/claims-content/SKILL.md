---
name: claims-content
description: >-
  Authors and edits Hugo posts with type claims: Claim (description), Grounding,
  section vs categories vs punchy hashtag-like tags, optional primary-source quote
  blocks (`###` heading + blockquote), and prose style.
  Use when editing or adding content under reality-protocols (or other sections
  using claims), when the user mentions Claim, Grounding, categories, tags, or
  claims archetype, or when shaping list-view copy for those posts.
---

# Claims content type (`type: claims`)

## What this type is for

Posts use front matter fields that split **narrative** from **intellectual anchor**. The **list view** (cards, summaries) leans heavily on **title**, **`description`**, and **`grounding`**; polish those before spending time on body-only formatting.

## Field roles

| Field | Role |
|-------|------|
| **`description`** | **Claim**: the narrative assertion in your voice. What the reader should believe or notice. Often shown as the **Claim** block in the UI. |
| **Body** (markdown under front matter) | **Thoughts** on the detail page: essay, metaphor, examples, optional **primary-source quote** section. Rendered **after** Claim, **before** Grounding. |
| **`grounding`** | **Support for the Claim**: definitions, named constructs, dates, and **links** (paper, overview) so the Claim is tied to sources or standard terminology. Not a duplicate of the full article. |

**Relationship:** Grounding **supports** the Claim. The Claim says *what you are arguing in plain language*; Grounding says *what ideas or citations that maps onto*.

**Detail page order** (`layouts/claims/single.html`): **Claim** → **Thoughts** (body) → **Grounding** → optional **Research** (`research` front matter).

## Section, categories, and tags (Hugo)

- **Section** comes from the **content path** (for example `content/reality-protocols/...` → section `reality-protocols`). It is not set by `categories`.
- **`categories`** are a **taxonomy**: optional labels for grouping and taxonomy pages. They do not have to mirror the folder name.
- If **`categories`** is omitted, list partials in this project can fall back to the **section** name for display; if set, the **first** category is often what themes show in list meta—check `layouts/partials/seven-style-row.html` when in doubt.
- Hugo **categories** are **flat** (no built-in parent/child). Use **tags** for hooks and subtopics (see **Tag voice** below).
- **Recommendation:** one **primary category** aligned with the main site area (for example `Reality-Protocols` for posts under `reality-protocols/`), and **several tags** for topic detail. Add a second category only if you need another taxonomy axis and accept how the theme surfaces the first term.

### Tag voice (punchy, hashtag-like)

- **Purpose:** Tags carry **attitude, provocation, and memory**. They are **not** a second abstract: do **not** lift jargon from **Grounding** (for example paper constructs) into tags unless you want that label on purpose.
- **Prefer:** questions, tribal / social stakes, irony about fads, time and attention (`SameButDifferentWorlds`, `DoYouHaveATribe`, `GoBackToOfficeFad`, `TimeThatCounts`, `RealityCheck`, `KnowYourPolitics`). Do not stack two tags that ask the same question (for example drop one of two near-duplicate tribe hooks).
- **Draft in your head as hashtags**, then put them in front matter **without** the `#` character (YAML and Hugo taxonomy terms work better as plain strings; the theme shows them as tag titles).
- **Shape:** Compact **PascalCase** fused phrases; readable aloud like a bumper sticker.
- **Count:** Aim for roughly **three to five** tags per post; quality over volume.
- **No repetition:** Each tag must add a **different** angle (provocation, target, or question). Do **not** use two tags that restate the same idea in different words, and do **not** repeat a hook you already used on another post unless you mean a running theme. If two tags feel like one joke twice, delete one.
- **Reusability:** Prefer tags that can **show up again** when another post hits the same theme (a recurring series or the same fault line in the wild). Avoid one-off in-jokes unless that is the point. If a phrase only fits a single paragraph in a single article, it is usually too narrow for a tag.
- **Example** (savings, sovereign debt, moral cost of funding):

  ```yaml
  tags: ["RealityCheck", "KnowYourPolitics", "ThinkHardThisTime"]
  ```

- **Example** (sync, tribe, real time vs performative togetherness):

  ```yaml
  tags: ["SameButDifferentWorlds", "DoYouHaveATribe", "GoBackToOfficeFad", "TimeThatCounts"]
  ```

- **Example** (culture, identity, illusion as infrastructure; tags reusable across posts):

  ```yaml
  tags: ["SharedIllusionsRunTheWorld", "IdeasBecomeIdentity", "TribeBeforeTruth"]
  ```

## Grounding (how to write it)

- **Density:** Similar to a short abstract plus pointers: enough to define key terms (bold) and point to a primary source or stable overview link.
- **Not the same as** an optional **quote exhibit** in the body: Grounding is the **digest**; a blockquote under a small heading is the **exhibit** (exact words). Grounding can be broader than one quote; the quote is optional and narrow.
- **Etymology vs theory:** For coinages (e.g. *meme*), etymology + year + overview link fits. For theory papers, state the **construct** (e.g. shared reality, epistemic companions), what the cited work does, then **Source:** link (mark `(PDF)` when it is a PDF).

## Optional body convention: primary-source quote (“What he said”)

- Use a **`###`** subsection (with an emoji, same style as other **Thoughts** headings), then the blockquote. Example: `### 💬 What he said`. That gives a heading id, **Contents** entry (nested under **Thoughts**), and anchors consistent with the rest of the outline. Do **not** use a plain **`[WHAT HE SAID]`** line; that was legacy markup, not a project convention.
- Use when a **long primary-source quotation** earns its space. Omit if Grounding + prose are enough.

## Prose style (project preference)

- **Avoid em dashes (`—`).** Prefer commas, semicolons, colons, or parentheses.
- **English only** for site content (paths, front matter strings, body copy).

## Authoring workflow

1. Draft **`description`** (Claim) so it reads well alone on a card.
2. Draft **`grounding`** so it names constructs and citations that anchor the Claim.
3. Write the body (metaphor, examples, optional quote exhibit with a `###` heading before the blockquote).
4. Re-read Claim, then body as **Thoughts**, then Grounding for alignment (same order as the live page).

## References in this repo

- Archetype: `archetypes/claims.md` (TOML; content bundles may use YAML with the same fields; legacy **`paper`** may still work for grounding-style content).
- Examples: `content/reality-protocols/2026-04-01-memes/index.md` (coinage + quote exhibit), `content/reality-protocols/2026-04-03-shared-reality/index.md` (theory + PDF source).
