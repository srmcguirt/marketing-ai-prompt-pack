# 📣 WireForge — Marketing AI Prompt Pack

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](./LICENSE) [![Prompts](https://img.shields.io/badge/Prompts-8-orange?style=flat-square)](./system-prompts/) [![GitHub stars](https://img.shields.io/github/stars/srmcguirt/marketing-ai-prompt-pack?style=flat-square)](https://github.com/srmcguirt/marketing-ai-prompt-pack)

**8 expert-level AI prompt templates for marketing professionals and agencies.**  
Stop getting generic outputs. Start getting campaign-ready results.

> Built by **WireForge** — production-grade AI tools for professionals.

> 💎 **Full pack** with all 8 prompts, few-shot examples, output schemas, and future updates → **[Get it on Gumroad ($49) →](https://srmcguirt.gumroad.com)**
>
> 📬 **Free sample prompt** — [subscribe at wireforge.fellwork.workers.dev](https://wireforge.fellwork.workers.dev)

---

## The Problem

Generic AI prompts produce generic marketing. You ask ChatGPT to "write a landing page" and get a template that sounds like every other SaaS landing page. You ask it to "plan a social media campaign" and get a list of obvious tactics with no depth.

The fix is the prompt. Specifically: a structured, role-defined, output-specified prompt that treats the AI like a specialist, not a search engine.

That's what this pack is.

---

## What's Inside

| # | Prompt | What it produces |
|---|--------|-----------------|
| 01 | **SEO Content Optimizer** | Full optimization report: keyword map, meta tags, content issues, technical checklist |
| 02 | **Social Media Campaign Planner** | Complete campaign brief: platform strategy, content pillars, 30-day calendar, hook library |
| 03 | **Email Sequence Writer** | Full email sequences with 3 subject line options per email, segmentation rules, deliverability flags |
| 04 | **Landing Page Copywriter** | Complete page copy: above fold, problem/solution, feature benefits, testimonials, FAQ, CTA |
| 05 | **Ad Copy Generator (Google + Meta)** | RSA headlines + descriptions + extensions; Meta feed/carousel/video scripts; A/B test matrix |
| 06 | **Brand Voice Architect** | Full brand voice guide: voice dimensions, spectrum sliders, writing mechanics, banned words |
| 07 | **Content Calendar Strategist** | Content pillar architecture, 30-day calendar, repurposing system, editorial brief template |
| 08 | **Analytics Report Narrator** | Executive-ready performance report with narrative, recommendations, and watchlist |

**Each prompt includes:**
- ✅ Detailed role definition and constraints
- ✅ Step-by-step output structure the AI follows
- ✅ 3–5 realistic few-shot examples (input → output)
- ✅ JSON Schema for structured/API use
- ✅ Edge case handling (what to do when the situation is complex)

---

## ⚡ The WireForge Prompt Architecture

Every WireForge prompt follows our **4-Layer Prompt Architecture** — a methodology we developed after studying what separates prompts that produce campaign-ready output from prompts that produce generic marketing fluff.

```
┌─────────────────────────────────────────────┐
│  Layer 1: IDENTITY                          │
│  Senior role + specific experience scope    │
│  "You've run campaigns with $500K+ budgets" │
├─────────────────────────────────────────────┤
│  Layer 2: GUARDRAILS                        │
│  10-15 behavioral constraints that prevent  │
│  common AI failure modes in marketing       │
│  "Never use fake urgency or scarcity"       │
├─────────────────────────────────────────────┤
│  Layer 3: OUTPUT BLUEPRINT                  │
│  Exact section-by-section format — the AI   │
│  produces structured deliverables, not      │
│  freeform essays you have to reformat       │
├─────────────────────────────────────────────┤
│  Layer 4: EDGE CASE LIBRARY                 │
│  7-8 specific scenarios (regulated          │
│  industries, cold vs warm traffic, multi-   │
│  market campaigns) that trip up generic AI  │
└─────────────────────────────────────────────┘
```

**Why this matters:** Most AI prompt packs give you Layer 1 and maybe Layer 3. Without Layers 2 and 4, the AI will produce generic "10 tips" listicles, suggest vanity metrics, or ignore your compliance requirements. Our guardrails and edge cases are sourced from real campaign data and agency workflows.

### The Brief Test™

Every prompt passes the **WireForge Brief Test**: can you hand the output directly to a copywriter, media buyer, or client as a working brief? If it needs a rewrite before it's useful, the prompt isn't done. That's our standard.

---

## Before & After

### ❌ Generic prompt
> "Write a landing page for my email marketing tool."

**Output:** Generic headline. Vague bullets. Template-sounding copy that converts at 1%.

### ✅ WireForge Landing Page Copywriter
> *[Paste the prompt, fill in your product details, audience, differentiator, social proof]*

**Output:** 
- Headline: "Write Better Emails. See Opens Jump — in Your First Week."
- Above-fold social proof: "Trusted by 12,400 marketers at Stripe, HubSpot, and Notion"
- 6 feature/benefit blocks with specific elaboration
- 3 long-form testimonials with specific results
- 7 FAQ items addressing real purchase objections
- Two CTAs with different copy to create momentum

Conversion rate difference: 2x–4x typical in real-world testing.

---

## How to Use

### Option 1: Copy-paste into any AI tool

1. Open `system-prompts/` → choose your prompt
2. Copy the prompt block (between the triple backticks)
3. Paste into Claude.ai, ChatGPT, or Cursor chat
4. Fill in the `[PLACEHOLDER]` sections with your actual details
5. Send and get campaign-ready output

Works with: **Claude** (best results), **GPT-4 / o1**, **Gemini**, **Cursor**, **Cline**

### Option 2: Use as a custom instruction / system prompt

In Claude Projects or ChatGPT Custom Instructions:
1. Copy the full prompt including the role definition
2. Paste as your "System prompt" or "Custom Instructions"
3. Now every conversation in that context uses the expert persona

### Option 3: API / programmatic use

Use the JSON schemas in `output-schemas/` to force structured output:

```python
import anthropic
import json

client = anthropic.Anthropic()

# Load the prompt
with open("system-prompts/01-seo-content-optimizer.md") as f:
    system_prompt = f.read()

# Load the schema  
with open("output-schemas/01-seo-content-optimizer.json") as f:
    schema = json.load(f)

# Run with structured output
response = client.messages.create(
    model="claude-opus-4-5",
    max_tokens=4096,
    system=system_prompt,
    messages=[{
        "role": "user",
        "content": f"Optimize this content:\nKeyword: {target_keyword}\nContent: {article_content}"
    }]
)
```

### Option 4: Cursor / Claude Code rules

Add to your `.cursorrules` or `CLAUDE.md`:

```
When I say /seo, use the SEO Content Optimizer from [path/to/prompts/01-seo-content-optimizer.md]
When I say /email, use the Email Sequence Writer from [path/to/prompts/03-email-sequence-writer.md]
```

---

## Folder Structure

```
marketing-ai-prompt-pack/
├── system-prompts/
│   ├── 01-seo-content-optimizer.md
│   ├── 02-social-media-campaign-planner.md
│   ├── 03-email-sequence-writer.md
│   ├── 04-landing-page-copywriter.md
│   ├── 05-ad-copy-generator.md
│   ├── 06-brand-voice-architect.md
│   ├── 07-content-calendar-strategist.md
│   └── 08-analytics-report-narrator.md
├── few-shot-examples/
│   ├── 01-seo-content-optimizer.json
│   ├── 02-social-media-campaign-planner.json
│   ├── 03-email-sequence-writer.json
│   ├── 04-landing-page-copywriter.json
│   ├── 05-ad-copy-generator.json
│   ├── 06-brand-voice-architect.json
│   ├── 07-content-calendar-strategist.json
│   └── 08-analytics-report-narrator.json
├── output-schemas/
│   ├── 01-seo-content-optimizer.json
│   ├── 08-analytics-report-narrator.json
│   └── ... (all 8 schemas)
├── README.md
├── LICENSE
└── CHANGELOG.md
```

---

## Quick Reference — Which Prompt for Which Job?

| Task | Use This Prompt |
|------|----------------|
| "Optimize this blog post for Google" | 01 — SEO Content Optimizer |
| "Plan our Q3 social media campaign" | 02 — Social Media Campaign Planner |
| "Write our new user welcome series" | 03 — Email Sequence Writer |
| "Write our product launch page" | 04 — Landing Page Copywriter |
| "Create Google + Facebook ads for this offer" | 05 — Ad Copy Generator |
| "Define our brand voice for the new rebrand" | 06 — Brand Voice Architect |
| "Build our content plan for next quarter" | 07 — Content Calendar Strategist |
| "Summarize our marketing performance for the CEO" | 08 — Analytics Report Narrator |

---

## Who This Is For

✅ **Marketing managers** building and executing campaigns solo or with small teams  
✅ **Growth marketers** who use AI daily and want to 10x their output quality  
✅ **Marketing agencies** delivering work to multiple clients  
✅ **Founders and solopreneurs** doing their own marketing  
✅ **Content creators** and **copywriters** who want AI to be their research and structure partner, not their ghostwriter  

**Not for:** Someone who wants AI to replace thinking. These prompts make AI work harder — but you still direct the strategy.

---

## Tips for Best Results

1. **Fill in every placeholder** — the more specific your context, the better the output. "SaaS tool for accountants at 50-500 person firms" beats "B2B tool."

2. **Include real examples** — paste in existing content, real customer quotes, or actual competitor examples when prompted. The AI uses specifics to produce specifics.

3. **Iterate, don't regenerate** — if output is 80% right, paste it back and say "Fix section 3 to be more specific about X." Don't start over.

4. **Claude performs best** with these prompts due to stronger instruction following and longer context. GPT-4 works well for most prompts. Gemini can handle all of them.

5. **Use the few-shot examples** as guidance — if your output doesn't look like the examples in `few-shot-examples/`, add more context about your audience and product.

---

## Updates

This pack receives updates when:
- Platform policies change (Meta ad policies, Google RSA changes)
- New high-performing prompt patterns are discovered
- Community feedback reveals gaps

Check `CHANGELOG.md` for version history.

---


---

## 💼 Get the Full Pack

**[Marketing AI Prompt Pack — $29 on Gumroad](https://srmcguirt.gumroad.com/l/marketing-prompt-pack)**

8 specialist system prompts, MIT licensed, plain Markdown — drop into Claude, GPT-4, or Cursor. No vendor lock-in.

→ [Full product lineup](https://wireforge.fellwork.workers.dev)

---

## License

MIT — free to use, modify, and integrate into your own tools and workflows.  
Attribution appreciated but not required.

---

## About WireForge

WireForge builds production-grade AI tools for professionals — prompt packs, MCP servers, agent boilerplates, and more.

- 🌐 [wireforge.dev](https://wireforge.fellwork.workers.dev)
- 🐙 [github.com/srmcguirt](https://github.com/srmcguirt)
- 🐦 [@wireforge](https://x.com/wireforge)

**Other products:**
- [DevOps AI Prompt Pack](https://srmcguirt.gumroad.com) — 8 prompts for DevOps and infrastructure engineers
- [MCP Server Starter Kit](https://srmcguirt.gumroad.com) — Production-ready MCP server boilerplate
- [Claude Agent Boilerplate](https://srmcguirt.gumroad.com) — Build production Claude agents fast
