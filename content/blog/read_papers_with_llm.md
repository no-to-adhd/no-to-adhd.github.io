+++
title = "Read Papers with LLM"
date = 2025-01-27:T11:10

[taxonomies]
tags = ["Reflection"]

[extra]
comment = true
+++

While I have enjoyed reading since while I was a kid, reading long academic papers has been,
ever since the need first emerged for me about 10 years ago, a source of misery. It has been
hard for me to 


### The 3-Pass Method

S. Keshav has famously proposed the 3-pass method that has been the goto reference for
paper reading techniques in every graduate course I have attended. As the name suggest,
there are 3 passes when it comes to reading a paper:

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
not actually know if you've formed the correct impression of the paper. Especially
for a beginner like me who don't have a good grasp of the field as a whole, there's
no good way for me to know if I've missed some very basic assumptions in the field,
or if I failed to understand a key concept due to misconception.

This is where generative AI comes to the rescue. The [Zotero
GPT](https://github.com/MuiseDestiny/zotero-gpt) plugin for this well-loved
reference manager has already provided a plethora of tools to help with paper
summary, literature review and so on. A few more prompts could help further. In
particular, it is useful to ask the LLM to evaluate your answers to the
questions listed above, and judge your understanding of the papers based on the
answers. Current testing shows that this is perhaps a hit-or-miss situation,
where the LLM could generate a number of hallucinated nonsense along with a few
key insights that is actually true. The next section (tbd) will present my
test with a number of prompts, as well as the suitability of each model.

### Test with LLMs

(To be continued)
