---
name: video-content
description: >-
  Authors and edits Hugo posts with type video: YouTube embed via youtube_id or
  body shortcode, description as lead, categories (often Mind-Infrastructure or
  Human-Condition), tags, optional featured image for cards, and compressed
  pitch when trimming long notes. Use when editing or adding video picks, when
  the user mentions type video, youtube_id, video archetype, curated videos, or
  compressing chapter notes into a short page.
---

# Video content type (`type: video`)

## What this type is for

**Video** posts highlight **worth-watching YouTube videos**: a short pitch, the embed, and **body copy** with your take (why it matters, how it connects, caveats).

**UI (this repo):** `layouts/video/single.html` renders **title** → **subtitle** (optional) → **meta** → **featured image** only if there is **no** `youtube_id` → **tags** → optional **TOC** → **lead** (see below) → **embed** (when `youtube_id` set) → **body**.

**Lead on the single (order):** If **`sowhat`** is set, **`description`** is shown under the fixed heading **“What you probably do not know yet”** (🎬), then **`sowhat`** under **“What you will have after”** (🎯). If **`sowhat`** is omitted, **`description`** has no extra heading above it. Both fields are markdownified.

**Section list rows** (`layouts/partials/seven-style-row.html`): **Left column** — same **YouTube** embed as on the single (not a still), then a pill link to the post using **`{{ T "fullPost" }}`** (English string in **`i18n/en.toml`**, e.g. “Read the article”; the iframe is not a link to the single). **Right column** — same **`description`** / optional **`sowhat`** copy as on the single, with the same **“What you probably do not know yet”** / **“What you will have after”** labels (fixed in the partial). Styling hooks: **`assets/css/_custom.scss`** (`.seven-list__figure--video`, `.seven-list__video-embed`, `.seven-list__video-detail-link`).

## Field roles

| Field | Role |
|-------|------|
| **`type`** | Must be **`video`**. |
| **`description`** | **Lead** above the player: why the reader should watch (one tight paragraph, bullets, or a few lines). On the **single**, shown before the embed; with **`sowhat`**, it appears under **“What you probably do not know yet.”** Also drives the **list row** aside. |
| **`sowhat`** | Optional **payoff** after the teaser: one short paragraph on what the viewer gains (overarching value). Rendered after **`description`** on single and list; when set, the single adds the **“What you will have after”** heading above **`description`** is paired with **“What you probably do not know yet.”** Use with **`description`** for the split teaser/payoff pattern. |
| **`youtube_id`** | The id from `https://www.youtube.com/watch?v=THIS` (or the `v=` value in a short URL). The layout injects Hugo’s **`youtube`** shortcode into **`.video-page__embed`**. Alias front matter key **`youtube`** is accepted. |
| **Body** | Commentary **below** the embed: reaction, context, links, headings. Use normal Markdown. |
| **`subtitle`** | Optional second line under the title. |
| **`categories`** | Taxonomy hubs. Often **`Mind-Infrastructure`** and **`Human-Condition`** for this site; pick what matches the post (see other posts in that section). |
| **`tags`** | Punchy hooks; align with **`.cursor/skills/claims-content/SKILL.md`** *Tag voice* for shape (PascalCase, reusable, no duplicates). |
| **`resources` / featured image** | Optional **`featured-image`** in the bundle for **cards and social previews**. If **`youtube_id`** is set, the **large hero image is hidden** on the single page so the page is not image + player; the resource can still help list thumbnails depending on theme partials—keep it if you want a strong card. |

## Embed: one source of truth

- **Preferred:** set **`youtube_id`** in front matter and put **only** commentary in the **body** (no duplicate `{{< youtube >}}` in the body).
- **Alternative:** omit **`youtube_id`** and place **`{{< youtube VIDEO_ID >}}`** in the **body** where you want it (still responsive; no `.video-page__embed` wrapper unless you add your own markup).

Do **not** set **`youtube_id`** **and** repeat the same id in a body shortcode (double embed).

## Compressed pitch (long notes → short page)

Use this when you have **long outlines**, chapter-by-chapter notes, or a dense talk and want a **short, impactful** page that explains what is **unusually good** about the video and nudges people to **watch** (not a syllabus).

**Division of labor**

| Part | Role |
|------|------|
| **`description`** | **Teaser / Hooks:** what is **non-obvious** or hard to get without watching. MUST use an educational, active, and accessible tone. Use a bulleted list for concrete, surprising hooks. Explain concepts simply; do not just drop jargon. MUST read well alone in **list and card** views. |
| **`sowhat`** | **Payoff:** A short summary of the overarching value (e.g., "A clear picture of how..."). Rendered below the teaser in list and single views. |
| **Body** | **Optional** depth **below** the embed: a short reaction, **at most three** concrete hooks (named ideas, not a full outline), or **one** optional “if you only have *N* minutes” block with a **single** `t=` link. The **video** is the deep layer; do not reproduce the lecture in text. Keep sections short, use active voice, and use concrete analogies to explain abstract concepts. Quotes from the speaker can be used as punctuation marks for the paragraphs above them. |

**MUST**

- Keep the **lead** focused on **surprise, stakes, or payoff**, not a neutral summary of every section.
- Prefer **few strong beats** over exhaustive coverage.
- Use **educational, active voice**. State facts directly without being condescending (avoid "You will learn to treat..." or "You get...").
- Explain the hooks. Instead of "hippocampal paths not taken," say "brain cells fire along paths they never take."

**MUST NOT**

- Turn the body into **course-style** notes: full chapter-by-chapter guides, long timestamp maps, or mandatory “So what?” footers (those belong in **`courses/**`** content, not default video picks).
- Use the body as a **transcript substitute** or a second article above the fold.

**MAY**

- Move **archive-grade** notes (full chapter guides, long timestamp lists) to a **separate** page or doc and **link once** from a short body if you still need them.
- Use **`cognitive-science-methodology.md`** (repo root) only as **light** editing discipline (chunking, cut fluff). Do **not** paste course templates onto **`type: video`** pages.

## Section paths

Posts are normal pages under a section folder, for example:

- `content/mind-infrastructure/<slug>/index.md`
- `content/human-condition/<slug>/index.md`

**Section** comes from the **folder**, not from `type`. `hugo.toml` already lists **`mind-infrastructure`** and **`human-condition`** in **`params.home.contentSections`** so new video posts can appear on the home feed.

## Authoring workflow

1. Create with **`hugo new content/<section>/<slug>/index.md --kind video`** (archetype: **`archetypes/video.md`**).
2. Set **`title`**, **`description`** (lead), **`youtube_id`**, **`categories`**, **`tags`**, **`draft`**, optional **`subtitle`** and featured image resource.
3. Write the **body** as optional commentary below the embed. If you are **compressing** long notes, follow **Compressed pitch (long notes → short page)** above.
4. Run a local **`hugo`** build before publishing.

## Style and repo rules

- MUST follow **`.cursor/rules/content-markdown-writing.mdc`** for English, punctuation, and prose habits.
- Styling hooks: **`assets/css/_custom.scss`** (`.single-video`, `.video-page__embed`, `.video-page__lead`).

## References in this repo

- Archetype: **`archetypes/video.md`**
- Layout: **`layouts/video/single.html`**
- Built-in embed: LoveIt docs *Theme Documentation - Built-in Shortcodes* → **youtube** (see `themes/LoveIt/exampleSite/content/posts/theme-documentation-built-in-shortcodes/index.en.md`).
