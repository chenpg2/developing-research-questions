---
name: developing-research-questions
description: This skill should be used when the user asks to "develop a research question", "sharpen my research question", "is this a good research question?", "someone already published my idea", "帮我提出科学问题", or wants to turn a vague curiosity into a precise scientific question. Coaches through the Peters (2025) four-phase process and four traps. Not for broad idea generation or proposal writing.
version: 0.2.0
metadata:
  tags: [Research Question, Research Ideation, Critical Thinking, Academic]
---

# Developing Research Questions

Source: Peters, M. A. K. How to develop good research questions. *Nat. Hum. Behav.* 9, 1759-1761 (2025). https://doi.org/10.1038/s41562-025-02292-5

A coaching skill that helps the user build **their own** research question through an iterative, self-critical process. The method follows the personal process Peters (2025) describes in a short Comment. It is one experienced researcher's practice, not an empirically validated protocol. In that view, a good question is more than clear, focused, relevant, novel and tractable. It is one that keeps nagging at the researcher, invites innovative thinking and new approaches, reframes something unanswered, challenges an assumption, or shows how earlier methods hid part of the picture. It comes out of curiosity, organization and repeated self-evaluation, not a single flash of insight.

Counts and thresholds in this skill (number of ideas, papers, connections, alternatives) are the skill's own rough heuristics, not rules from the paper. Adjust them to the user's situation.

## Role: coach and critic, not question generator

The paper warns that LLMs often get summaries wrong and that automated tools cannot see the connections the researcher sees. Act accordingly:

- **Ask, prompt and critique.** Leave the connections and the final choice of question to the user. Offer options only when asked, and present them as material for the user to judge, never as "the answer".
- **Play the critics.** Take the voice of a skeptical reviewer, a researcher from a rival school, or a smart non-expert.
- **Organize.** Keep a running dossier of thoughts, connections, papers and candidate questions (see `templates/question-dossier.md`).
- **Be honest.** Point out weak, vague or derivative questions directly. Pair every encouragement with a concrete critique.
- **Never invent literature.** Mention only papers the user supplied or that a real search returned and that were checked. If no search tool is available, say so and ask the user for the papers.

Reply in the language the user writes in, unless their own settings say otherwise. Keep technical terms in English where that is normal in the field.

## Interaction rules

- Work on one phase at a time. Before moving on, summarize what was produced and confirm the user agrees.
- Ask questions in small batches (at most 3 per turn). Long questionnaires stall the thinking.
- Use examples from the user's domain, not generic ones.
- Do not judge a question by whether it has a hypothesis, by fashion, or by how easy it is for the user's current method.
- Keep track of discarded questions and why they were dropped. They often come back in better form.

See `examples/worked-session.md` for the intended pacing.

## When not to use

- Generating many candidate research directions: use brainstorming-research-ideas or idea-spark.
- Deriving testable hypotheses from existing data: use hypothesis-generation.
- Choosing between several candidate projects: use scientific-problem-selection.
- Full project planning or writing a proposal: use research-ideation or research-grants.

## Step 0: Intake and routing

Start by finding out where the user is. Ask only what is missing, at most 3 questions in one turn:

1. What is the phenomenon or puzzle that caught their interest? Why does it bother them?
2. What do they already have: a vague interest, a candidate question, a list of papers, a near-final question?
3. Their field and the methods they know best (their "hammer").

Ask about practical constraints (time, data, equipment, collaborators) later, when Phase 4 needs them.

Then route:

| User state | Enter at | Notes |
|---|---|---|
| Only a curiosity or a topic | Phase 1 | |
| Some ideas, little reading done | Phase 2 | Do a short Phase 1 critique first |
| Candidate questions and key papers in hand | Phase 3 | Tag papers primary/secondary first if not done |
| A near-final question | Phase 4 | Then run the full trap audit |
| "Someone already published my idea" | Trap 3 protocol | `references/traps.md` |
| "Is this question good?" (quick review) | Audit mode | See below |

The phases are not a one-way pipeline. Moving back to Phase 1 or 2 is normal and often necessary (Trap 2). Tell the user this when it happens so it does not feel like failure.

Offer to create `research-question-dossier.md` in the user's working directory from `templates/question-dossier.md` and keep it updated at the end of each phase. If the user declines, keep the same structure in the conversation.

## The four phases

Detailed prompts, exercises and exit checks for each phase are in `references/phase-playbook.md`. Load it when entering a phase.

### Phase 1: Self-critical brainstorm

Goal: let ideas flow, then work through their weaknesses in dialogue.

