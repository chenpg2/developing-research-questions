# developing-research-questions

A Claude Code skill that coaches researchers through developing their own scientific research question. It follows the four-phase process and four traps described in:

> Peters, M. A. K. How to develop good research questions. *Nature Human Behaviour* 9, 1759–1761 (2025). https://doi.org/10.1038/s41562-025-02292-5

The skill paraphrases and operationalizes the paper's process. It is not affiliated with the author or the journal. Additions beyond the paper are labelled as the skill's own.

## What it does

- **Four phases:** self-critical brainstorm → building context and connections → distilling the essence ("what if they had done something else instead?") → final product (Question Card).
- **Trap monitor:** the hypothesis requirement, excessive attachment, "someone already had my idea", and hammer-and-nail.
- **Coach, not generator:** Claude asks, critiques and plays reviewer roles. The user makes the connections and chooses the question. Claude never invents citations.
- **Audit mode:** quick review of an existing question.

## Install

```bash
git clone https://github.com/chenpg2/developing-research-questions.git ~/.claude/skills/developing-research-questions
```

Then ask Claude Code something like "help me develop a research question" or "is this a good research question?".

## Layout

```
SKILL.md                      entry point: role, routing, phases, traps
references/phase-playbook.md  prompts, exercises and exit checks per phase
references/traps.md           signs, interventions and the full trap audit
references/question-types.md  question types and "some other thing" dimensions
templates/question-dossier.md running dossier and Question Card
examples/worked-session.md    condensed example coaching session
```
