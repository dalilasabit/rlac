---
title: "Assignment 3"
excerpt: "Can a Computer Separate Style from Content?"
layout: single
date: 2026-05-11
categories:
  - assignments
---
# What the Corpus Already Knew: Colonial Language in a Science Fiction Word Vector Space

Science fiction is supposed to be about the future. But the corpus of roughly 1,000 texts scraped from Project Gutenberg tells a different story — or rather, it reveals that the future these writers imagined was built from the vocabulary of the colonial past. Using word2vec models trained on this corpus, I queried three words: *alien*, *native*, and *race*. The results were not what I expected, and in some ways they were exactly what I should have expected.

This essay compares results across two models — `model_100d_w4` (100 dimensions, window size 4) and `model_300d_w8` (300 dimensions, window size 8) — and argues that the semantic space of this corpus is saturated with real-world imperial and racial ideology, not science-fictional imagination.

---

## Background: What the Models Are Doing

Word2vec learns meaning from context. It does not know what a word means in the way a dictionary does. It learns which words tend to appear near each other across millions of sentences, and it places those words close together in a high-dimensional vector space. The closer two words are in that space, the more similar their contexts are across the corpus.

This matters for interpreting the results. When *mongrel* appears in the same neighborhood as *native*, it is not a coincidence or a noise artifact. The model found that these words share contexts — that they tend to appear near the same other words across many texts. The corpus taught the model that.

Ted Underwood warns that this is also where distant reading can mislead. In "The Dangers of Distant Reading," he cautions that computational methods do not reveal objective truths about a corpus; they reveal patterns that a researcher then interprets. The patterns I found below are real, but what they *mean* is a claim I am making, not something the model tells me directly. That interpretive responsibility is mine.

---

## Query 1: *alien*

### Results

**`model_100d_w4` — Top neighbors:**

| Position | Words |
|----------|-------|
| 1–4 | alien, inhuman, ancient, animal |
| 5–8 | isolated, invisible, adult, indeterminate |
| 9–12 | humanoid, exotic, organic, anthropomorphic |
| 13–16 | individual, unbreakable, enemy, earthly |
| 17–20 | irrational, Termans, esthetic, ebony |
| 21–24 | obscenity, mythical, armful, arboreal |
| 25–28 | unsettled, unforgiving, appropriate, fearsome |
| 29–30 | expanding, atom | |

**`model_300d_w8` — Top neighbors:**

| Position | Words |
|----------|-------|
| 1–4 | alien, humanoid, inhuman, ancient |
| 5–8 | invisible, Terran, anthropomorphic, isolated |
| 9–12 | irrational, anomaly, animal, organic |
| 13–16 | "Mediterranean", exotic, armful, enemy |
| 17–20 | earthly, unthinkably, indeterminate, different |
| 21–24 | unforgiving, individual, embodied, unbreakable |
| 25–28 | peopled, invocation, embodied, ebony |
| 29–30 | instinctive, impervious | |

### Analysis

Both models agree on the core cluster: *inhuman, humanoid, anthropomorphic, ancient, organic, irrational, animal.* What this tells you is that the corpus constructs "alien" almost entirely through the body. Something is alien because it is measured against the human form and found deficient or strange. *Anthropomorphic* and *humanoid* sitting next to *inhuman* captures the tension perfectly — the alien is always being compared to the human as a baseline.

The 300d model adds *Terran* and *anomaly*, which are slightly more sci-fi in register. But it also surfaces *"Mediterranean"* and *ebony*, which pull the word back toward real-world racial geography. The richer model does not make the ideology disappear — it makes it more specific.

*Irrational* appearing in both models is worth pausing on. The alien, in this corpus, is not just physically different. It is cognitively subordinate. That is not a neutral semantic fact; it is an ideological one.

---

## Query 2: *native*

This is the most striking result.

### Results

**`model_100d_w4` — Top neighbors:**

| Position | Words |
|----------|-------|
| 1–5 | ancestors, Phoenician, farms, allies, traders |
| 6–10 | own, surrounding, deities, Waziri, tribe |
| 11–15 | dialect, Morocco, Bohemian, pilgrims, Altaic |
| 16–20 | nobility, royal, untravelled, ancient, tribes |
| 21–25 | mistress, overlordship, mongrel, Senegalese, mercenaries |
| 26–30 | arboreal, country, Spanish, clans, followers | |

**`model_300d_w8` — Top neighbors:**

| Position | Words |
|----------|-------|
| 1–6 | own, Altaic, farms, followers, tribes, Phoenician |
| 7–12 | tribe, mongrel, allies, traders, alien, dialects |
| 13–18 | dialect, neighbor, traders, alien, surrounding, ancestors |
| 19–24 | invaders, peasantry, Waziri, mistress, country, Aryans |
| 25–30 | beloved, mercenaries, scum, mates, resided, clans | |

### Analysis

"Native" in this corpus is not a spatial word meaning "belonging to a place." It is a colonial category. The semantic neighborhood is overwhelmingly made up of real-world imperial geographies and ethnic labels: *Morocco, Senegalese, Bohemian, Altaic, Phoenician, Waziri, Spanish, Aryans.* These are not invented planets or fictional civilizations. They are actual places and peoples that nineteenth and early twentieth century colonial literature wrote about constantly.

