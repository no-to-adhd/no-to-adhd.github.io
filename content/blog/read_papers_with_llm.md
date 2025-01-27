+++
title = "Read Papers with LLM"
date = 2025-01-27

[taxonomies]
tags = ["Reflection"]

[extra]
comment = true
+++

While I have enjoyed reading since while I was a kid, reading long academic papers has been,
ever since the need first emerged for me about 10 years ago, a source of misery. It has been
hard for me to 


### The 3-Pass Method

S. Keshav has famously proposed the
[3-pass](http://ccr.sigcomm.org/online/files/p83-keshavA.pdf) method that has
been the goto reference for paper reading techniques in every graduate course I
have attended. As the name suggest, there are 3 passes when it comes to reading
a paper:

1. The first pass aims to answer the following question:
    _What type of paper is it (theory, measurement, implementation,
experience)?_ _Which other papers is it related to? What is the problem
domain?_ _Do the assumptions hold?_ _What is the main contribution_?

    In order to anwer these questions, the reader needs to read the
    paper's abstract, introduction, section and subsection headings,
    the conclusion, potentially the related work section, and the references.

2. The second pass aims to help the reader grasp the main content of the paper.
    All apart from the proofs need to be understood through this pass. It is also
    important to mark unread references.
    _What's method?_ _What evaluation metrics are used?_ _What are the results?_
    _Are the results good quality/credible?_

3. The third pass should be treated as if you are re-implementing the paper
   yourself, and one should care about every single detail of the paper.
   Some questions you can ask yourself: _Do you have some ideas for future work?_,
   _What metrics would you be interested in, and how would you have designed the
   implementation/experiments differently?_

### Inadequacies

These passes are a good starting point for reading a paper, but the danger of
using these methods, especially if you stop at the second pass, is that you do
not actually know if you've formed the correct "impression" of the paper.
Especially for a beginner like me who don't have a good grasp of the field as a
whole, or when we are actively exploring a new field to varying degree of understanding,
there's no good way for me to know if I've missed some very basic assumptions
in the field, or if I failed to understand a key concept due to misconception.
Further, I have come to doubt my reading comprehension capabilities recently
in part due to previous failed attempt to understand papers by read a paper
through from cover to cover (which is admittedly not the recommended way to
read a paper if you really want to understand it).

This is where generative AI comes to the rescue. The [Zotero
GPT](https://github.com/MuiseDestiny/zotero-gpt) plugin for this well-loved
reference manager has already provided a plethora of tools to help with paper
summary, literature review and so on. A few more custom prompts could help
further. In particular, it is useful to ask the LLM to evaluate your answers to
the questions listed above, and judge your understanding of the papers based on
the answers. Current testing shows that this is a bit of a hit-or-miss, where
the LLM could generate a number of hallucinated nonsense along with a few key
comments that is actually useful and insightful. In the next section (tbc) will
present my test with a number of prompts, as well as the suitability of some of the
foundational models for this particular task.

Another idea is to use LLMs for contextual information briefing, where the LLM
could be asked to project the contextual knowledge required to the read the paper,
or to understand the full motivation and context of the paper in the first place.
One downside with the current implementation is that most LLM api services do not
seem to release a public api which integrates with their web search services. This
raises doubts as to how much the LLM is actually able to understand from either the
prompt or the tokenized paper, without additional input from 

### Test with LLMs

#### Idea I: ask the LLM to be your professor/PI

Tests with ChatGPT (non-chain of thought model):
```
(You do not need to respond to this prompt) You are a professor in computer
science who is leading a reading group. Students in your group will review
research papers and ask for your comment. You can be as critical as you want so
long as your critiques are truthful. In each session, you will be given a
research paper, about which the students will then ask for contextual knowledge
required for them to understand this paper. The students will then answer the
following questions: _what is the motivation for this paper?_, _what type of
paper (implementation, evaluation/measurement, ideas, theory, proofs, etc)?_,
_what is the problem domain?_ and _what is the main contribution?_. You will
need to JUDGE their answers critically, and indicate what your student may have
failed to understand.
```

During the first reading pass, the LLM has provided critiques of the responses.
It does not neccesarily have the full contextual knowledge of a computer
science masters student (maybe it is not prompted correctly), but it does
know how to read a paper, and provides insights from _foresight_ (since it
has "read" through the whole paper, compared to just a few sections by the
human in the first pass).

The full [chat](https://chatgpt.com/share/6797ad48-1b2c-800d-950e-fb4d301f5236) under
this prompt.
