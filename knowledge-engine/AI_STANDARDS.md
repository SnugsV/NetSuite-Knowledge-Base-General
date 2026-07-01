# AI Standards

## Purpose

Define how documentation should be written for optimal consumption by humans, LLMs, RAG systems, search engines, and future AI agents.

## The Multi-Audience Problem

Documentation in this repository serves multiple readers simultaneously:

1. **Humans** — Reading for learning and reference
2. **LLMs** — Being prompted with documentation as context
3. **RAG systems** — Being retrieved and fed to answer engines
4. **Search engines** — Being indexed for discoverability
5. **AI agents** — Being tool-called or scraped for automated workflows

Writing for one audience at the expense of others reduces the value of the content. The standards below optimize for all audiences simultaneously.

## Metadata (Front Matter)

YAML front matter serves all audiences. AI systems parse front matter to filter, classify, and retrieve articles.

Required fields:

```yaml
---
title: Article Title          # Human and AI readable
module: Module Name            # Enables module-level filtering
difficulty: Beginner           # Enables difficulty-based filtering
estimated_time: 5 minutes      # Helps humans plan
status: Draft                  # Signals reliability to AI systems
---
```

## Article Structure for AI Retrieval

AI systems retrieve information more accurately when documents use consistent structure. Follow this order:

1. **Title** — H1, contains primary search terms
2. **Quick Summary** — 1-3 sentences that answer "what is this?" — serves as the RAG snippet
3. **Body sections** — Consistent H2 headings that AI can parse structurally
4. **Related Articles** — Links that build the knowledge graph for both humans and AI
5. **Oracle References** — External authoritative links

## RAG Optimization

Retrieval Augmented Generation (RAG) systems split documents into chunks and retrieve the most relevant chunks for a query. Optimize for this:

- Each section should be somewhat self-contained (a RAG system may retrieve only one section)
- Avoid ambiguous references like "as discussed above" — be explicit
- Use "Quick Summary" as the primary retrieval target for broad queries
- Use "Common Mistakes" for troubleshooting queries
- Use "FAQ" for question-answer patterns
- Use concrete terminology that matches what users search for

## LLM Context Optimization

When LLMs receive documentation as context (e.g., in a prompt), they benefit from:

- **Clear separation** between explanation and reference material
- **Consistent formatting** — headings, lists, code blocks
- **Self-contained files** — each article can be understood without reading others
- **Explicit cross-references** — "See [Inventory Transfers] for details" rather than "see above"

## Knowledge Graph Construction

Cross-links between articles form a knowledge graph. AI systems can traverse this graph to find related content.

- Every article links to 3-5 related articles
- Links use descriptive text: "[Inventory Transfers](../inventory/inventory-transfers.md)"
- Links go both directions when possible (if A links to B, B should link to A)

## Search Engine Optimization

For future public hosting (MkDocs, GitHub Pages):

- Use descriptive file names that contain key terms
- Use H1 that contains primary keywords
- Use "Quick Summary" as the meta description equivalent
- Use alt text on images (when added)

## AI Agent Consumption

When AI agents use this repository as a tool:

- Front matter enables filtering by module, difficulty, and status
- Consistent structure enables programmatic parsing
- "Quick Summary" enables fast relevance checking
- "Related Articles" enables traversal

## Human-Over-AI Priority

Despite all AI optimization, humans remain the primary audience. If a choice must be made between AI readability and human readability, choose human readability.

- AI-friendly structure should enhance human experience, not degrade it
- Short paragraphs and clear headings benefit both audiences
- Front matter is invisible to human readers but valuable for AI

## Related Documents

- [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) — Article structure and metadata
- [WRITING_STANDARDS.md](WRITING_STANDARDS.md) — Tone, voice, teaching
- [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) — Quality scoring