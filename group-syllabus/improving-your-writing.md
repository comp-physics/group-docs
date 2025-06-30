## Academic writing

**Companion documents: [Formatting your work](formatting.md), [Improving your writing](improving-your-writing.md), [Making a figure](figures.md), [Responding to reviewers](responding-to-reviewers.md)**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of Contents

- [Why should I read this?](#why-should-i-read-this)
- [Automatic grammar, spelling, and syntax checkers](#automatic-grammar-spelling-and-syntax-checkers)
- [Consistency](#consistency)
- [Nomenclature](#nomenclature)
- [Variable Naming](#variable-naming)
- [Concise writing](#concise-writing)
- [What goes where](#what-goes-where)
- [Guidelines, tips, and more!](#guidelines-tips-and-more)
  - [Things to avoid; from the Angry Reviewer](#things-to-avoid-from-the-angry-reviewer)
  - [From some tips for scientific writing](#from-some-tips-for-scientific-writing)
  - [From Koen Hufkens](#from-koen-hufkens)
- [Required watching](#required-watching)
- [Other links](#other-links)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

### Why should I read this?

Many students have trouble producing scientifically acceptable writing without significant training.
(I use "scientifically acceptable" as a suitcase word for whatever seasoned academics find appropriate in journal papers.) 
Perhaps this isn't surprising; students do not formally learn how to do this.

This difficulty is juxtaposed with just how important your writing is.
You likely will only remember some details of your past research projects.
Instead, you'll be able to use your papers as references.
Other scientists won't see your research notes (nor would you want them to) or know the details of your academic past.
Instead, they will judge you based on your archived writing (conference proceedings and journal articles).
Only a few opportunities exist to side-step this.
Giving conference and invited talks communicates your research without paper-in-hand.
However, this format is ephemeral.
Anyone interested in your talks can find your papers to understand your contributions without time constraints.
It is also two-way coupled: you will likely only be invited to give talks with the presumption of good papers behind them.

Careful writing also begets careful thinking (and vice-versa).
That is, forcing yourself to clarify and organize your work will bring problems in your thinking to light.
Because of this, improving your writing as soon as possible can be useful.
New students may well be over a year from starting a manuscript for a journal.
However, they, too, will benefit from carefully writing up their notes, ideas, and plans.

For the above reasons, high-quality scientific writing is often expected from students ready to graduate with their Ph.D.
I invite you to use this document to bootstrap your way to scientifically-acceptable technical writing.

From a now-deleted StackExchange post on "pet peeves in academic writing":
> Ernest Hemingway wrote, "the only kind of writing is rewriting." E. B. White wrote essentially the same thing: "The best writing is rewriting."
> 
> I have plenty of pet peeves about academic writing, but they all seem to have the same cause: that the author apparently didn't care about writing well.
> 
> Your first version of anything is likely to be mediocre. (That's certainly true for me!) Care about your own writing, enough to notice and be annoyed by shortcomings in your first draft, and then figure out how to improve it. Do this, and you will be well on your way to excellent writing.

Also see: [Does writing matter a lot in research?](https://academia.stackexchange.com/questions/107919/does-writing-matter-a-lot-in-research)

### Automatic grammar, spelling, and syntax checkers

Several of these exist.
I use [Grammarly](https://www.grammarly.com/).
It offers a free tier and a trial of the "pro" service at the time of writing.
I purchased the full Grammarly and do not regret the purchase.
The [Angry Reviewer](https://www.angryreviewer.com/) tool is also helpful for giving line-by-line feedback.
A general list of rules used in this tool is available [here](https://www.angryreviewer.com/rules).
We elaborate on this below.

These tools can check for simple things, like improper spelling and grammar. 
They can also identify more complicated style-related things, such as active and passive voices, repeated words and sentence-starters, "sticky sentences" (run-on sentences held together by many articles), and so on. 

I recommend using one of these before submitting any paper or abstract.
Often, even seemingly obvious mistakes can go unnoticed after so many revisions.
Such mistakes are a quick way for an editor or reviewer to perceive your work as careless (e.g., does he conduct his simulations like he writes his abstracts?!), even if only subconsciously.

### Consistency

One should keep styles consistent within a manuscript.
You might be forgiven for even poor style choices if you are consistent.
Please look at the [these](formatting.md) documents for more.
Note that this consistency extends to the level of detail throughout the paper.
A detailed introduction is best matched with a results section that achieves a similar level of detail.

### Nomenclature

Changing technical terms mid-way through a paper in the name of style will confuse people.
If your domain is a cylinder, don't switch to "tube" at any point.
If you call your model a "physical model," do not switch to calling it a "numerical model" (with the additional problem that these two things aren't the same, anyway).
If you define your "mesh spacing" in one section, don't switch to "grid spacing" or "mesh resolution" later on.
Don't use software-specific nomenclature.
This confuses readers if they haven't used the software, and they may not plan to use it.

### Variable Naming

Names of variables should make sense for an outside reader.
The objective is to make the paper as easily readable as possible.
In some cases, there may be a standard variable used for the value.
For example, consider how $c$ is used to denote the speed of sound.
Using $m$ to denote the speed of sound is not invalid, but may be confusing at the outset.

Beware of using too many distinct variables for quantities, especially related ones.
This leads to confusion for the reader, who now must keep track of a variable table on top of the content of the work.
Make use of subscripts to annotate the variable and simplify the naming scheme.
For example, suppose we have the following values to be used in equations:
- Number of samples
- Number of lattice sites
- Number of dimensions

We may use $M$, $N$, and $K$ to denote each of these quantities.
However, this is confusing and fails to show that we are simply counting the "number of [something]". 
Instead, denote the values using variables $N_{samp.}$, $N_{sites}$, and $N_{dim.}$. 

### Concise writing

One should prefer using as few words as required when describing something technical.
You can consult replacement lists for common mistakes:

* [Wordy phrases](https://grammarist.com/wordiness/)
* [Wordy phrase replacements](https://www.kingcounty.gov/help/editorial-style-guide/concisewriting/wordyphrases.aspx)
* [Wordiness, Wordiness, Wordiness List](https://web.uvic.ca/~gkblank/wordiness.html)
* [50 Plain-Language Substitutions for Wordy Phrases](https://www.dailywritingtips.com/50-plain-language-substitutions-for-wordy-phrases/)

These lists help me realize, "Hey, I write wordy phrases like this all the time!"
Use the lists to learn the general ways one ends up with low information-density writing.
You can then identify similar phrases in your writing.
Often, eliminating them is relatively easy, but noticing them is (at first).

Conciseness can be viewed in a broader sense.
For example, you should structure your paragraphs such that you aren't repeating information.
Other tips of this type are available at these links:

* [Writing Concisely – The Writing Center • University of North Carolina at Chapel Hill](https://writingcenter.unc.edu/tips-and-tools/conciseness-handout/)
* [Writing Clearly & Concisely](https://writingcenter.ashford.edu/writing-clearly-concisely)
* [Tips for being concise in academic writing](https://lauraripperproofreading.com/2018/01/26/how-to-be-concise-tips-for-academic-writing/)

### What goes where

__Always__ have a narrative first figure demonstrating what you are doing and "telling the overall story."
Take time to make this figure as attractive as possible.
It is one of the first things your readers will see!
See, for example, the first figure in my paper, "Fast Macroscopic Forcing Method."

* Abstract 
    * Include a full, self-contained mini-version of your paper, including an introduction to your method, quantitative measures of your results, and conclusion and takeaways.
* Introduction (in this order)
    * What is your work?
    * Why are you doing it?
    * What is the open problem you are trying to solve?
    * What are some methods related to your work?
    * What key contributions will you add? (without full detail)
    * What does the rest of the manuscript contain?
* Acknowledgments 
    * We always have an unnumbered acknowledgment section before the references but after the discussion/conclusions. This is where we acknowledge funders and those who have helped with the work but are not authors.
* Future work 
    * I recommend not including a future work section in your papers or presentations

### Guidelines, tips, and more!

#### Things to avoid; from the [Angry Reviewer](https://www.angryreviewer.com/rules)

* Don't hype. Avoid words like novel, highly, clearly, greatly. Better still, avoid all adverbs.
* Don't use clichés. In a nutshell, by and large, they are clear as mud.
* Don't use "very" very often. Usually, there is a better word for it.
* Be concise. Avoid phrases like "by means of, despite the fact that, in order to".
* Avoid negatives. For example, use "unable" instead of "not able".
* Avoid redundancy. For example, use "investigate" instead of "conduct an investigation of".
* Use active voice. Although not always possible, most text should be in an active voice.
* Avoid inappropriate language. Keep words like "really, actually, pretty much" for social networks.
* Avoid rare words and latinisms. Non credo all readers know the meaning.
* Keep abbreviations to a minimum. Abbreviations are hard to read, consider just spelling it out.
* Beware of zombie nouns. Utilization of nominalization is the causation of distraction.

#### From [some tips for scientific writing](https://kucharski.substack.com/p/some-tips-for-scientific-writing)

* Use the "show, don't tell" technique. If something is interesting or surprising, the reader should be interested or surprised by what they've read. They shouldn't need to be told. Anton Chekhov reportedly said: "Don't tell me the moon is shining; show me the glint of light on broken glass."

* Don't bury the lede. When journalists write articles, they usually include crucial information in the opening paragraph. Hiding big news later in the piece is known as "burying the lede." This idiom forms part of the inverted pyramid approach to writing: put the most important information first in an article or section, then fill out the details.

* Read widely, reflecting as you go. Why was that sentence hard to follow? Why did you like that section of text? Why was that turn of phrase annoying? What gave that paragraph its nice balance and rhythm? As Toni Morrison once put it: "Writing is a way of thinking – not just feeling but thinking about things that are disparate, unresolved, mysterious, problematic or just sweet."

* Make your readers care about what they're reading. Like a good story, this typically means outlining a clear problem and promising a later resolution.

* Some anonymous entities didn't do the analysis. You did the analysis. So avoid the passive voice if possible. (See also: "a decision was made" rather than "we made the decision" when it comes to responsibility-dodging in leadership messages.)

* If you promise something in the introduction, ensure you've delivered by the end of the results. For example, if you open by mentioning A and B, readers will be expecting a conclusion about A and B by the end of the paper. "Remove everything that has no relevance to the story,' as Chekhov put it. "If you say in the first chapter that there is a rifle hanging on the wall, in the second or third chapter, it absolutely must go off."

* Follow Orwell's rules of writing
    * Never use a metaphor, simile, or other figure of speech that you are used to seeing in print.
    * Never use a long word where a short one will do.
    If it is possible to cut a word out, always cut it out.
    * Never use the passive where you can use the active.
    * Never use a foreign phrase, a scientific word, or a jargon word if you can think of an everyday English equivalent.
    * Break any of these rules sooner than say anything outright barbarous.

* Kill your darlings. Sometimes, you'll write a so elegant and well-crafted phrase that it jars with the rest of your writing and pulls the reader out of the flow. So cut it. As Stephen King once put it: _'Kill your darlings, kill your darlings, even when it breaks your egocentric little scribbler's heart, kill your darlings.'_

* If you want to describe a figure/table in the results text, it can help to imagine you're giving a seminar. What features would you draw your audience's attention to? What would you tell people about during coffee break?

* Help the reader interpret your figures and tables. Don't give them a sixteen-panel graph and expect them to spot the main takeaway; if the author can't be bothered to find a key message, the reader almost certainly won't either.

* You can probably cut your word count by about half if you need to, without losing meaning. (I've managed to cut down a bunch of paper submissions into much shorter report formats when pressed.)

* A good intro and discussion will often include a reference or statistic most readers won't have been aware of. Try and find the best references, rather than the easiest ones.

#### From [Koen Hufkens](https://github.com/khufkens/paper_writing_checklist)

His document covers a small subset of components of a well-written manuscript.
Some of these are soft writing rules/guidelines.
They can be broken, but before breaking them, one usually has to understand why they exist.
If you consciously break a rule in your view for a good reason, then go for it.
Otherwise, stick to the guidelines.

- [ ] Use active language
- [ ] Avoid long sentences
- [ ] Simplify your language (_no thesaurus_)
- [ ] One paragraph communicates one important idea
- [ ] Connect paragraphs and ideas in a logical order
- [ ] Use the present tense for the main part of the manuscript; past tense is allowed in some parts of the abstract and conclusions.
- [ ] Avoid informal language
- [ ] No superlatives (e.g., _very complicated_)
- [ ] Limit the use of conjunctive (connecting) words (e.g., however, moreover). It's ok just to start a sentence!
- [ ] Limit repetitive words (don't substitute using the thesaurus, re-evaluate the sentences)
- [ ] Don't use spoken contractions (e.g., it's)

### Required watching

Before writing a paper, watch these two lectures from the University of Chicago:
* [The Craft of Writing Effectively](https://www.youtube.com/watch?v=vtIzMaLkCaM)
* [Writing Beyond the Academy](https://www.youtube.com/watch?v=aFwVf5a3pZM)

### Other links

Over the years, I found the documents below helpful for improving my writing:

* [Toward a good scientific writing](https://link.springer.com/article/10.1007/s40071-014-0080-8)
* [Terry Tao's advice](https://terrytao.wordpress.com/advice-on-writing-papers/)
* [Improving your scientific writing: a short guide](https://lijunsun.github.io/files/ScientificWritingV39.pdf)
* [Knuth Mathematical Writing Guide](https://tex.loria.fr/typographie/mathwriting.pdf)
* [Three Sins of Authors in Computer Science and Math](http://www.cs.cmu.edu/~jrs/sins.html)
* [How to write a great research paper](https://www.microsoft.com/en-us/research/academic-program/write-great-research-paper/)
* [Notes on writing](http://people.csail.mit.edu/fredo/PUBLI/writing.pdf)
* [How to Write a Good Article](http://people.csail.mit.edu/fredo/FredoBadWriting.pdf)
* [Ten simple Rules for Responsible referencing](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006036#sec001)
* [Writing a science paper some dos and don'ts](https://www.elsevier.com/connect/writing-a-science-paper-some-dos-and-donts)
* [Experimental Biosciences writing science](http://www.ruf.rice.edu/~bioslabs/tools/report/reportform.html)
* [11 steps to structuring a science paper editors will take seriously](https://www.elsevier.com/connect/11-steps-to-structuring-a-science-paper-editors-will-take-seriously)
* [Strunk and Write](https://www.amazon.com/Elements-Style-Fourth-William-Strunk/dp/020530902X) is a classical book that describes common writing gaffs and style particulars. 
* [Move over Strunk and White: My all-time favorite books on writing](https://clauswilke.com/blog/2017/11/12/move-over-strunk-and-white/)


