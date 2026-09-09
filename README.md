# Alec Stephens

Applied AI engineer. I sit between a team and the model: learn how the work
actually runs, ship the agent, the knowledge system, or the automation that
runs it, and keep it running in production. Then I teach the people who use it.

Two years of that, end to end, for businesses that hand over their AI work and
expect it to hold up on a Tuesday afternoon with the wifi flickering.

**Stack I ship in:** TypeScript and Python. Claude and OpenAI APIs, agents and
tool calling, MCP servers and connectors, evals, RAG on Postgres and Pinecone.
Supabase with row-level security, Next.js, Google Apps Script, Playwright,
Docker. Claude Code and Codex as the daily build environment, with scoped
sub-agents and a shared context layer between them.

## Systems in production

| System | Where it runs | What it does |
|---|---|---|
| **Front-desk knowledge base** | 27-person eyecare clinic, daily since Aug 2026 | Staff look up plan rules, protocols, and pricing in seconds. Two named managers edit in-app behind Postgres RLS and Google OAuth, with revision history and restore. Offline-first on tablets. The generic pattern is public: [supabase-team-knowledge-base](https://github.com/alecstephens3-stack/supabase-team-knowledge-base). |
| **PTO and payroll system** | Same clinic, since Apr 2026 | Replaced a paper process that cost 60 to 100 hours a year. Form intake, balance and conflict checks, approvals from a phone, calendar events, a payroll report every pay period. Anniversary-aware routing, recompute-on-write balances, a 22-check release suite. The logic is public: [apps-script-pto-payroll](https://github.com/alecstephens3-stack/apps-script-pto-payroll). |
| **Claude Team rollout + invoice capture** | Same clinic, 2026 | Four seats, connectors, onboarding sessions for the bookkeeper. Vendor PDF bills routed into QuickBooks capture with filing rules, vendor defaults, and a human review step. Deterministic where the answer is known; the model only handles the messy input. |
| **AI operating model for a consulting practice** | HR and business-coaching firm | One knowledge doc as the source of truth and four agents that triage the inbox, draft scheduling replies, turn voice notes into tasks, and keep the doc current. Handed over as a portable 7-file system the owner runs herself. |
| **In-house AI stack for a 1M-audience education company** | Mar to Sep 2026 | Owned the AI tooling and ran the engineering through Claude Code and Codex: MCP and API connections into Wistia, Circle, Customer.io, Google Workspace, and Slack; a one-command publishing pipeline with an ffmpeg loudness gate; the weekly KPI report leadership reads; a newsletter that went from a multi-hour job to review-and-send. About 10 hours a week back to the team. Plus 100+ short tutorials on agents, Claude Code, and MCP for a non-technical audience. |
| **My own operating system** | Every day | A 500+ note vault with RAG search, 28+ automation modules, six least-privilege sub-agents wired to 10+ systems through MCP, and scheduled jobs that leave an inspectable log. The site it produces: [stephensai.co](https://stephensai.co) ([source](https://github.com/alecstephens3-stack/alec-stephens-ai)). |

## What I care about when I build

- **The grid is the truth, the counter is a copy.** Anything derived gets
  recomputed from source after every write. Counters drift; I have the bug
  reports to prove it.
- **Regression tests that can fail on the bug.** A test that passes on the
  broken code proves nothing. My suites run the old predicate too.
- **Degrade to the old behaviour.** New routing ships with a fallback to the
  path it replaces, so a live request can never break on deploy day.
- **Deterministic where the answer is known.** The model gets the messy input
  and the judgment call. Everything else is a script with a log.
- **Write the reasoning next to the code.** The next person is usually me in
  three months, or a client's office manager reading a runbook.

## Elsewhere

[stephensai.co](https://stephensai.co) · [LinkedIn](https://linkedin.com/in/alecpstephens) · alec@stephensai.co
