# Worked Session (condensed)

A fictional, condensed coaching session to show pacing: at most 3 questions per turn, one critic voice at a time, the user making the choices, and traps named when they appear. Long stretches are summarized in *[brackets]*. The papers are placeholders ("Paper A", "Paper B"). In a real session, use only papers the user supplied or that a real search returned.

Domain: computational biology. The user writes in English.

---

## Step 0: Intake

**User:** I keep seeing single-cell papers claim a "transitional" cell state between two cell types. I'm not sure I believe it. Can you help me turn this into a research question?

**Claude:** Happy to. Three questions to start:
1. What exactly makes you doubt the transitional state? Something you saw in data, or in how papers argue for it?
2. What do you have so far: just the doubt, some candidate questions, or papers you've already read closely?
3. What methods do you know best?

**User:** I've reanalyzed two public datasets and the "transitional" cluster looks different depending on preprocessing. I have only the doubt and those two papers. I mostly do trajectory inference and clustering in Python.

**Claude:** So: a doubt grounded in your own reanalysis, two papers, and trajectory inference as your main tool. I'd start with a short Phase 1 to get your ideas out and pressure-test them, then move into reading (Phase 2). Shall I keep a dossier file for this as we go?

**User:** Yes, please.

*[Claude creates `research-question-dossier.md` from the template.]*

---

## Phase 1: Self-critical brainstorm

**Claude:** Write down every version of the doubt you can think of, without judging. Rough is fine. If talking it through on a walk works better for you, record it and paste the transcript.

**User:** *[pastes a rambling voice-memo transcript]*

**Claude:** Here's my bullet version. Tell me where I've misread you:
- Idea 1: the transitional cluster is a preprocessing artifact (normalization, number of highly variable genes).
- Idea 2: it's real, but it is a mixture of doublets and two pure states.
- Idea 3: "transitional" is inferred from pseudotime, which assumes continuity, so the reasoning is circular.
- I'm unsure about the "cell-cycle" remark: did you mean cell cycle as a confound, or as a separate idea?

**User:** Cell cycle as a confound inside idea 1. The rest is right.

**Claude:** Let's critique one idea at a time. Start with idea 3. Speaking as a skeptical reviewer: "Pseudotime methods don't assume a continuum. They're often run *because* lineage tracing shows one." How would you answer?

**User:** Fair for some papers, but the two I read have no lineage tracing.

**Claude:** Then idea 3 may be narrower than it first looked: "inferred without independent evidence of continuity". I've noted that as its weakness. Next, the smart non-expert voice on idea 1. Can you explain in three sentences why preprocessing could create a cluster?

*[The user explains. Claude reports one unclear step, and the user fixes it. Idea 2 gets the same treatment.]*

**Claude:** Before Phase 2, one suggestion: walk a colleague who isn't in single-cell through idea 1 this week. If it survives their questions, it's clearer than either of us can judge alone.

**Dossier after Phase 1:** three ideas, each with its main weakness named, plus a note to talk to a colleague.

---

## Phase 2: Building context and connections

*[The user reads 6 papers over several sessions. Claude runs literature searches when asked and reports only real results with DOIs.]*

**Claude:** For Paper A, don't summarize it. What does it connect to?

**User:** `#connection` Paper A → idea 2: they removed doublets, but with a tool that has a known blind spot for doublets made from two similar cell types.

**Claude:** Good link. Is Paper A primary or secondary for you, and why?

**User:** Primary. It's the strongest claim of a transitional state in my system.

**Claude:** One wider question. Strip out the biology words: what is the abstract problem?

**User:** Deciding whether a cloud of points between two clusters is a real intermediate population or a blend of the two.

**Claude:** Which other fields face that problem? You don't need to find one. It's worth a few minutes of thought.

**User:** Mixture modeling in astronomy, maybe. Spectra that blend two sources.

*[The user notes it as a "same shape" lead.]*

**Trap 2 appears.** Halfway through reading, the user finds that idea 1 is largely answered by a benchmarking paper.

**User:** But I've already spent two weeks on the preprocessing angle...

**Claude:** This looks like the attachment trap. The two weeks aren't lost: you now know what the benchmarks covered. If you saw idea 1 fresh today, knowing the benchmark exists, would you pick it?

**User:** No. Idea 2 is more interesting now.

*[Idea 1 moves to "Dropped questions" with the reason. Its cell-cycle confound note is kept.]*

---

## Phase 3: Distilling the essence

**Claude:** Back to Paper A. What if they had done something else instead of what they actually did? List as many as you can before we judge any of them. Think about analysis, controls, data collection and population.

*[The user lists 9 alternatives. Claude adds 2, marked as Claude's suggestions, on the "control condition" dimension. Excerpt:]*

| Primary paper | What they did | What if instead ... | Dimension | Extends / challenges | Alternative explanation tested |
|---|---|---|---|---|---|
| Paper A | Generic doublet removal | Simulate same-type doublets and check if they land in the transitional cluster | Control | Challenges | Doublet blend |
| Paper A | One tissue sample | Use a sample where a lineage tracer is available | Data collection | Extends | Circular continuity |
| Paper B | Pseudotime ordering | Fit a two-component mixture model per cell | Analysis | Challenges | Blend vs intermediate |

**Claude:** Which two or three stand out to you, and why?

**User:** Simulated same-type doublets as a control, combined with the mixture-model test. Together they directly separate "blend" from "intermediate".

---

## Phase 4: The final product

**Trap 4 check.** The user's first draft approach is "run my trajectory pipeline with a doublet filter".

**Claude:** Quick hammer-and-nail check. Would you still choose trajectory inference here if it weren't the method you know best? The question is "blend or intermediate", and trajectory inference assumes an intermediate exists.

**User:** Fair. The mixture-model test should come first. Trajectory inference only comes in if a real intermediate survives that test.

**Claude:** Now let's list the alternative explanations, and I'll argue the reviewer side. Suppose your mixture model calls the cluster a "blend". What else could produce that result?

*[They fill the alternative-explanations table together: ambient RNA, cell-cycle confound carried over from the dropped idea 1, a mixture model that is too flexible. Each is marked as ruled out by design or stated as a limitation.]*

**Question Card (excerpt)**
- **Research question:** Are the "transitional" cells reported between type X and type Y in tissue Z a distinct intermediate population, or a blend of the two endpoint states produced by same-type doublets and ambient RNA?
- **Question type:** mechanistic ("how does the transitional signal come about?"). No effect-size hypothesis required.
- **What is new:** relative to Papers A and B, it adds same-type doublet simulation as a control and tests blend vs intermediate directly, instead of assuming continuity.
- **Trap audit:** 1 pass · 2 pass (idea 1 dropped, reason recorded) · 3 pass (difference from Paper A stated) · 4 pass (method order justified)
- **Next actions:** read Paper A's supplement on doublet removal closely; run a pilot simulation on one dataset; discuss with the colleague from Phase 1.
