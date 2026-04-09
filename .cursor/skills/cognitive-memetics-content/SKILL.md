---
name: cognitive-memetics-content
description: >-
  Authors and edits Hugo posts under the cognitive-memetics section: type cows
  (cube-cows weekly) or type sayings (TLDR / Context), Street Wisdom / Venezuelan
  sayings project tags and LinkedIn hashtags, heading_code, descriptions, categories,
  and featured images. Use when editing content/cognitive-memetics/, when the user
  mentions Cognitive-Memetics, cube-cows, Office-Paddoc, Tales from the Cube Farm,
  Street Wisdom, Cultural Stopwatch, cartoon stopwatch, or Venezuelan sayings.
---

# Cognitive-Memetics section content

## What this section is

**Cognitive-Memetics** is a **Hugo section**: paths under `content/cognitive-memetics/...` (URL prefix `/cognitive-memetics/`). It is listed in **`hugo.toml`** `params.home.contentSections` so posts can appear on the home feed with other sections.

This section does **not** define a separate `type`. Posts use existing content types:

| `type` | Role | Typical use in this folder |
|--------|------|----------------------------|
| **`cows`** | Longer **cube-cows** / weekly-style pieces | Essay body; optional `heading_code` (week **W6**, **W7**); optional **`project`** (series label) + unique **`title`** (episode name) |
| **`sayings`** | Short **saying** entries with TLDR + Context | `tldr` and `fluff`; optional `heading_code`; optional **`project`** (series line) + unique **`title`** (episode name), same hero pattern as **`cows`** |

For **`type: claims`** (Claim / Thoughts / Grounding), use **`.cursor/skills/claims-content/SKILL.md`** and a section such as `reality-protocols`, not this skill.

## Authoring rules (site-wide)

- MUST follow **`.cursor/rules/content-markdown-writing.mdc`** for English, punctuation, and markdown habits.
- MUST keep code, identifiers, and user-facing strings in **English** (see workspace AI protocol).

## Front matter conventions

### Shared

- **`date`**, **`title`**, **`draft`**
- **`heading_code`** (optional): short label before the title (e.g. `W6`, `W13`). Rendered via `layouts/partials/heading-title-markup.html` with class `heading-code--tldr`.
- **`categories`**: Use **two** terms so each post belongs to the section **and** to a **project hub** you can link to (Hugo taxonomy list pages under `/categories/<slug>/`).
  - **Umbrella:** always **`Cognitive-Memetics`** (this site area).
  - **Project (pick one):** **`Office-Paddoc`** for **`type: cows`** (the **Tales from the Cube Farm** series; short category label for a shareable hub). **`Venezuelan-Street-Wisdom`** for **Street Wisdom** **`type: sayings`** posts.
  Example YAML:

  ```yaml
  categories: ["Cognitive-Memetics", "Office-Paddoc"]   # type: cows (cube-cow / Cube Farm posts)
  ```

  ```yaml
  categories: ["Cognitive-Memetics", "Venezuelan-Street-Wisdom"]       # Street Wisdom sayings
  ```

  Hugo flattens categories (no true parent/child in core), but two terms give a **shareable URL** for “everything in this project” while the section path still scopes content by folder.
- **`tags`**: Punchy **PascalCase** hooks (no placeholder terms). Prefer three to five tags; see **`content/cognitive-memetics/`** examples. Align with **`.cursor/skills/claims-content/SKILL.md`** *Tag voice* for shape and reuse, but topics here are cube-cows, sayings, and culture notes—not Claim/Grounding jargon unless you intend it.
- **`resources`** with `name: "featured-image"` and `src: "filename.ext"` for the card / detail hero image (put the file in the page bundle).

### `type: cows`

- **`description`**: Teaser for cards / list column; on the **detail** page it becomes the **Teaser** block before the main article (markdownified), with merged **Contents** when the body has headings.
- **`project`** (optional but recommended for **Tales from the Cube Farm**): The recurring **series line** on the detail hero (e.g. `Cube-Cows 🐮📈`). **`title`** must be a **unique episode name** (lists, prev/next links, browser tab). Without `project`, the layout falls back to `heading_code` + `title` everywhere (legacy one-line titles).
- Body markdown below `<!--more-->` is the main article (`layouts/cows/single.html`).

Archetype: **`archetypes/cows.md`**.

#### Tales from the Cube Farm (why cube-cows exist)

The **category** for these posts is **`Office-Paddoc`** (paddock for office “cattle”). The **series name** in copy stays **Tales from the Cube Farm**.

**`type: cows`** posts in this section are part of **Tales from the Cube Farm**: an informal experiment that counts how many of these pieces ship **before robots read as just another ordinary coworker**. Think of it as a **cartoon stopwatch** on the end of the “human-as-robot” office era.

The wider point: workplaces trained people to be efficient, compliant office machines long before real machines could replace them. The series uses **AI-generated cow-workers** to surface how **domesticated** office life has become, and to ask—lightly—whether humans might reclaim a bit of **wild individuality** before the real robots fully move in.

