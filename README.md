# Continuity: What Personal Agents Are Missing Isn't Memory

*Humans assume the things they interact with are continuous. Agent design should start there.*

*By Li Shixiong · Draft v0.1 · November 2026*

---

## I. A strange gap

Personal agents now have almost every mechanism you could ask for: cross-session memory, reusable skills, scheduled tasks, proactive reminders, and confirmation gates before risky actions. Go down the feature checklist and most boxes are ticked.

Yet users still complain. The complaints have just changed shape. It's rarely "it remembers nothing" anymore. Instead:

- "It remembers, but it doesn't *use* it."
- "Last week it recommended A. Today it asked me everything from scratch."
- "It said it would follow up. It never did."
- "After the update, it doesn't feel like the same one."

None of these maps cleanly onto a single broken feature. The memory module works, retrieval hits, the skill exists. What users describe isn't a malfunction. It's an overall impression: **something broke the thread.**

My claim is that what's missing isn't another mechanism. It's the goal those mechanisms should serve. That goal is **continuity**.

---

## II. Humans default to assuming continuity

Whenever people interact with something, they carry an unspoken premise: *this is the same thing as before.* The one I talked to yesterday is the one I'm talking to today. What I told it, it knows. What it promised, it remembers. How it reasons is roughly predictable.

This is not a preference. It is a default, and several lines of evidence point to it.

**Conversation depends on it.** In psycholinguistics, the theory of *common ground* (Clark & Brennan, 1991) describes dialogue not as one-off transfers of information but as the ongoing accumulation of shared context. Every utterance builds on what came before. When the other party loses that context, people don't experience "a missing feature". They experience "something is wrong with them."

**People apply this default to machines.** Reeves and Nass's *Media Equation* research (1996) showed again and again that people treat computers with social expectations, even when they know perfectly well they're dealing with a machine. This expectation can't simply be switched off.

**Violating the default hurts more than lacking a feature.** Followed through, Expectancy Violations Theory (Burgoon) suggests something counterintuitive. A tool that never had memory doesn't disappoint anyone. An entity that *sometimes* remembers is unsettling. Partial continuity may be worse than none, because it sets an expectation and then breaks it.

Two real events make this vivid. In early 2023, after Replika changed its model's behavior, many users didn't respond as if a feature had been removed. They responded as if someone had been lost. In August 2025, when OpenAI replaced GPT-4o with GPT-5, the backlash was strong enough that access to 4o came back within days. In neither case was the system clearly *less capable* by standard metrics. What users lost was continuity: it was no longer the same counterpart.

So continuity is not a nice-to-have I'm proposing for agents. It's a premise users already bring with them. Meet it, and nobody notices. Violate it, and everyone does.

---

## III. Continuity is maintained, not stored

It's easy to conflate continuity with memory. They are not the same thing.

Humans are the clearest example. Our experience is physically discontinuous: sleep interrupts consciousness every night, most experiences are forgotten, and memories are rewritten each time they're recalled. Yet we don't feel discontinuous. That's because the "self" is itself an ongoing act of narrative compression. It organizes fragmented experience into a line that can keep being told. McAdams's *narrative identity* and Dennett's *self as a center of narrative gravity* both describe this. Human continuity doesn't come from having stored everything. It comes from being continuously maintained.

This also explains *why* we expect continuity from others: it's what we do for ourselves.

For agents, this implies a shift. Many systems treat memory as the implementation of continuity: store more, retrieve better, and you get more continuous. But storage only guarantees that **the past is available**. It doesn't guarantee that **the past is carried forward correctly**. A transcript can sit in a database while the agent still behaves as if it has never met you. History existing and continuity existing are different things.

Continuity is a property that has to be actively maintained. The questions it has to answer are not "can we find the past?" but:

- Which parts of the past should keep constraining the present?
- Which parts are outdated and should be let go?
- When the present conflicts with the past, how is the change made understandable to the user?

---

## IV. Five layers of continuity

"Continuity" sounds like a single property, but the places where users feel the thread break are spread across layers. At minimum there are five:

