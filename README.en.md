# Ian Xiaohei Illustrations

[简体中文](README.md) · **English** · [日本語](README.ja.md)

> Turn the judgments, flows, states and metaphors inside an article into white-background, hand-drawn, absurd-but-clean body illustrations. The article can be in any language; the handwritten labels follow the article's language.
>
> 16:9 landscape | Xiaohei IP | pure white hand-drawn | sparse red/orange/blue handwritten labels | multilingual | Codex Skill

---

## What this repo is

Ian Xiaohei Illustrations is a Codex Skill that guides an AI agent to generate body illustrations for articles, posts, blogs, Notion documents and methodology content. The source language is not restricted — Chinese, English and Japanese all work — and the handwritten labels in the image follow the article's language by default.

It is not a generic illustration prompt, and it is not a PPT infographic template. Its core goal: first understand the cognitive anchors in the article, then turn one judgment, flow, structure, state or metaphor into a memorable 16:9 hand-drawn explanatory image.

The default visual IP is **Xiaohei (小黑)**: a small solid-black creature with white dot eyes, thin legs and a blank expression. Xiaohei is not a mascot, not a sticker, and not decoration standing in a corner — it is an absurd worker seriously participating in how the system runs.

In one line: **make the AI draw a key cognitive action from the article, not just "add a picture."**

---

## Who it's for

A good fit if you:

- Write articles (Chinese, English, Japanese, etc.) and need body illustrations
- Produce knowledge content, methodology content or AI workflow content
- Want to turn abstract judgments into concrete metaphors
- Want an illustration style lighter, stranger and more personally recognizable than a PPT infographic
- Use Codex for content production and want to reuse one stable visual language

Not a fit if you want:

- Commercial illustration, brand key visuals or polished flat illustration
- Traditional PPT infographics, complex architecture diagrams or formal flowcharts
- Children's cartoons, cute IP or sticker-pack style
- To cram lots of body text, long explanations or a full course page into one image
- Strictly editable vector source files

---

## What it produces

Default output:

