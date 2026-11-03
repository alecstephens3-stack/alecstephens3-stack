# Alec Stephens

I'm an applied AI engineer and co-founder of [Stephens AI](https://stephensai.co). We build
software for independent healthcare practices. I start with the person who does the job, find the
task that takes most of their week, and build software that does it and asks them before anything
risky.

Client code stays private. The repos below are rebuilds of production systems with no client data
in them. The tests came across with the code.

## Repos

| Repo | What it is |
|---|---|
| [bill-intake](https://github.com/alecstephens3-stack/bill-intake) | Vendor bills read by Claude on AWS Bedrock, filed by plain rules, entered in QuickBooks Online only after a person approves. The production version has run on a bookkeeper's PC since 1 October 2026, with no failed bill as of late October. |
| [computer-use-agents](https://github.com/alecstephens3-stack/computer-use-agents) | Claude computer-use agents for practice software with no API. The checks that matter run in code, a work queue is handled one row per conversation, and a recorded run replays for free until the screen changes. Built against a mock back-office app with a scorer. |
| [claude-code-operating-system](https://github.com/alecstephens3-stack/claude-code-operating-system) | How I run the business on Claude Code: sub-agents with least-privilege tool lists, hook guards, a secret-scanning pre-commit hook, scheduled jobs, and a one-way mirror for Codex. |
| [claude-code-voice-mod](https://github.com/alecstephens3-stack/claude-code-voice-mod) | A Claude Code mod that holds the agent to one writing voice, checks each reply and outgoing draft with a Simplified Technical English checker, and opens browser steps as checklist pages whose ticks are saved. |
| [lens-design-system](https://github.com/alecstephens3-stack/lens-design-system) | The design system behind our reports and proposals. Tokens generated to CSS, JSON and TypeScript, a build step that inlines the kit into one HTML file, and a WebGL shader that draws photos as banknote-style engravings. |
| [supabase-team-knowledge-base](https://github.com/alecstephens3-stack/supabase-team-knowledge-base) | The pattern behind an eye care practice's front-desk knowledge base: everyone reads, two named people edit, and Postgres row-level security enforces it. |
| [apps-script-pto-payroll](https://github.com/alecstephens3-stack/apps-script-pto-payroll) | The date and balance logic from a clinic's time-off and payroll system on Google Sheets, with 183 regression tests. |
| [alec-stephens-ai](https://github.com/alecstephens3-stack/alec-stephens-ai) | The stephensai.co site. Next.js, React, TypeScript, Tailwind. |

## Running now

At an eye care practice, the front desk looks things up in a knowledge base I built instead of
stopping the office manager, which comes to about 200 hours a year. Time off and payroll moved
off paper slips onto a system that routes requests, checks balances and builds the payroll
report, about 60 to 100 hours of admin a year. The bill reader costs about a cent a bill. In a
side-by-side test on the bookkeeper's real invoices, QuickBooks' own reader got 40% of the totals
wrong and ours got every one right.

With my co-founder I'm also building insurance claims software. It reads a practice's claims
report and asks each insurer where every unpaid claim stands over X12 276/277, inside the
practice's own AWS account. It runs at an eye care practice, and a dental practice is being set
up.

Before this I owned the AI tooling at a nine-figure education company and made more than 200
short videos teaching AI to people who don't work in tech.

## How I build

I use plain code where the answer is known and the model only for messy input, like a scanned
bill or an insurer's reply. Anything that touches money or patient data waits for a person. When
something breaks, I add a check that fails loudly and a test built from the case that broke.

[stephensai.co](https://stephensai.co) · [LinkedIn](https://linkedin.com/in/alecpstephens) · alec@stephensai.co
