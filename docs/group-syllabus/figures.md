# Making figures

**Companion documents: [Formatting your work](formatting.md)**

See [here](https://github.com/sbryngelson/group-docs/tree/master/templates/paper/figures) for examples.

## This seems like a lot of work. Why am I doing this?

From the formatting document:
> For better or worse, the quality of your figures correlates with the perceived quality of your work. Just like the grammatical correctness of your writing, one might wonder if someone is sufficiently careful with their scientific work if they aren't very careful with their figures and presentation.

Further, using the packages below allows one to easily edit your figures on the fly, reproduce them, and edit them for another document.
This is particularly important, as you will find that many of your figures are surprisingly similar.
I often also request small changes to figures to make them nicer.
You might become quite frustrated if you have to re-do everything in Python + matplotlib, including re-running analysis, exporting the file, reuploading it, etc.
With the method we use in the group, you pay the price __once__ to learn how to make very nice figures with TikZ/pgfplots, then reap the benefits until you decide to stop publishing your work (perhaps retirement).

## What tool should you use to make figures?

Use TikZ and PGFplots.
These are TeX packages that provide a natural way to achieve consistency.
There is a steep learning curve, though the trade-off is worth it compared to their competitors.
The TeX stack exchange website regularly answers questions about these packages.
A web search of almost any basic TikZ/PGF question will quickly flag an answer.
I can provide example `.tex` files for many things (like [here](https://github.com/sbryngelson/group-docs/tree/master/templates/paper/figures)), and you can gather examples from your colleagues as well as online (like [here](https://github.com/comp-physics/tikz-examples) and [here](https://github.com/comp-physics/TikZ-examples-2)).

Some other nice features:

* Allows you to remake a figure very quickly (e.g., change a line of text in a program and recompile)
* Natural use of LaTeX fonts for text and equations

## Standalone compilation

Compile all your figures as standalone PDF documents.
This is handy for your paper and for using them in presentations and other media.
With TikZ, this is quite easy, [here](https://github.com/sbryngelson/group-docs/blob/master/templates/paper/figures/slices.tex) is an example.
Here is a template of sorts:
```tex
\input{tikz_preamble}

\begin{document}
\pagestyle{empty}

\begin{tikzpicture}
%%% Your figure here
\end{tikzpicture}

\end{document}
```
where I have a separate file called `tikz_preamble.tex` that you can find [here](https://github.com/sbryngelson/group-docs/blob/master/templates/paper/figures/tikz_preamble.tex) that holds the relevant packages I need and defined the document style.

Use Tikz option:

```tex
\tikzset{>=latex}
```
to make all the arrows in latex form.

## Use of Git with Overleaf

To create standalone figures in Overleaf, you should leverage its `git` feature.
You simply go to the menu in the browser's top-left and then select `git`.
This gives you a command to `git clone` your Overleaf document.
You can `git add/commit/push` and `git pull` from this cloned directory.

## What if you have flow visualizations?

Images of complex simulations _require careful attention_!
In some cases one will need to annotate them with axes labels, tick marks and labels, legends, and so on.
All of this text/equations should not be rasterized; if they are rasterized, I will send them back to you to fix.

__Paraview:__
I believe Paraview has some functionality for this. Here is [a reference](https://www.paraview.org/Wiki/ParaView/Vector_Graphics_Export) and here is [another](https://scicomp.stackexchange.com/questions/36122/vector-format-export-for-screenshots) and [another](https://www.paraview.org/pipermail/paraview/2017-April/039969.html).
Perhaps it exports a separate vector image for the text and/or legends?
I am not entirely sure how it works.
I welcome recommendations on the best way to do this, but I know it is possible.

Other rules:

* __Background color:__ Do not use background colors in your visualizations, e.g., the dark blue used in Paraview.
Instead, use a white background! It will blend nicely into the document. To get Paraview to create a proper white background instead of a grayish one, make sure you [turn off the light kit for all 2D visualizations!](https://visualisation.gitlab-pages.dkrz.de/documentation/Paraview/Light/deactivate-light-kit/index.html).

* __File size:__ Do not use very large images. Images bigger than roughly 10MB are too large.

## How to label sub-figures

Label your sub-figures using font face and size consistent with the figure caption font face and size.
Place your sub-figure labels (e.g., (a) and (b)) in a place that is not too obtrusive.

* If you do not need sub-captions, you can place the labels in each sub-figure's top left or bottom left.
* If you need sub-captions, you should put the sub-figure labels below the center of the figure.

Do not put the sub-figure captions directly below the sub-figures if you have no "real" caption (e.g., you are just labeling them (a) or (b), etc.); in this case, instead put them in one of the corners per above.
See the examples [here](https://github.com/sbryngelson/group-docs/tree/master/templates/paper/figures) for reference.

Place a space between your sub-figure labels (e.g., (a, b) instead of (a,b)).

## Title

Your figures should not have titles.

## White space

Minimize any excessive white space in journal/abstract figures.
This helps match the figures with relevant text and makes the paper and figure more appealing.
This can also prevent figures from floating into irrelevant sections.
Remove all white space around the figure borders.
Figures in presentations can afford a bit of extra white space.
Figures should never go beyond the page margin.

This principle is discussed more [here](https://bioinformatics-core-shared-training.github.io/effective-figure-design/DesigningEffectiveScientificFigures_Zabala_afternoon_v00.pdf).

## Shared plots and legends

* If you have two side-by-side (left and right) figures (say, sub-figures) that have the same range in the vertical axis, you can remove the vertical labels on the one on the right and move it close to the one on the left so they are sharing the axis and tick labels.

* If the range is different but the axis label is the same, you can leave space for the tick labels for both but remove the axis label for the figures on the right.

* If all the data are marked similarly (lines, markers, etc.) in each subplot, only use one legend, likely centered above the plots, to be interpreted as shared amongst all the subplots.

* Be specific with your legends. Your readers should be able to distinguish the data series by reading the legends only, not requiring the caption to determine what the figure means.

## Color bars

If your data involves a color bar, use one that makes sense for the data you plot.
You can read more about this online, like [here](https://chartio.com/learn/charts/how-to-choose-colors-data-visualization/) or [here](https://academy.datawrapper.de/article/140-what-to-consider-when-choosing-colors-for-data-visualization).
Common guidelines are

* Don't use the rainbow/jet color scheme (read more about the problem with this [here](https://stats.stackexchange.com/questions/223315/why-use-colormap-viridis-over-jet))
* Don't use a tri-color scheme (e.g., Paraview's default blue-white-red) for data that is not centered at a unique/special value like 0
  * A violation would be using such a color scheme for data that varies from 0 to 1
  * In 2D settings, Paraview uses, by default, a lighting scheme that modifies the colors, including making white appear sand colored. Alleviate this by going to `View -> Light inspector` and deselect `Light Kit`.
  * Adjust the RGB values of the color bar to let the unique/special value be exactly white if the data is centered at the unique/special value.
* Using a monochromatic color scheme (e.g., from white to black) for data that vary uniformly as above, say from 0 to 1.
* Use a tri-color scheme that centers the color at black or white, e.g., the Paraview default red-white-blue for nominally centered data at a special or reference value, like 0 or 1.

## Coordinate direction arrow triad.

Do not show the coordinate direction arrows (usually x, y, z) included in Paraview and Visit exports by default.
An exception might be creating a simulation video that requires the viewer to know these orientations.
If you are exporting an image, superimpose your own direction triad if needed.

## Axis bounds and ticks

Your axes should, whenever possible, start and end at labeled tick marks.
This is especially important for log-scale axes.
One should avoid extra white space to the axes' left and right (or top and bottom).
In pgfplots, this is achieved with the options:
`\begin{axis}[enlarge x limits=0, enlarge y limits=0]`.
Avoid excessive text in tick marks when possible.
For example, use `1, 2, 3, 4, 5` in units of `kHz` instead of `1000, 2000, 300, 4000, 5000` in units of `Hz`.

## Axis labels

In `tikz_preamble.tex`, the package `siunitx` is imported. If possible, use this to format your units. For example, if your units are in microseconds ($\mu \textrm{s}$), use `\unit{\micro\second}`. To access documentation on `siunitx`, visit [the package webpage here](https://ctan.org/pkg/siunitx?lang=en).

For log-scale axes, be sure that you use actual quantities in the data you plot.
For example, do not label your axis as "$2^x$ Points" where $x$ is linearly plotted on the axis.
Log mode in pgfplots exists for a reason!

In some cases, pgfplots will scale the axis label by some $k$-th power of $10$, indicated using $\cdot 10^n$. If possible, it would be preferable to replace the $\cdot$ symbol with $\times$. This may be done by ways of inserting the expression `tick scale binop=\times` in the axis environment.

When naming your axes, ensure the chosen labels clearly convey what quantities or qualities they describe, and in almost all cases one should include the math symbol that describes any text in the label.
For example, suppose you seek to indicate how your algorithm scales with the number of lattice sites.
"Number of Lattice Sites $N$" conveys this intention, albeit long, and simply using "Lattice Sites" is unclear.
Someone unfamiliar with the content may interpret this as referring to data describing different points on a given lattice.

## Information quantity

Your figures should only contain the information required to tell the story or demonstrate the desired results.

Examples of having too much information are, well, numerous. Some examples:

* You have too many tick marks
* You include too many lines of data on your plot.

To be quite specific, if you have two simulation results that are very close to each other, you may or may not want to show both on your figure.
You should show both if your intention _is to show_ that they are close together.
If your message is the result, you can just show one simulation result and mention in the caption that the results for the other case look the same.

Simulations usually involve critical physical configurations such as domain boundaries, immersed boundaries, or objects with significantly different physical properties.
Make sure to show them in the simulation visualization.

Essentially, you want to show the reader as close as possible to a 'cartoon' of your work.
Showing frivolous information distracts from your message.

Avoid using colors that are too similar to the background to annotate figures. Use easily distinguishable colors.

## Consistency

Figures should also be consistent between each other and the surrounding text.
If you use a solid black line to denote the "exact solution" in one figure, do not switch to a dashed red line for a different exact solution in a later figure.
The fonts used in the figures should match the face and size of the surrounding text.
LaTeX uses Computer Modern and Latin Modern font faces and 11pt sizes by default, though journal templates and class files may change this.

The font size of the captions below your figures should be one step smaller than that of your document (so 10pt if the document is nominally 11pt).
The tick and axis labels should also be smaller than the nominal font size of your document; 9pt is usual here, and it should be consistently this size throughout your document.

**Rule:** Do _not_ scale your figures via the command
```tex
\includegraphics[width=0.3\textwidth]{figure.pdf}
```
Doing so leads to inconsistent font sizes between the document and the software that generated the figure.
__An exception__ to the above is if the figure contains no text or equations, like a simulation visualization.

**Rule:** Use vector graphic formats (PDF, please) for all plots that involve text or equations.

**Rule:** Use the same color palette for all of your figures (not including flow visualizations) and your main text (see [formatting](formatting.md)]).

An excerpt from [Formatting your work](formatting.md).

> One should keep styles consistent within a manuscript.
> You might be forgiven for esoteric style choices if they are employed consistently.
> From [here](https://www.annaclemens.com/blog/figure-graph-data-vizualisation-plot-scientific-paper):
> A clear and consistent design in the figures in your scientific paper will make it easy for your reader to gather the presented information. For this, I suggest using the same color and symbols for each variable throughout all your scientific figures. Sample 1 is displayed as red triangles in Figure 1? Make sure it is in Figure 5, too.

## Useful references

* [Principles of Beautiful Figures for Research Papers (must watch!)](https://www.youtube.com/watch?v=i-HAjex6VtM)
* [Ten Simple Rules for Better Figures](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003833)
* [How to make figures for scientific papers](https://www.annaclemens.com/blog/figure-graph-data-vizualisation-plot-scientific-paper)
* [Brushing Up Science Figure Advice](https://brushingupscience.com/category/figures/)

## Additional Resources

Additional resources on using Paraview and making presentable visualizations can be found [here](https://github.com/comp-physics/Scientific-Visualization)