- 16:9 landscape body illustrations
- A shot list of 4-8 images for one article
- Per image: theme, core idea, structure type, what Xiaohei does, and suggested labels (in the article's language)
- Final PNGs, saved to `assets/<article-slug>-illustrations/` in your workspace

Not produced by default:

- PPTX / PDF / Keynote
- Editable SVG / HTML / Canvas
- Commercial posters or cover key visuals
- Text-heavy infographics

---

## Visual style

This skill defaults to Ian's "Xiaohei absurd body illustration" style:

- Pure white background — no paper texture, beige, shadows or gradients
- Black hand-drawn line art, thin lines, slightly wobbly
- Lots of white space; the main subject takes only about 40%-60% of the canvas
- Sparse red, orange and blue handwritten labels, in the article's language
- One image expresses only one core action, structure, state or metaphor
- Xiaohei must perform the core action, never just decorate
- Absurd, creative, clean — never childish or cutesy

---

## Examples

### Two breakpoints

![Two breakpoints](examples/images/01-two-breakpoints.png)

### Sort by purpose

![Sort by purpose](examples/images/02-sort-by-purpose.png)

### One fish, many uses

![One fish, many uses](examples/images/03-one-fish-many-uses.png)

### Handoff path

![Handoff path](examples/images/04-handoff-path.png)

### Information well

![Information well](examples/images/05-information-well.png)

### Idea press

![Idea press](examples/images/06-idea-press.png)

### Content fermentation

![Content fermentation](examples/images/07-content-fermentation.png)

### Trust bridge

![Trust bridge](examples/images/08-trust-bridge.png)

These images are style calibration samples, not composition templates. Reinvent the metaphor from the article at hand instead of copying the objects and compositions of old cases.

---

## Install

Clone the repo:

```bash
git clone https://github.com/helloianneo/ian-xiaohei-illustrations.git
cd ian-xiaohei-illustrations
```

Copy the skill into your Codex skills directory:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R ./ian-xiaohei-illustrations "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Then use it in Codex:

```text
Use $ian-xiaohei-illustrations to design and generate 5 Xiaohei absurd body illustrations for this article.
```

---

## How to use

### Planning only

```text
Use $ian-xiaohei-illustrations. Do not generate images yet.
Analyze the article below, find where illustrations are worth adding, and output a shot list of about 5 images.
For each image, specify: which paragraph it follows, the theme, the core idea, the structure type, what Xiaohei is doing, and suggested labels.

<paste article>
```

### Generate body illustrations directly

```text
Use $ian-xiaohei-illustrations to generate 4 Xiaohei absurd body illustrations for the article below.
Requirements: 16:9 landscape, pure white background, black hand-drawn line art, sparse red/orange/blue handwritten labels.

<paste article>
```

### One image for a single idea

```text
Use $ian-xiaohei-illustrations to generate one body illustration for: "Trust is not announced; it is laid down one piece of evidence at a time."
Make it absurd but clean. Xiaohei must perform the core action.
```

### Override the label language

```text
Use $ian-xiaohei-illustrations to generate 3 body illustrations for the Chinese article below.
The article is in Chinese, but write all labels in English, 1-4 words each. Do not mix writing systems.

<paste article>
```

### Remove a title or wrong text from an image

```text
Use $ian-xiaohei-illustrations to edit this image: remove the "Workflow" title in the top-left corner and keep everything else unchanged.
```

More examples in [examples/prompts.md](examples/prompts.md).

---

## Workflow

The skill runs like this:

1. Read the article, Markdown, Notion content, screenshot or topic you provide
2. Extract the core argument, cognitive turning points, structures and the passages worth visualizing
3. Output a shot list first — one cognitive anchor per image
4. Pick a structure type per image: workflow, system slice, before/after, character state, conceptual metaphor, layered method, map route, or short comic panels
5. Reinvent a low-tech, absurd but coherent physical metaphor
6. Put Xiaohei in charge of the core action
7. Generate each image with a separate image-model call
8. Check against the QA checklist: white background, white space, Xiaohei's action, label language and readability, no PPT feel, no copying old cases
9. Save the final PNGs and report their purpose and paths

---

## Repo structure

```text
.
├── README.md
├── README.en.md
├── README.ja.md
├── LICENSE
├── NOTICE.md
├── assets/
│   └── ian-wechat-qr.jpg
├── examples/
│   ├── images/
│   │   ├── 01-two-breakpoints.png
│   │   ├── 02-sort-by-purpose.png
│   │   └── ...
│   └── prompts.md
└── ian-xiaohei-illustrations/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   └── examples/
    └── references/
        ├── style-dna.md
        ├── xiaohei-ip.md
        ├── composition-patterns.md
        ├── prompt-template.md
        └── qa-checklist.md
```

The part you actually install into Codex is the subdirectory:

```text
ian-xiaohei-illustrations/
```

The README, LICENSE, NOTICE and examples at the root are GitHub-facing documentation.

---

## Notes

- The shorter the text in an image, the more reliable it renders. Non-Latin scripts (Chinese, Japanese, Korean) break more easily than English, so use fewer and shorter labels.
- The label language follows the article by default; to force English labels, say so explicitly in the prompt.
- One core structure per image — do not turn the article into a manual.
- Xiaohei must perform the core action. If the image still works with Xiaohei removed, Xiaohei is decoration.
- The sample images only calibrate line density, white space, color restraint and how Xiaohei participates. Do not copy their compositions.
- AI image models can produce typos, hallucinated labels, style drift or unwanted titles. Always review what comes out.
- If typos are severe, cut the number of labels and regenerate. If the language is wrong or mixed, pin the label language to exactly one in the prompt.

---

## Related projects

- [Ian Handdrawn PPT](https://github.com/helloianneo/ian-handdrawn-ppt) — a skill for hand-drawn technical PPT-style page images in Chinese
- [Awesome Claude Code Skills](https://github.com/helloianneo/awesome-claude-code-skills) — a curated list of Claude Code skills, agents and plugins
- [Obsidian + Claude AI Second Brain](https://github.com/helloianneo/obsidian-ai-second-brain) — a guide to building a personal knowledge base with Obsidian and Claude AI

---

## About the author

**Ian (伊恩)** — product designer / one-person company practitioner / AI builder

Building a one-person company with an AI team.

- GitHub: [helloianneo](https://github.com/helloianneo)
- X/Twitter: [@ianneo_ai](https://x.com/ianneo_ai)
- Website: [www.ianneo.xyz](https://www.ianneo.xyz)
- WeChat: `ianneoxyz`
- Email: hello.neoc@gmail.com

---

## Keep exploring

This Xiaohei illustration skill is just one small tool in the personal production system I build with AI.

If you also use AI for content, knowledge bases, workflows or productization, keep reading at [www.ianneo.xyz](https://www.ianneo.xyz).

If you'd rather just watch for now, follow me on [X/Twitter](https://x.com/ianneo_ai).

Curious about the Indie Builders Club? Add me on WeChat: `ianneoxyz`, with the note "OPC".

<p>
  <img src="assets/ian-wechat-qr.jpg" alt="Ian WeChat QR code" width="120">
</p>

If scanning is inconvenient, search for the WeChat ID: `ianneoxyz`.

---

## License

MIT License. See [LICENSE](LICENSE).
