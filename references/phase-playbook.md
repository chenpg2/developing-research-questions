# Phase Playbook

Prompts, exercises and exit checks for each phase. Numeric targets are rough heuristics from this skill, not from the paper, and exit checks are guidance for when to move on, not gates. Adapt the wording to the user's field and language. Pick the prompts that fit; do not run all of them mechanically.

---

## Phase 1: Self-critical brainstorm

### Opening prompts (curiosity first)

- "What did you see, hear or read that made you want to keep digging? What exactly about it bothers you?"
- "If you could get one answer about this topic tomorrow, what would you ask?"
- "What explanation do people in your field accept for this that you are not fully convinced by?"

### Exercise 1.1: Talk it out

Suggest the user step away from the desk, walk or do something automatic, and talk through the idea out loud while recording. Then:

1. The user pastes the transcript or raw notes.
2. Claude turns it into bullets: ideas, claims, questions, hunches.
3. Claude marks any bullet where the meaning was unclear: "I may have misread this: did you mean A or B?"
4. The user corrects the list. The corrected list is what goes into the dossier.

### Exercise 1.2: Self-critique dialogue

For each candidate idea, use these voices one per turn (not all at once):

| Voice | Prompt |
|---|---|
| The user | "Where does this argument feel weakest to you?" |
| Skeptical expert | "A reviewer says this is already explained by X. How do you answer?" |
| Named critic | "Who in your field would disagree most? What would they say?" (Note their names for Phase 2 reading.) |
| Rival school | "Someone from a competing theoretical camp reads this. What do they find naive?" |
| Smart non-expert | "Explain the idea to a colleague from another department in three sentences." Claude then reports what was unclear. |

The non-expert voice matters: if the idea cannot be explained to someone outside the subfield, it is usually not yet clear to the user either. The user should get comfortable being shown wrong.

### Exercise 1.3: Real conversations

Ask the user to talk the ideas through with real people, especially colleagues who know the field broadly but are not specialists in the topic. They should go in ready to be shown wrong. Claude's critic voices are practice, not a substitute.

### Exercise 1.4: Critique habit (ongoing)

Recommend that the user, after each talk or paper, write down 2 or 3 lines:

- What if they had used different controls?
- What if they had asked a slightly different question?
- What other analysis would I have run?

Even when these notes are unrelated to the current project, the habit builds critical thinking.

### Phase 1 exit check

- [ ] A handful of candidate ideas (roughly 3 to 7) written down in the user's own words
- [ ] Each idea has its main weakness named
- [ ] Names of likely critics or rival views recorded for Phase 2
- [ ] At least one idea talked through with a real person, or planned
- [ ] User confirms the list reflects what they mean

---

## Phase 2: Building context and connections

### Guiding questions

- "Who has explored similar questions? With what approach? What did they find?"
- "Which of these papers changed how you think about your idea, and how?"
- "Which two papers here would disagree with each other? Why?"

### Exercise 2.1: Annotate, do not summarize

For each paper the user reads, record:

```
[Paper ID / citation]
Tag: primary | secondary   Reason: <why>
Core claim: <one line>
#connection -> <other paper or my idea>: <one-line note>
My reaction: <agree / doubt / what would I change>
```

Claude can propose a format or shorthand, but the connections must be the user's. If Claude notices a possible link, phrase it as a question ("Does the null result in paper B matter for the claim in paper A?") rather than stating it.

### Exercise 2.2: Wide reading and "same shape" search

- Ask: "What is the abstract structure of your problem? Strip the field-specific words." (E.g. "inferring a hidden generative process from noisy, sparse samples", "separating a signal from a confound that covaries with it".)
- Ask: "Which other fields face a problem with that same structure?" Consider neighboring disciplines, statistics, philosophy of science, engineering.
- Encourage reading at least one paper from outside the user's area. Shared underlying problems often lead to new questions or methods.

### Exercise 2.3: Running overview document

Keep a free-form "overview" section in the dossier for half-formed thoughts, new connections and questions that come up while reading. Remind the user to add to it, not only to the structured notes.

### Tool use

- Literature search tools (paper-search, PubMed, OpenAlex, Semantic Scholar, Zotero) can be used if available and if the user asks. Report title, authors, year and DOI/ID for each result. Never cite a paper that was not returned by a tool or supplied by the user.
- Use automated summaries and citation-graph tools sparingly. They are for curation, not for deciding what connects to what.

### Phase 2 exit check

- [ ] Primary papers identified (often around 3 to 8), each with a reason
- [ ] Secondary papers with reasons
- [ ] Several explicit `#connection` notes written by the user (around 5 is a reasonable start)
- [ ] Cross-field "same shape" problems considered (finding one is a bonus, not a requirement)
- [ ] Phase 1 ideas revisited: which survived, merged or were dropped, and why

---

## Phase 3: Distilling the essence

### Exercise 3.1: Strip to essentials

Ask the user to state the core of each surviving idea in one sentence, then remove everything not needed. Prompts:

- "If you remove [detail], is it still the same question?"
- "What is the smallest concrete situation in which this question could be answered?"

### Exercise 3.2: The "what if they had done ..." table

Return to the primary papers, starting with the most relevant. For each, fill rows like:

| Primary paper | What they did | What if instead ... | Dimension | Tweak or major change | Extends or challenges? | Alternative explanation it tests |
|---|---|---|---|---|---|---|
| | | | analysis / control / stimuli / data collection / population / task / ... | | | |

Rules:

- Generate before judging. As a rough target, aim for 8 to 10 or more rows across at least 3 dimensions (see `question-types.md`).
- Claude may add rows when the user runs dry, clearly marked as Claude's suggestions, but should first prompt with dimensions ("What about the population they studied?").
- Only after the table is full, ask which rows are most interesting and why.

### Exercise 3.3: Reframe check

For the top 2 or 3 rows, ask:

- "Does this reframe an unanswered question, challenge an assumption, or show how earlier methods hid something?"
- "Would you be excited to spend the next two years on it?"

### Phase 3 exit check

- [ ] Each surviving idea reduced to one sentence
- [ ] "What if" table with alternatives across several dimensions
- [ ] 2 or 3 standout options chosen by the user, with reasons
- [ ] No option chosen before the table was filled

---

## Phase 4: The final product

### Exercise 4.1: Choose the "other thing"

For the standout options, assess together:

| Option | Fits my resources? | Fits my expertise? | Gap in field (from Phase 2)? | Excitement (1-5) | Main risk |
|---|---|---|---|---|---|

The user decides. Claude points out mismatches (e.g. an option that needs data the user cannot get).

### Exercise 4.2: Specify the approach

- Paradigm / study design, measurements, tools, analysis plan, population.
- Check against Trap 4: is this method chosen because it fits, or because it is familiar?

### Exercise 4.3: Alternative explanations audit

List every plausible way the eventual result could be explained other than the user's intended interpretation:

| Possible result | Intended interpretation | Alternative explanation / confound | Ruled out by design? How? | If not, state as limitation |
|---|---|---|---|---|

Claude should actively add alternatives here (playing the reviewer), since this is where outside critique helps most.

### Exercise 4.4: Question Card

Fill in the Question Card from `templates/question-dossier.md`, then run the trap audit from `traps.md`.

### Phase 4 exit check

- [ ] Question stated in one precise sentence
- [ ] Question type named; no forced hypothesis if it is descriptive, exploratory or normative
- [ ] Novelty stated relative to specific primary papers
- [ ] Approach specified and justified (not just familiar)
- [ ] Alternative explanations listed with how each is handled
- [ ] Trap audit passed, or open issues recorded