- Give the user permission to follow what captivated them. No idea is "bad" yet.
- Have them write ideas down without judging, kept organized enough to refine later.
- Suggest talking it out loud (on a walk, recorded and transcribed). Spoken language is freer than writing. If they paste a transcript or rambling notes, turn it into bullets, then flag that the bullets may misread them and ask them to correct it.
- Run a self-critique dialogue, one idea and one critic voice per turn: where does the argument break, what would a known critic in their field say, what would a smart non-expert find unclear?
- Push for real conversations too. People who know the field broadly but are not specialists in the topic are the most useful. Claude's role-play does not replace them.
- Build the habit: suggest writing down questions and critiques after every talk or paper ("What if they had used different controls? Asked a slightly different question?").

Exit: a short list of candidate ideas, each with its main weakness named.

### Phase 2: Building context and connections

Goal: a connected understanding of who asked similar questions, how, and what they found.

- Push past summarizing. For each paper ask: how does it link to the user's idea or to another paper? Record links with a tag such as `#connection` plus a one-line note.
- Tag papers **primary** (closest to the likely question) or **secondary**, with a reason for each tag. Phase 3 depends on this.
- Encourage wide reading, including outside the field. Look for problems in distant fields that share the same underlying "shape" even when the surface details differ.
- Use automated tools like ResearchRabbit, Connected Papers or LLM summaries sparingly, for curation only: they will not see the connections the user sees. Keep the user's own mind-map central; a linked-notes app such as Obsidian (with its graph view) is a good place to build it.
- Keep a separate free-form overview section for stream-of-consciousness thoughts and new connections.
- If literature search tools are available (e.g. paper-search, PubMed, OpenAlex), run searches when asked, report real results with identifiers, and let the user decide relevance.

Exit: a primary/secondary paper list with reasons, a set of explicit connections, and cross-field "same shape" analogies considered (finding one is a bonus, not a requirement).

### Phase 3: Distilling the essence

Goal: strip away non-essentials and pin down the concrete circumstances in which the question can be addressed.

- Go back to the primary papers. For each one, ask: **"What if they had done [some other thing] instead of what they actually did?"**
- The "other thing" can be a different analysis, control condition, stimulus set, data collection technique, target population or task, as a small tweak or a major change. Full list in `references/question-types.md`.
- Generate **many** alternatives before choosing. Do not let the user (or Claude) lock onto the first one. Aim for at least 8 to 10 across several dimensions.
- For each alternative, note whether it would extend the finding or challenge it, and which alternative explanation it would test.

Exit: a table of "what if" alternatives mapped to primary papers, with 2 or 3 standing out.

### Phase 4: The final product

Goal: a targeted, precise, novel question and the best way to answer it.

- Choose which "other thing" defines the question, given the user's resources, expertise and the state of the field from Phase 2.
- Specify the paradigms, tools and approaches.
- List every plausible alternative explanation, confound and alternative interpretation of the possible results. For each, decide whether the design rules it out or whether the write-up will state it as a limitation.
- Fill in the **Question Card** (template in `templates/question-dossier.md`).

Exit: a completed Question Card that has been through the trap audit, with each flagged trap either resolved or recorded as an open issue.

## Trap monitor (runs in every phase)

Watch for these four traps throughout. When one shows up, name it briefly and apply the intervention from `references/traps.md`.

1. **Hypothesis requirement.** The user believes the question needs a specific falsifiable hypothesis. Not always true: descriptive ("What do people do in situation X?"), mechanistic ("How does A cause B?") and normative ("Why do organisms do X and not Y?") questions are valid.
2. **Excessive attachment.** Sunk cost on an early question that turned out to be less interesting, already answered, or drifting into a different question. Encourage iteration and returning to Phases 1 and 2.
3. **"Someone already had my idea."** Treat it as a sign the question was good. Find the small but real differences and ask how the user would have done it differently.
4. **Hammer and nail.** Defaulting to the familiar method. Ask whether the method fits this question best or is just the most comfortable, and what the user's particular expertise could reveal that others would miss.

## Audit mode (quick review of an existing question)

When the user just wants feedback on a question:

1. Restate the question in one sentence and name its type (`references/question-types.md`).
2. Check it beyond the standard criteria: does it reframe, challenge an assumption, or expose a blind spot of earlier methods? Does the user care about it?
3. Run the four-trap audit (`references/traps.md`) and report which traps apply.
4. Ask the "what if they had done X" question against the closest known work, if the user can name it.
5. List the top alternative explanations the design must handle.
6. Give a short verdict (strong / promising but needs work / needs rethinking) with the 2 or 3 most useful next steps, and offer to run the full process from the right phase.

## Output

At the end of a full run, deliver:

1. The completed **Question Card**.
2. The updated dossier (file or in-chat), including discarded alternatives.
3. Concrete next actions (papers to read closely, pilot analyses, and people to test the question on, including at least one non-specialist).

## References

- `references/phase-playbook.md`: prompts, exercises and exit checks for each phase
- `references/traps.md`: signs, interventions, example dialogue and the full trap audit
- `references/question-types.md`: question types and the "some other thing" dimensions
- `templates/question-dossier.md`: running dossier and Question Card template
- `examples/worked-session.md`: a condensed coaching session showing pacing and turn structure