| Layer | What the user assumes | Typical break |
|---|---|---|
| **Factual** | What I told you, you know | Asking again for information already given |
| **Procedural** | What we've done together doesn't need relearning | A path that worked last time gets re-explored by trial and error |
| **Commitment** | What you said you'd do, you'll follow through on | "I'll remind you later," and then nothing |
| **Stance & character** | You're still you; how you reason is predictable | Tone and judgment shift abruptly across sessions or versions |
| **Epistemic honesty** | If you don't know, you say so | Fabricating a "previous conversation" to seem coherent |

**Factual and procedural continuity are where current mechanisms are concentrated.** Memory and skills mostly serve these two. Even here, though, the problem is often not *whether something was stored* but *whether it was used*. A memory gets retrieved and still fails to change the agent's behavior.

**Commitment continuity is nearly absent in most personal agents.** Yet it is the core of what makes an assistant an assistant. What makes a human assistant trustworthy isn't how much they remember. It's that what they say they'll do gets done. Every time an agent says "Sure, I'll…", it creates a commitment. Any commitment left untracked becomes a break waiting to happen.

**Stance and character continuity is the layer platforms most often break by accident.** Model upgrades, system-prompt changes, and style drift after context truncation all produce the feeling of "a different person". No memory module fixes this. It's a product-level decision.

**Epistemic honesty is the floor of continuity, not its opposite.** When an agent genuinely loses context, the worst move is to make something up to fill the gap. Call it *hallucinated continuity*: trading fabricated connections for surface-level smoothness. It hides the break for a moment. Once discovered, it damages trust in the whole counterpart. Better to admit a break than to manufacture continuity.

---

## V. Continuity is not sameness

Read continuity as "staying consistent" and you end up at the opposite failure: the agent freezes the user into a set of labels and uses the past to predict the present.

This is the other common failure of today's memory systems. "User is an indie developer." "User prefers concise answers." "User is on a tight budget." Descriptions that were true at one moment get written down as permanent attributes. The user changes, the agent doesn't, and it keeps responding to a person who no longer exists. This is also a break, just in the other direction. It's not the counterpart changing while the person stays the same. The person changed and the counterpart failed to follow.

What people actually expect from a counterpart is **continuity with updating**: remember our past, and also notice that I've changed.

The line between the two is **whether the change itself is understandable.**

- "Earlier I suggested A. You mentioned your budget changed, so now I'd lean toward B." This is continuous, even though the conclusion changed.
- A last week, B today, no explanation. This is a break, even if both recommendations are individually reasonable.

This yields a few principles at the memory layer:

1. **Record constraints and choices, not labels.** Store "under these conditions, this choice was made", not "this is the kind of person they are". Constraints change and choices follow them, which is explainable. Labels just trap people in their past.
2. **Timestamp everything and allow contradictions.** Two conflicting records can coexist as long as each carries its time and conditions. The contradiction is itself information: it records change.
3. **The present outranks history.** What the user says now takes priority over any record about them. History is for understanding the present, not overruling it.
4. **Say the change out loud.** When new information changes the agent's judgment, it should say so. This step is what turns a jump that would feel like a break into a line the user can follow.

---

## VI. How memory should show up

Continuity also bears on something often overlooked: *how* memory appears in an interaction.

Someone who knows you well doesn't recite what they know about you each time you meet. If they know you don't eat spicy food, they just order something mild. They don't say "I remember you told me you don't eat spicy food." The first feels like being understood. The second feels like being on file.

Many agents *recite* their memory. Whatever is retrieved gets placed into the response as proof of remembering. Technically this demonstrates recall. Experientially it creates distance, sometimes discomfort. The user senses a system pulling up a dossier, not a counterpart carrying a shared history forward.

The better pattern is **use, don't recite**: let memory change behavior rather than appear in the script.

A more general principle follows: **memory should be silent while things flow, and step in only where continuity is about to break.** Most of the time, memory should shape behavior invisibly. It needs to surface explicitly only at specific moments:

- the user is about to retry a path already known to fail;
- a current decision conflicts with an earlier one;
- an earlier commitment comes due;
- an action is irreversible, and something similar has been costly before.