**Tags for `cows`:** Always include **`CubeCows`**. Add **recurring theme** tags when the joke fits (for example **`AGIHype`** when the strip is about AI hype). Add **one or two episode-specific** tags for that week’s punchline; do not force-reuse narrow joke tags across unrelated weeks.

### `type: sayings`

- **`description`**: Short teaser for cards.
- **`tldr`**: Main “TLDR” block (shown in list and on the single layout).
- **`fluff`**: “Context” block (optional second column on list; shown on single).
- **`project`** (optional): Recurring **series line** on the detail hero (e.g. **Arepa-Contigo** for posts under the **Venezuelan-Street-Wisdom** hub). **`title`** should be the **unique** episode name (Spanish saying, etc.) for lists, prev/next, and the tab. Without `project`, the layout uses one-line `heading_code` + `title` everywhere.

Archetype: **`archetypes/sayings.md`**.

### Street Wisdom (Venezuelan sayings sub-series)

Some **`type: sayings`** posts translate **Venezuelan street wisdom** for an English audience. They usually use **`categories`**: **`Cognitive-Memetics`** and **`Venezuelan-Street-Wisdom`** (shareable hub aligned with the series). For the detail hero, use **`project: Arepa-Contigo`** so the series line matches the **Arepa-Contigo** tag and social framing.

**Project framing (for editors, intros, or social copy):** This is an informal experiment: track how many Venezuelan sayings get translated while a political era runs its course, like a **cultural stopwatch**. Where American culture is often exported and adopted worldwide, these posts **export back** Venezuelan street wisdom as a small contribution to a more balanced cultural exchange.

**LinkedIn hashtags** (use on LinkedIn with `#`; in Hugo front matter use **PascalCase** and **no** `#` character):

| LinkedIn | Hugo `tags` value |
|----------|-------------------|
| `#StreetWisdom` | `StreetWisdom` |
| `#CulturalStopwatch` | `CulturalStopwatch` |
| `#TakeBackYourMcDonaldsCulture` | `TakeBackYourMcDonaldsCulture` |
| `#Arepa-Contigo` | `Arepa-Contigo` |

For Venezuelan saying posts, **include those four tags** when promoting the series, plus **`VenezuelanSayings`** and optional **post-specific** tags (one or two hooks for that saying). Keep total tags roughly **five to seven** if you add both series tags and a hook.

## Layouts and list UI

- Singles: **`layouts/cows/single.html`**, **`layouts/sayings/single.html`**
- Section / home rows: **`layouts/partials/seven-style-row.html`** (claims vs sayings vs default teaser columns)

### Detail singles (parity with reality-protocols / `type: claims`)

Single pages for **`cows`** and **`sayings`** follow the same UX pattern as **`layouts/claims/single.html`**:

- **`tags`**: Shown **under the featured image** (not duplicated in the article footer). Footer tag list is suppressed for these types via **`layouts/partials/single/footer.html`**.
- **`type: cows`**: Main content is the markdown body. When **`description`** is set, the detail page renders **Teaser** (`#section-teaser`) then **Article** (`#section-essay`) for the markdown body, with merged **Contents** via **`layouts/partials/cows-table-of-contents.html`** (same idea as sayings). With **`project`** set, the detail **h1** uses **`heading-series-single.html`**; lists use **`heading-series-list.html`** (via **`heading-title-markup.html`**).
- **`type: sayings`**: Same **`project`** / **`title`** split as **`cows`** when **`project`** is set (shared **`heading-series-*.html`** partials). Additionally:
  - **Teaser** (`description`), **TLDR** (`tldr`), and **Context** (`fluff`) are rendered as sections with stable anchors **`#section-teaser`**, **`#section-tldr`**, **`#section-context`** when present. Front-matter strings are **markdownified** like claims `description`.
  - If any of those blocks exist **and** the post has a non-empty body, the main markdown is introduced by an **Article** section with anchor **`#section-essay`** (i18n key **`sayingsArticle`**).
  - **Contents** is a **merged** nav: **`layouts/partials/sayings-table-of-contents.html`** combines Teaser / TLDR / Context links with body heading links from the built TOC; when Article wraps the body, in-body heading links nest under **Article** (same idea as **Thoughts** nesting on claims).

For **`type: claims`** (Claim / Thoughts / Grounding), authoring rules stay in **`.cursor/skills/claims-content/SKILL.md`**.

## Bundle layout

Use one folder per post with **`index.md`** and assets beside it, for example:

`content/cognitive-memetics/2006-04-02-cow-w06/index.md` + `agi.png`

## Theme and style

- Site overrides: **`assets/css/_custom.scss`** (prefer not editing `themes/LoveIt/`).
- LoveIt how-tos: **`themes/LoveIt/exampleSite/content/posts/`** (see **`.cursor/rules/always-rules-3-hugo.mdc`** index).

## References in this repo

- **`hugo.toml`**: menu entry and `contentSections` for the home feed.
- Examples: **`content/cognitive-memetics/2006-04-02-cow-w06/`** (`type: cows`), **`content/cognitive-memetics/2006-04-06-saying-13/`** (`type: sayings`).
