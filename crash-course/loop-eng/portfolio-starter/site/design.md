# The design decision
The page renders as a multi-agent trace — a single connecting thread runs down the page linking five numbered steps (received, initialized, tool-calls, tools, human-in-the-loop), each project is shown as a call-and-result pair instead of a paragraph, and the contact section is marked visibly as the one step that waits on a human instead of an agent.

## Why this person
Rubaiya's own material is orchestration, not just code: her flagship project is "a multi-agent orchestration system with tool-calling and action planning," built with "Human-in-the-Loop (HITL) decision points for reliable agent oversight," and her skill list names Multi-Agent Orchestration, Tool-Calling, HITL Systems, and Event-Driven Architecture as things she practices, not tools she's merely heard of. A page built as a trace of a run — steps executing in order, one of them explicitly gated on a human — is the one structural idea a generic "full-stack developer" page could not honestly claim, because it depends on HITL and orchestration being real parts of her work, not decoration borrowed from this file.

## How the page carries it out
- The hero opens the trace: a numbered marker (00) and a single line of display type stating the task received — no summary paragraph, no photo-and-blurb.
- A vertical thread runs down the page linking the numbered steps; the sticky nav mirrors those same numbers and highlights the current step as you scroll, acting as the control plane a person watching an agent run would use to jump to any node.
- The projects grid renders each project as a call → result pair: one line stating the problem taken in, one line stating what she built and shipped — never a loose paragraph describing tools used, which is the thing this decision explicitly forbids.
- The skills list is framed as the tools available to the run — a flat inventory, not a decorative cloud.
- The contact section breaks the pattern on purpose: it carries the accent colour and a distinct marker reading as "awaiting input," because it is the one step in the trace that is not automated — the human-in-the-loop gate, made visible instead of filed at the bottom as an afterthought.
- At 390px it survives by: the thread collapses to a slim left rail of step numbers that stays on screen; each step goes full width stacked; every call → result pair keeps an internal rule between the call line and the result line so the tool-call structure never collapses into an ordinary paragraph.

## Tokens
```css
:root {
  --bg: #0f1115;
  --fg: #e8e6e1;
  --accent: #f2b134;     /* --fg on --bg = 15.19:1, --accent on --bg = 10.03:1 — both computed, both pass */

  --text-xs:   0.75rem;
  --text-sm:   0.875rem;
  --text-base: 1.125rem;
  --text-lg:   1.5rem;
  --text-xl:   clamp(2rem, 1rem + 4vw, 3.25rem);
  --text-2xl:  clamp(3rem, 1.5rem + 6vw, 6rem);

  --space-1: 0.5rem;
  --space-2: 1rem;
  --space-3: 1.75rem;
  --space-4: 3rem;
  --space-5: 5rem;
  --space-6: 8rem;

  --measure: 47ch;
}
```

### Contrast, computed
`L = 0.2126R + 0.7152G + 0.0722B` on linearised channels; `ratio = (L1+0.05)/(L2+0.05)`.

- `--bg #0f1115`: L = 0.005455
- `--fg #e8e6e1`: L = 0.79198 → ratio vs bg = (0.79198+0.05)/(0.005455+0.05) = **15.19:1**
- `--accent #f2b134`: L = 0.50585 → ratio vs bg = (0.50585+0.05)/(0.005455+0.05) = **10.03:1**

Both clear WCAG AA (4.5:1) with margin.