*Waziri* is directly traceable to Edgar Rice Burroughs' Tarzan series, where the Waziri are an African tribe allied with Tarzan. The presence of this word here tells you something about which texts are shaping the semantic neighborhood of "native" most strongly.

The 300d model makes the ideological layer even more explicit. *Mongrel, scum, invaders, Aryans* appear more prominently with the richer model. This is the opposite of what you might hope — that more sophisticated training would smooth out the bias. Instead, it learns the ideology more precisely because it has more capacity to capture the full context. *Scum* and *native* sharing a semantic neighborhood is not noise. The model learned this from the texts.

Underwood's warning is directly relevant here. The pattern is real. But I am the one saying it reflects colonial ideology — the model does not label it that way. What the model shows is a distributional fact: across hundreds of texts, the word "native" appeared near these other words with regularity. What that means is an interpretation.


## Query 3: *race*

### Results

**`model_100d_w4` — Top neighbors:**

| Position | Words |
|----------|-------|
| 1–6 | races, tribe, breed, ancestors, universe, rulers |
| 7–12 | element, country, deities, lives, intellect, spirit |
| 13–18 | science, hierarchy, nobility, standards, notions, tribes |
| 19–24 | land, peasantry, creators, knowledge, kingdoms, virtues |
| 25–30 | belief, consciences, group, cities, priesthoods, morale | |

**`model_300d_w8` — Top neighbors:**

| Position | Words |
|----------|-------|
| 1–5 | races, ancestors, tribe, rulers, universe |
| 6–10 | tribes, science, country, breed, age |
| 11–15 | cities, lives, interplay, kingdoms, deities |
| 16–20 | clans, virtues, knowledge, nobility, creatures |
| 21–25 | advancement, standards, Martians, extermination, struggle |
| 26–30 | rule, powers, allies, cults, belief | |

### Analysis

"Race" in this corpus operates simultaneously as biology and civilization. *Breed* and *ancestors* pull it toward hereditary thinking. *Hierarchy, nobility, peasantry, kingdoms, priesthoods* pull it toward social order. Both models show this double meaning clearly.

The 300d model adds something the smaller model misses: *Martians, extermination, advancement.* This is the most explicitly sci-fi cluster in all three queries, and it is also the most alarming. *Advancement* sitting next to *extermination* in the semantic neighborhood of *race* is a near-perfect compression of social Darwinism — the idea that some races advance and others are eliminated, and that this is natural or scientific. The word *science* appearing in both models reinforces this: "race science" was a real ideological formation in the period when most of these texts were written.

*Martians* appearing here is also interesting. It suggests that the corpus uses "Martians" in the same way it uses racial categories — as a group defined by collective characteristics, hierarchy, and difference from humans.

## Comparing the Two Models

The 100d window-4 model captures tighter, more local semantic relationships — what words appear immediately near each other. The 300d window-8 model has more capacity and broader context. The differences between them in these three queries are instructive.

For *alien*, the models are broadly similar, with the 300d version adding slightly more conceptual vocabulary. For *native*, the 300d model surfaces *Aryans, scum, invaders* more prominently — the ideology sharpens rather than blurs with richer training. For *race*, the 300d model uniquely captures the *Martians/extermination/advancement* cluster, which is the most thematically coherent finding of the whole analysis.

The "best for" description in the assignment says the 300d model captures "complex semantic and thematic relationships across broader context." That holds up. The larger model is not just more of the same — it reveals connections that the smaller model cannot see.


## What the Model Cannot Tell You

Word2vec learns from repetition and proximity. It does not know whether a text is endorsing the ideology embedded in its vocabulary or critiquing it. A novel that uses *native* and *mongrel* to satirize colonialism looks identical to one that uses those words approvingly, from the model's point of view. Both contribute equally to the semantic neighborhood.

This is Underwood's core concern made concrete. The patterns I described above are real distributional facts about this corpus. Whether they mean the corpus is uniformly colonial in ideology, or whether some texts are doing something more complicated, is a question the model cannot answer. You would need to read individual texts to find out — which is exactly what AntConc and close reading are for.

What the model can tell you is that the vocabulary of empire was so pervasive in this corpus that it left a measurable statistical trace across 1,000 texts. That is already a significant finding.


## Conclusion

The word vector models trained on this science fiction corpus reveal that three words — *alien, native, race* — live in semantic neighborhoods shaped less by science fiction world-building than by real-world colonial ideology. "Alien" is measured against the human body. "Native" clusters with actual African and Middle Eastern geographies, racial slurs, and markers of imperial hierarchy. "Race" combines biological determinism with civilizational ranking and, in the richer model, connects directly to *extermination*.

The science fiction label does not insulate a corpus from the ideological conditions of its production. These texts were written mostly in the late nineteenth and early twentieth century, during the height of European and American imperialism, and the models learned that context. The future these writers imagined was built from the language of the world they already lived in.

Whether that makes this corpus bad science fiction or historically typical science fiction is a different question — one the model cannot answer, and one worth asking.