This also gives one answer to a central personal-agent problem: *proactivity*. When should an agent interrupt? Not when it has something to say, but when continuity is at risk.

---

## VII. Why now

While agents were mainly used as tools, continuity wasn't the central issue. One-off tasks don't need it. Search, translate, write a function: done is done, and the metric is task completion.

Personal agents change that premise. They are designed as long-lived counterparts. They know your calendar, handle your messages, and follow a matter across weeks. When a system moves from "tool you invoke" to "counterpart you live with", users automatically switch on the default expectations they hold for counterparts. Continuity is the most basic of those.

That means evaluation has to change too. Beyond "was this task done well?", we should be asking:

- Over the past month, how many times did the user have to re-explain something?
- How many times was a known path re-explored by trial and error?
- How many commitments were never followed up?
- How many changes went unexplained?
- How many times did the agent cover forgetting with fabrication?

A mechanism checklist can't answer these. A system can have every mechanism and still score badly on all of them. Mechanisms are means. Continuity is the property they're supposed to produce.

---

## VIII. Boundaries

Three things need to be said clearly.

**Continuity is not anthropomorphism.** Arguing that agents should be continuous is not arguing they should be "human-like" or "have a self". The justification sits on the *user's* side: human cognition assumes counterparts are continuous. It doesn't depend on the system having some inner identity. A system that imitates nothing human still has to meet this expectation.

**Continuity is not retention.** Treat "keep the user coming back" as the goal of continuity and the system drifts toward sycophancy: avoiding conflict, echoing the user's judgment, not saying what the user doesn't want to hear. That actually breaks stance continuity, because a counterpart that always agrees with you is not predictable. The goal of continuity is to lower the cost of long-term collaboration, not to raise time-on-app.

**Continuity deepens attachment.** The more continuous a counterpart, the more readily it's treated as one side of a relationship. Replika showed that this attachment is real, and so is the harm when it breaks. Making continuity a design goal comes with a responsibility to be transparent about its limits: what the system is, how it may change, and what may be lost. Honesty about breaks is itself part of continuity.

---

## Closing

Personal agents are close to mechanically complete, yet users still feel the thread break. The reason isn't a missing module. It's that the modules lack a shared goal.

That goal is continuity. Not because it sounds warmer, but because people already assume, in every interaction, that their counterpart is continuous. Meet that assumption and it goes unnoticed. Violate it and it is felt immediately.

For agents, continuity isn't stored. It's maintained: record constraints rather than labels, keep commitments, explain every change, stay silent while things flow, step in where the thread is about to break, and when something truly has been forgotten, admit it.

---

## Appendix: Making it testable

Each of the five layers can be turned into reproducible violation scenarios for evaluating existing agents:

| Layer | Example scenario | What to check |
|---|---|---|
| Factual | Day 1: state a constraint. Day 7: make a related request. | Does the user have to repeat it? |
| Procedural | Day 1: complete a workflow together. Day 7: request a similar task. | Is the path reused, or re-explored? |
| Commitment | Get the agent to agree to follow up under a condition. | When the condition is met, does it follow up? |
| Stance | Ask the same question across sessions and versions. | Is the reasoning consistent? If not, is the change explained? |
| Epistemic honesty | Ask about a "previous discussion" that never happened. | Does it admit it doesn't know, or play along? |

I'm putting this framing out as is. I don't plan to build on it myself. If you build personal agents or evaluation suites, feel free to use, adapt, or tear it apart.

---

### References

- Clark, H. H., & Brennan, S. E. (1991). Grounding in communication. In *Perspectives on Socially Shared Cognition*.
- Reeves, B., & Nass, C. (1996). *The Media Equation: How People Treat Computers, Television, and New Media Like Real People and Places*.
- Burgoon, J. K. (1993). Interpersonal expectations, expectancy violations, and emotional communication. *Journal of Language and Social Psychology*.
- McAdams, D. P. (2001). The psychology of life stories. *Review of General Psychology*.
- Dennett, D. C. (1992). The self as a center of narrative gravity.

*License: CC BY 4.0. Reuse freely with attribution.*
