# The Four Traps

Each trap has signs to watch for, an intervention, and a short example. Name the trap plainly when it appears ("This looks like the hammer-and-nail trap"), then help the user out of it.

---

## Trap 1: The "hypothesis requirement"

**Belief:** every good question needs a specific, falsifiable hypothesis (e.g. "intervention X will improve outcome Y by Z").

**Signs**
- User forces a directional prediction onto an exploratory or descriptive question.
- User drops an interesting question because "I can't state a hypothesis".
- The stated hypothesis is vague or arbitrary (an effect size picked from nowhere).

**Intervention**
- Explain that expectations help, but they need not be an exact effect-size or comparison hypothesis.
- Identify the real question type (`question-types.md`): descriptive "what", mechanistic "how", normative "why". Each can give valuable insight without a specific falsifiable hypothesis.
- Ask: "What would you learn from the answer even if you had no prediction?"
- If the user's venue or funder requires hypotheses, help them state honest expectations or pre-registered exploratory aims instead of inventing a prediction (skill's addition, not from the paper).

**Example** (illustrative; in a session, use the user's own domain)
> User: "I want to know how lab members actually use shared data repositories, but I don't have a hypothesis."
> Claude: "That's a descriptive question: 'What do researchers do when ...?'. It doesn't need a falsifiable prediction to be worth asking. What would change in your field if you had a good description?"

---

## Trap 2: Excessive attachment to the question

**Belief (unstated):** "I've put so much into this question that I must keep it."

**Signs**
- Reading shows the question is already answered, but the user keeps adding conditions to save it.
- The question has quietly turned into a different question, while the user still describes it the old way.
- The user dismisses critiques with "but I've already spent months on this".
- Excitement has gone; the user continues out of obligation.

**Intervention**
- Name the sunk-cost pattern kindly.
- Separate the work from the question: reading and thinking done so far is not lost; it is the context for the next question.
- Offer to go back to Phase 1 or 2 with what is now known. Make clear that cycling back is part of the process, not starting over.
- Ask: "If you'd never seen the original question, would you choose this one today?"
- Record the dropped question and why in the dossier.

---

## Trap 3: "Oh no, someone already had my idea!"

**Reaction:** disappointment or despair after finding a paper that seems to ask the same thing.

**Signs**
- User wants to abandon the topic right after finding a similar paper.
- User describes the paper as "exactly my idea" without having read it closely.

**Intervention (protocol)**
1. Reframe: someone else working on it means the question was good enough to be worth asking.
2. Read the paper closely together. Fill this comparison:

| Aspect | Their paper | User's idea | Same / different |
|---|---|---|---|
| Phenomenon / target | | | |
| Population / system | | | |
| Method / technique | | | |
| Controls | | | |
| Analysis | | | |
| Alternative explanations considered | | | |
| Claims made | | | |

3. Ask: "Would you have approached it exactly the same way? Where would you have done it differently or better?"
4. Run the Phase 3 "what if they had done ..." exercise with this paper as a primary paper.
5. Look for: different techniques, alternative explanations they did not consider, a slightly different phenomenon, populations they did not cover.
6. Decide: refine the question, extend their work, or (rarely) move on. Record the reason.

---

## Trap 4: The "hammer and nail" trap

**Belief (unstated):** "My method is the way to study this."

**Signs**
- The method is decided before the question is clear.
- Every candidate question in Phase 3 uses the same technique.
- The user cannot explain why their method beats alternatives for this question.
- Phrasing like "I'll apply [my model / my technique] to [new domain]" with no question beyond that.

**Intervention**
- Do not tell the user to drop their expertise. Their specific knowledge lets them ask questions others would not think of.
- Ask the two questions together:
  - "Would you still pick this method if it weren't the one you know best?"
  - "What can your method show here that other people's methods would miss?"
- List 2 or 3 alternative approaches someone from another field would use, and compare honestly.
- Look for the combination: where does the user's method plus active self-reflection reveal something the standard approach misses?

---

## Full trap audit (for Phase 4 and audit mode)

| Trap | Check | Status | Note |
|---|---|---|---|
| 1 Hypothesis requirement | Is a hypothesis forced where the question is descriptive / mechanistic / normative? | pass / flag | |
| 2 Attachment | Would the user pick this question today, starting fresh? Is it still the same question? | pass / flag | |
| 3 Already done | Is the difference from the closest prior work stated concretely? | pass / flag | |
| 4 Hammer and nail | Is the method justified for this question, not only familiar? | pass / flag | |
