# claude-skills

Agent skills written for day-to-day work at a small company and then made general. Each one came out of real use: the website skill from months of audits on a production marketing site, the two writing skills from reviewing drafts before they went to customers and onto a company page.

They use the Agent Skills format: a `SKILL.md` with any reference files the agent reads only when it needs them. Nothing in them is tied to one company, framework or brand. Where a skill needs house rules (spelling, trademarks, what is confidential), it reads them from your project instructions or `CLAUDE.md`.

## The skills

| Skill | What it does |
| --- | --- |
| [website-review-build](skills/website-review-build/) | Reviews and builds marketing and content websites so they stay correct after launch. Every rule becomes an automated check, every check runs where it can stop a bad deploy, and every check has been seen to fail. Covers SEO, accessibility, performance, security, house style, responsive layout, CMS content, mobile and motion. |
| [second-draft](skills/second-draft/) | Questions a draft Claude helped write before anyone outside the conversation reads it. Traces every number, date and claim to an exact line, page or cell in your files, flags what is not in them, reads the draft as its reader would, and applies your organisation's rules. |
| [company-post-scoring](skills/company-post-scoring/) | Scores or drafts posts for a company page: a pass-or-fail gate, eight criteria out of 16, and a publish threshold. Built for LinkedIn company pages, where a page that talks like a person reads badly. |

## Install

### Claude Code, as a plugin

Inside a Claude Code session:

```
/plugin marketplace add AbhiDas-lab/claude-skills
/plugin install abhidas-skills@abhidas-skills
```

That installs all three skills.

### Claude Code, one skill at a time

Copy a skill's folder into your personal skills folder, or into `.claude/skills/` in a project so everyone on that repository gets it:

```bash
git clone --depth 1 https://github.com/AbhiDas-lab/claude-skills.git /tmp/claude-skills
```

```bash
cp -r /tmp/claude-skills/skills/second-draft ~/.claude/skills/
```

The folder name should match the `name` in its `SKILL.md`.

### Claude.ai and the Claude desktop app

Zip a single skill's folder so that `SKILL.md` sits at the top level of the zip, then upload it under Settings, Capabilities, Skills. Skills need to be enabled for your plan or organisation.

### Other agents

Every `SKILL.md` and reference file is plain Markdown. Any agent that can read files can follow them.

## House rules

All three skills defer to your own rules where you have them. Put them in your project instructions or a `CLAUDE.md`: the spelling convention, how your company, product and partner names are written, which claims your field regulates, what must never be published. Without them, the skills fall back to stated defaults and say so in their output.

`website-review-build` includes a house profile template in `references/templates.md`.

## Licence

MIT. See [LICENSE](LICENSE).
