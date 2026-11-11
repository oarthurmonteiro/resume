# Leadership Principle → story mapping

Full stories live in `stories.md`. This file is the index: which story to reach for per principle, and
an honest list of the principles nothing in `raw.md` actually supports.

## Covered principles

| Leadership Principle | Primary story | Backup story |
|---|---|---|
| Customer Obsession | Story 6 (AI recruiting agent) | Story 8 (Metabase), Story 7 (government reporting) |
| Ownership | Story 1 (SDK consolidation) | Story 5 (N+1 fix), Story 7, Story 9 |
| Invent and Simplify | Story 4 (hexagonal architecture) | Story 8 (Metabase), Story 1 (SDK) |
| Are Right, A Lot | Story 2 (OpenTelemetry vs. vendor lock-in) | Story 10 (CRM internationalization) |
| Learn and Be Curious | Story 6 (AI recruiting agent) | Story 10 (CRM), Story 9 (ScanSource) |
| Insist on the Highest Standards | Story 4 (hexagonal architecture) | Story 2 (OpenTelemetry), Story 1 |
| Think Big | Story 6 (AI recruiting agent) | Story 1 (SDK), Story 8 (Metabase) |
| Bias for Action | Story 7 (government reporting automation) | Story 3 (Go TUI), Story 9 (ScanSource) |
| Frugality | Story 3 (Go TUI host idleness) | Story 5 (N+1 fix, infra cost angle) |
| Earn Trust | Story 10 (CRM internationalization) | none strong, see note below |
| Dive Deep | Story 5 (N+1 query fix) | Story 1 (SDK), Story 3 (Go TUI) |
| Deliver Results | Story 5 (N+1 fix) | Story 9 (ScanSource 98%), Story 7 (gov reporting) |

## Gaps: no grounded story exists yet

These four principles have nothing solid in `raw.md`. Don't force-fit one of the 10 stories above into
them in an actual interview, Amazon interviewers probe hard on the specific LP being asked about and a
stretched-to-fit story reads as evasive. Answer the prompts below for yourself; if a real example comes
to mind, write it up as an 11th+ story in `stories.md` using the same STAR structure.

### Hire and Develop the Best
`raw.md` has no mention of hiring, interviewing, mentoring, or formally developing someone else's
career. Prompts to check your own memory against:
- Did you ever onboard, train, or mentor a freelance collaborator, intern, or junior engineer, at
  Intelligenti, Companhia de Estágios, or elsewhere?
- Did you ever participate in a technical interview or hiring decision, even informally (e.g. pairing
  with a candidate, reviewing a take-home)?
- Did you ever push back on hiring someone you thought wouldn't raise the bar, or advocate for someone
  you thought would?
If none of these happened, say so plainly in the interview rather than inventing a thin example, it's a
more credible answer than a forced one for an IC without people-management scope yet.

### Have Backbone; Disagree and Commit
This is one of the most commonly asked LPs and currently has zero grounded coverage. Two existing
stories are plausible homes for a real example, check your actual memory against them before the
interview:
- **Story 2 (OpenTelemetry/observability):** did anyone argue for a simpler, paid tool instead, and did
  you have to make the case for the open-protocol approach?
- **Story 4 (hexagonal architecture refactor):** did engineering leadership or product want a quick
  patch instead of the time investment in an architectural fix?
If neither of those actually involved pushback, think about any other moment (a code review disagreement,
a technical direction you argued against, a deadline/scope fight) and write it up properly, don't leave
this one unanswered walking into the loop.

### Strive to be Earth's Best Employer
Nothing in `raw.md` about team culture, psychological safety, employee growth, or workplace improvement
initiatives. Prompts:
- Did you ever raise a concern about team workload, burnout, or process that led to a real change?
- Did you help a teammate grow in a specific, nameable way (not just "helped the team")?
- Did you make work more fun or less painful for someone else in a concrete way?

### Success and Scale Bring Broad Responsibility
This principle is about org-scale/societal responsibility, naturally hard for an individual contributor
to have a clean story for. The closest fit in the existing material is **Story 8 (Metabase token-based
client access)**, since it's genuinely about protecting client data properly as the dashboard system
scaled across many clients, but treat that as a stretch/secondary fit, not a confident primary answer.
Prompt: any time you considered the broader or longer-term consequence of a technical decision (data
privacy, security, maintainability that would affect teams beyond your own) before acting on it?

## Before the actual interview

Every **[FILL IN]** marker in `stories.md` is a real gap, not filler text. Go through each story and
either supply the real detail from memory, or decide the story is weaker than it looks and should be
backup rather than primary for that principle. An interviewer's follow-up questions land exactly on the
things currently marked FILL IN: the obstacle, who else was involved, the trade-off, what you'd do
differently. Walking in with those still blank is the single biggest risk in this file, bigger than the
0-coverage gaps above, since those are at least honestly disclosed instead of silently thin.
