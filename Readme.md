# Literary Emotion Dynamics

Code and data for the paper `The Emotion Dynamics of Literary Novels`.

## Emotion Arcs in Novels
Characters (fictional named entities) are often at the center of the emotional connection that readers form with a story; we identify with their struggles, react to their pain,
and celebrate their victories. The different characters within a single story usually display varying
emotional trajectories through the course of the
narrative. This variation is also seen at the level
of the novel itself: some are tragedies, some are
comedies; some have very dramatic highs and lows,
others have a more even emotional tone.

Prior work in NLP on plotting the shapes of stories has largely considered a novel as representing a single emotional trajectory, where the dialogue of all the different characters is merged together with the narration to create one overarching novel arc (a simplification made because of the lack of annotated data in which characters are mapped to their utterances --- still a challenging NLP problem).


In this work, we look instead at the emotion arcs of the individual characters in  story, distinguishing them from the arcs of the narration as well as the overall novel arc, and quantify the extent of their variation both within a single novel and across novels written by different authors. We model character emotion arcs as the temporal sequence of emotions expressed by them in their **utterances** (i.e, quotations uttered by the character).

## The Project Dialogism Novel Corpus
[PDNC](https://github.com/Priya22/project-dialogism-novel-corpus) contains manual annotations identifying the speakers
of all dialogue in 28 full-length English-
language novels. We use this dataset to obtain temporally-ordered sequences of character utterances.

## The Utterance Emotion Dynamics Framework
Emotion dynamics is a framework from Psychology for measuring how an individual’s emotional state changes over time. [Hipson and Mohammad (2020)](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0256153) introduced an analogous framework for changes in emotional state associated with one's utterances. They refer to it as Utterance Emotion Dynamics (UED). Specifically, they proposed a set of metrics (such as home base, density, variability, rise rate, etc.) that quantify various characteristics of change in one's emotional state as reflected in their utterances. 

We use the [Python implementation of the UED framework](https://github.com/Priya22/EmotionDynamics) to characterize the emotion arcs for each speaker in PDNC (individual characters,  the narration and the overall novel (narration and dialogue combined)).

### Constructing Emotion Arcs
Temporal arcs of emotion states can also be derived from a sequence of textual utterances using the [Emotion Dynamics](https://github.com/Priya22/EmotionDynamics) framework. We use lexicon-based methods to determine the emotion score of a text span. This was shown to produce high-quality emotion arcs when used with window sizes of a 100 utterances or more in [Teodorescu and Mohammad, 2023](https://github.com/dteodore/EmotionArcs).

### Emotion Dimensions
We characterize the emotion states of speakers along the three affective dimensions of valence (positive--negative), arousal (active--passive), and dominance (in control--out of control).

Lexicons that associate nearly 20000 English words with a real-valued score of VAD (1 indicates maximum positive association, and 0 indicates a highly negative association) can be obtained from the [NRC-VAD lexicons](http://saifmohammad.com/WebPages/nrc-vad.html).

## Authors

For any queries, you can contact the authors:

1. [Krishnapriya Vishnubhotla](https://priya22.github.io/) (University of Toronto)
2. [Adam Hammond](https://www.adamhammond.com/) (University of Toronto)
3. [Graeme Hirst](http://www.cs.toronto.edu/~gh/) (University of Toronto)
4. [Saif M. Mohammad](http://saifmohammad.com/) (National Research Council Canada)

Contact: vkpriya@cs.toronto.edu
