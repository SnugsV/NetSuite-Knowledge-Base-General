# Writing Standards

## Purpose

Define the tone, voice, and teaching approach for all documentation in this repository.

## Tone

Write like a knowledgeable NetSuite consultant teaching a new user. Be clear, practical, and direct. Use "you" when addressing the reader. Avoid promotional or marketing language.

## Audience

Primary audience is someone learning NetSuite — administrators, developers, consultants, and business users. They may have experience with other ERP systems or none at all.

- Do not assume technical expertise
- Do not assume familiarity with NetSuite terminology
- Do assume the reader is intelligent and motivated to learn

## Teaching Philosophy

### Teach Before Instructing

Explain *why* something exists before showing *how* to use it. A user who understands the concept can adapt steps to their situation. A user who only knows steps is helpless when something changes.

### Show the Business Problem

Every feature exists to solve a business problem. Lead with the problem. Example:

> Before NetSuite, a growing company might track inventory in a spreadsheet, sales in one system, and accounting in another. Reconciling these at month-end was time-consuming and error-prone. NetSuite solves this by storing all data in one shared system.

### Use Concrete Examples

Abstract explanations are hard to remember. Concrete examples stick.

- Instead of: "Inventory transfers move stock between locations"
- Write: "A company with a New York warehouse and a Chicago warehouse uses inventory transfers to rebalance stock without changing total inventory value."

### Progressive Disclosure

Start with the simplest explanation. Add detail as the article progresses. A beginner should understand the first paragraph; an expert can dive deeper.

## Writing Rules

| Rule | Explanation |
|---|---|
| One H1 per article | The article title |
| Descriptive headings | Not "Overview" — use "What Is NetSuite?" |
| Short paragraphs | 3-5 sentences max |
| Define acronyms | First use in each article |
| Prefer active voice | "Use the search field" not "The search field can be used" |
| Avoid vendor copying | Never copy Oracle documentation verbatim |
| Be specific | "Click Save" not "Complete the transaction" |
| Use lists for steps | Numbered steps for procedures, bullets for options |

## Plain Language Guidelines

- Use short words over long ones
- Use "use" not "utilize"
- Use "start" not "initiate"
- Use "show" not "display"
- Use "help" not "facilitate"
- Break complex sentences into shorter ones
- Replace "if and when" with "if"

## AI Optimization

Writing for AI retrieval means:

- Consistent section headers that AI can parse
- "Quick Summary" as the first content section
- "Common Mistakes" section that captures troubleshooting queries
- "Related Articles" for knowledge graph connections
- Front matter for metadata queries

## Accessibility

- Use alt text for images (when images are added)
- Use descriptive link text (not "click here")
- Ensure sufficient color contrast in diagrams
- Use tables for structured data

## Consistency

- Follow the DOCUMENTATION_STANDARDS.md article structure
- Use the same terminology across all modules
- Keep similar content in similar heading positions
- Use consistent formatting for UI paths: **Menu > Submenu > Item**

## Related Documents

- [DOCUMENTATION_STANDARDS.md](DOCUMENTATION_STANDARDS.md) — Article structure and metadata
- [AI_STANDARDS.md](AI_STANDARDS.md) — AI optimization guidelines
- [QUALITY_STANDARDS.md](QUALITY_STANDARDS.md) — Quality scoring