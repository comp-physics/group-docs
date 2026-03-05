
# Responding to reviewers

When you submit a paper, you will likely get reviews that request changes to your work.
These changes may be major or minor.
Sometimes, the best papers require the most major changes because they are high-impact or the reviewer is picky.
Sometimes, the reviewer may not fully appreciate your manuscript, so the questions don't make much sense.
You should be prepared for all such situations.
Ultimately, it is up to you to make your contributions crystal clear and tell a complete story accessible to __your audience__.

## Principle of charity

While you may want to defend your work, thinking something like, "This reviewer didn't even read the paper!", I recommend a more balanced approach.
If they didn't read your paper deeply and comprehensively, why not?
It could be because it did not grab their interest quickly, and the paper's objective was elusive to them.
In such cases, it is very easy to be lazy when reviewing.
In the end, reviewing papers is an unpaid service that we do as academics, for better or worse.
So, if a paper seems boring, they may quickly dismiss much of it and only skim it (if that!).

Again, _it is your responsibility to make the paper tell an interesting, clear, and important story to the reviewer_.

If they only skim it, their critiques of your work may not make much sense to you.
In these cases, you should respond carefully and point the reviewer to the part of the paper that clearly describes what you did.
You likely will want to reword certain parts of the paper so that you can say something like
> We agree that X was unclear, though it was discussed in Section Y.Z. We have rephrased and clarified paragraph A of this section to clarify point B. Below is the revised text:

## Knowing what to and not to do

Sometimes, a reviewer will request you to do significant extra work for a paper.
Whether or not you should do this rests on many choices.
Do you know if the extra work _really_ improves the paper or makes your conclusions more salient or obvious?
If it doesn't, you should avoid doing this extra work if it (a) doesn't meaningfully improve the paper and thus (b) wastes your time and (c) the reader's time.
Ultimately, this is a rather sensitive topic, and one has to be careful with wording.
I will help you decide what should and shouldn't do.
Regardless, you should be grateful for the reviewer's contributions towards a better manuscript.

## The details of a response document

When you create a response document, make sure to

* Be specific with references to sections and figures! Use the specific section you are talking about and include many quotes of the new text that you added to address their concerns (these should be in a different color than the main reply)

* Defer to the reviewer unless there is a good reason not to. Many issues can be solved by simply agreeing with the reviewer, thanking them for the comment, and correcting the manuscript accordingly.

* If the reviewer is clearly wrong or misunderstanding the paper, this is (usually) on you. Perhaps you should have been more clear in your exposition! You should apologize for any confusion, clarify what you meant, and bolster that part of the paper with references, discussion, and clarity. You should include all of this in your reply to them and apologize for any confusion you caused.

* This is a formal document. Treat it as such. Do not be lax with your grammar or writing.

## Examples

There are examples in this repository, including

* A Revision template [in this directory](https://github.com/comp-physics/group-docs/tree/master/templates/paper_rebuttal)

* In the same place, a `Makefile` that uses the `latexdiff` tool to create a `diff` between the submitted (`main.tex`) and revised (`main_rev.tex`) manuscript files in the form of a new PDF file called `diff.pdf`. This shows the reviewer explicitly all the changes you made to improve the paper (on top of the revisions in the response to the reviewers document).

* Example diffs and responses to reviewers for some of my papers are located [here](https://gatech.app.box.com/folder/245228437856)
