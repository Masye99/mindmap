# Wiki Schema

## Domain
Personal memory wiki — a record of what we've done together: Hermes Agent setup,
messaging platforms, automation, and the tools and lessons learned along the way.

## Conventions
- File names: lowercase, hyphens, no spaces (e.g., `telegram-bot-setup.md`)
- Every wiki page starts with YAML frontmatter (see below)
- Use `[[wikilinks]]` to link between pages (minimum 2 outbound links per page)
- When updating a page, always bump the `updated` date
- Every new page must be added to `index.md` under the correct section
- Every action must be appended to `log.md`
- **Provenance markers:** On pages that synthesize 3+ sources, append
  `^[raw/articles/source-file.md]` at the end of paragraphs whose claims come
  from a specific source.

## Frontmatter
  ```yaml
  ---
  title: Page Title
  created: YYYY-MM-DD
  updated: YYYY-MM-DD
  type: entity | concept | comparison | query | summary
  tags: [from taxonomy below]
  sources: [raw/articles/source-name.md]
  confidence: high | medium | low
  ---
  ```

## Tag Taxonomy
- Platform: telegram, discord, slack, whatsapp, email
- Hermes: hermes, gateway, bot, cron, webhook, skills, memory, config
- Tooling: terminal, docker, git, github, proxy, auth
- Topic: setup, troubleshooting, automation, research, planning
- Meta: comparison, timeline, reference

Rule: every tag on a page must appear in this taxonomy. If a new tag is needed,
add it here first, then use it.

## Page Thresholds
- **Create a page** when an entity/concept appears in 2+ sources OR is central to one source
- **Add to existing page** when a source mentions something already covered
- **DON'T create a page** for passing mentions, minor details, or things outside the domain
- **Split a page** when it exceeds ~200 lines

## Update Policy
When new information conflicts with existing content:
1. Check the dates — newer sources generally supersede older ones
2. If genuinely contradictory, note both positions with dates and sources
3. Flag for user review in the lint report
