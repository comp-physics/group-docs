## Formatting your documents

**Companion documents: [Improving your writing](improving-your-writing.md), [Making a figure](figures.md)**

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of Contents

- [Why should I read this?](#why-should-i-read-this)
- [Consistency](#consistency)
- [Compiling and other boilerplate](#compiling-and-other-boilerplate)
- [Preamble and packages](#preamble-and-packages)
- [Units](#units)
- [Math symbols](#math-symbols)
- [Scientific notation and large/small numbers](#scientific-notation-and-largesmall-numbers)
- [Bibliography](#bibliography)
- [Referencing your bibliography](#referencing-your-bibliography)
- [Creating your bibliography](#creating-your-bibliography)
- [Colors](#colors)
- [Referencing equations, figures, tables, and sections](#referencing-equations-figures-tables-and-sections)
  - [Figures, tables, sections](#figures-tables-sections)
  - [Equations](#equations)
- ["Dashes"](#dashes)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

### Why should I read this?

For better or worse, the quality of your figures correlates with the perceived quality of your work.
Just like the grammatical correctness of your writing, one might wonder if someone is sufficiently careful with their scientific work if they aren't very careful with their figures and presentation.
I am putting some "rules" below for how to format your documents and figures.

### Consistency

One should keep styles consistent within a manuscript.
You might be forgiven for esoteric style choices if they are employed consistently.
From [here](https://www.annaclemens.com/blog/figure-graph-data-vizualisation-plot-scientific-paper):
> A clear and consistent design in the figures in your scientific paper will make it easy for your reader to gather the presented information. For this, I suggest to use the same colour and symbols for each variable throughout all your scientific figures. Sample 1 is displayed as red triangles in Figure 1? Make sure it is in Figure 5 too. 

### Compiling and other boilerplate

* Use LaTeX for all of your documents.
* Make sure your documents _do not_ compile with errors, especially if you are using Overleaf!
* If you have warnings, understand where they warnings come from. They may be signaling something important!
* On my local computer, I like using `latexmk` for compilation.
* __Put each sentence on one line of source `.tex` code__

### Preamble and packages

Always structure your document so that the preamble is separate from the main text (two separate files).
You can connect them by placing `\input{preamble.tex}` at the top of your main text file `main.tex`, right after the
```latex
\documentclass[11pt,sort&compress]{elsarticle}
```
clause.

In the preamble file, you should include some packages.
[Here](../templates/paper/preamble.tex) are some examples.
Please look them up to see what they do.

For `elsarticle` class files (mine is included [here](../templates/paper/elsarticle.cls)), which I recommend you use, you need to organize the hyper-reference coloring a bit differently, which in that example document you will see in the preamble as well the top of `main.tex`

```tex
\documentclass[11pt,sort&compress]{elsarticle}

\input{preamble.tex}

\begin{document}

\hypersetup{
  linkcolor=darkrust,
  citecolor=seagreen,
  urlcolor=darkrust,
  pdfauthor=author,
}
```

Discussion of these colors and their definitions are included below.

### Units

Always use a LaTeX package if your quantities use units.
My preference is
```tex
\usepackage{siunitx}
```
If you do not use a LaTeX package your spacing and characters will likely be inconsistent and incorrect.
Your source code will also be very verbose and hard to read.
Use proper package options:

```tex
\sisetup{separate-uncertainty = true,print-unity-mantissa=false,per-mode=symbol,range-phrase = \text{--}}
```
which configures the `siunitx` package to display units with division `m/s` using the slash symbol (/) instead of the reciprocal form `m s^{-1}`, amongst other things.
See the template preamble for its use.

### Math symbols

Always use consistent math symbols.
I usually put all of these in a single file that is invoked in the LaTeX preamble via
```tex
\input{mathsymbols.tex}
```
and an example such file is in `templates/paper/mathsymbols.tex` in this repository.

Some notation rules you should follow
* Bold lowercase for vectors
* Bold uppercase for matrices and tensors
* Non-bold lowercase for scalars/constants

Common errors
* Dimensionless symbols like the Reynolds number __should not__ be italic, but upright.
    * Like this $\mathrm{Re}$
    * Not like this $Re$
* Super and subscripts that denote text __should not__ be in math/italic symbols but rather upright normal text. 
    * Like this: $c_{\mathrm{Temp.}}$ or $\mathbf{A}_{\mathrm{Fast}}$
    * This is also OK: $c^{\mathrm{(Temp.)}}$ or $\mathbf{A}^{\mathrm{(Fast)}}$
    * But not like this: $c_{Temp}$ or $\mathbf{A}_{Fast}$
* Do not use asterisks or $\times$ for multiplication
    * Like this: $ab$
    * Never like this: $a\times b$ or $a \ast b$
* Do not use inline math with full fractions that make your text too small to read!
    * Don't do this (inline): $\frac{a}{b}$
    * Do this: $a/b$
* Always use \left and \right for scalable delimiters around tall expressions like fractions or summations.
    * Don't do this: $(1 + a(1 + \frac{a + b}{b}))$
    * Do this: $\left(1 + a\left(1+ \frac{a + b}{b} \right) \right)$
    * Note that in the incorrect version, the closing parenthesis is too small and does not scale to the height of the fraction

### Scientific notation and large/small numbers

__Rule:__ Never use the notation $4e-5$, $4e+05$, or the like in any paper, presentation, or figure.
Always use $4 \times 10^{-5}$.
If units are involved, use `siunitx` and the options listed in the paper template `preamble.tex`.

### Bibliography

Always use consistent formatting.
This might mean more than it seems at first.

Some examples and common errors:
* Choose to either abbreviate journal names (using the __correct__ abbreviation, Google it!) or use the full journal name (use camel case! _Journal of Fluid Mechanics_ __not__ _Journal of fluid mechanics_), then stick with it. 
    * Like this (full names): 
        * Firouznia, M., Bryngelson, S. H., Saintillan, D. (2023). A spectral boundary integral method for simulating electrohydrodynamic flows in viscous drops. Journal of Computational Physics, 489, 112248.
        * Spratt, J.-S., Rodriguez, M., Schmidmayer, K., Bryngelson, S. H., Yang, J., Franck, C., and Colonius, T. (2021). Characterizing viscoelastic materials via ensemble-based data assimilation of bubble collapse observations. Journal of the Mechanics and Physics of Solids, 152, 104455.
    * Or like this (abbreviations)
        * Firouznia, M., Bryngelson, S. H., Saintillan, D. (2023). A spectral boundary integral method for simulating electrohydrodynamic flows in viscous drops. J. Comp. Phys., 489, 112248.
        * Spratt, J.-S., Rodriguez, M., Schmidmayer, K., Bryngelson, S. H., Yang, J., Franck, C., and Colonius, T. (2021). Characterizing viscoelastic materials via ensemble-based data assimilation of bubble collapse observations. J. Mech. Phys. Solids, 152, 104455.
    * But not like this (mixed)
        * Firouznia, M., Bryngelson, S. H., Saintillan, D. (2023). A spectral boundary integral method for simulating electrohydrodynamic flows in viscous drops. Journal of Computational Physics, 489, 112248.
        * Spratt, J.-S., Rodriguez, M., Schmidmayer, K., Bryngelson, S. H., Yang, J., Franck, C., and Colonius, T. (2021). Characterizing viscoelastic materials via ensemble-based data assimilation of bubble collapse observations. J. Mech. Phys. Solids, 152, 104455.

* In an article title, only capitalize the first letter, proper nouns, abbreviations, and the first letter after a colon
    * Like this: _A Gaussian moment method and its augmentation via LSTM recurrent neural networks for the statistics of cavitating bubble populations_
    * Not like this: _A Gaussian Moment Method and its Augmentation via LSTM Recurrent Neural Networks for the Statistics of Cavitating Bubble Populations_
    * And definitely not like this: _A gaussian moment method and its augmentation via lstm recurrent neural networks for the statistics of cavitating bubble populations_
    * Accomplish this via the `.bib` entry, like this
    ```tex
    title = {A {G}aussian moment method and its augmentation via {LSTM} recurrent neural networks for the statistics of cavitating bubble populations},
    ```

* Book titles are usually capitalized as you enter them verbatim (capitalization and all) in the `.bib` file. So, be consistent when citing book titles!
    * Like this:
        * M. A. Nielsen and I. L. Chuang, _Quantum Computation and Quantum Information_ (Cambridge University Press, 2000)
        * T. Kruger, H. Kusumaatmaja, A. Kuzmin, O. Shardt, G. Silva, and E. Viggen, _The Lattice Boltzmann Method: Principles and Practice_ (Springer International Publishing, 2016)
    * Or like this:
        * M. A. Nielsen and I. L. Chuang, _Quantum computation and quantum information_ (Cambridge University Press, 2000)
        * T. Kruger, H. Kusumaatmaja, A. Kuzmin, O. Shardt, G. Silva, and E. Viggen, _The lattice Boltzmann method: Principles and practice_ (Springer International Publishing, 2016)
    * But not like this:
        * M. A. Nielsen and I. L. Chuang, _Quantum Computation and Quantum Information_ (Cambridge University Press, 2000)
        * T. Kruger, H. Kusumaatmaja, A. Kuzmin, O. Shardt, G. Silva, and E. Viggen, _The lattice Boltzmann method: Principles and practice_ (Springer International Publishing, 2016)

### Referencing your bibliography

Use `natbib` via `\usepackage{natbib}` (it is automatically loaded when one uses the `elsarticle` class).
I recommend the bibliography style file in the template at `templates/paper/bibsty.bst`.
This is automatically handled if you use the paper template in this repository.
This way, you will have access to text and parenthetical citations, which render as:
> One can partially address this problem by working in Fourier space [1] or fitting a parametric model to approximate the eddy diffusivity operator [21, 23]. However, the former requires spatial homogeneity, and the latter's accuracy depends on the parametric model's quality. Liu et al. [17] introduces an improved model that uses the nonlocal eddy diffusivity operator's moments to approximate the operator. 
via the code
```tex
One can partially address this problem by working in Fourier space or fitting a parametric model to approximate the eddy diffusivity operator~\citep{hamba04,park21}. 
However, the former requires spatial homogeneity, and the latter's accuracy depends on the parametric model's quality. 
\citet{liu21} introduces an improved model that uses the nonlocal eddy diffusivity operator's moments to approximate the operator.
```
__Note__ the use of `\citep{ref}` and `\citet{ref}` here.
Text `\citet{ref}` instances can be used as nouns but parenthetical references _cannot_.
* This is OK (via `\citet{ref}`):
    > So and so [1] did this awesome thing.
* This is not (via `\citep{ref}`):
    > [1] did this awesome thing.

Always prevent line-breaks via tides `~` between a parenthetical reference and the text before it.
For example:
* This is correct: `The algorithm is fast, but not as fast as possible~\citep{ref}.`
* This is not: `The algorithm is fast, but not as fast as possible \citep{ref}.`

We generally want our references at the end of sentences unless they are part of a long list.
* Incorrect:
    > The LBM method [1] is not as accurate as the finite volume method [2].
* Correct:
    > The LBM method is described in So and So [1]. However, is not as accurate as the finite volume method [2].
* And this is also acceptable
    > Cavitation is seen in many engineering applications, including submarines [1], pumps [2], and medical devices [3].

### Creating your bibliography

* Use `bibtool` to remove unused entries from your bibliography (`.bib`) file
    * Remove all unused bibliography entries from your `.bib` file. To do this, 
        * Make sure you have `bibtool` installed your your system
        * Copy a `bibtool.config` file to your document path, mine is located [here](../templates/paper/bibtool.config)
        * Compile your document (I prefer `latexmk` for this, but a combination of `pdflatex` and `bibtex` also works).
        * Use the command `bibtool -r bibtool.config -x main.aux > test.bib`
        * Now you have a file `test.bib` that contains only the bibliography entries in your document
        * Move the `test.bib` file over to your main bibliography file via something like `mv test.bib ref.bib`

* Use `bibstyle` to remove unneeded elements from your bibliography entries
    * In particular, I use the command `bibtex-tidy --omit=date-added,date-modified,month,doi --curly --numeric --align=13 --sort=title --duplicates=key,citation --no-escape --sort-fields --trailing-commas --no-remove-dupe-fields test.bib`
    * You can see above that it removes certain entries, sorts the document, checks for duplicates, etc.
    * It does this on `test.bib` in the above call. You will want to do it on whatever the `bibtool` output file is.

* Bibliography style file (`.bst`) 
    * Unless the journal or conference you submit to insists otherwise, use the style file [here](../templates/paper/bibsty.bst). This style file includes the relevant information you want your entries to include (like title), but ignores others (like month of publication). It also supports author-year citations (invoked via `\citet{}` as above).

### Colors

I like to use the following color palette in your TeX preamble:
```tex
\usepackage{xcolor}
\definecolor{lightblue}{rgb}{0.63, 0.74, 0.78}
\definecolor{seagreen}{rgb}{0.18, 0.42, 0.41}
\definecolor{orange}{rgb}{0.85, 0.55, 0.13}
\definecolor{silver}{rgb}{0.69, 0.67, 0.66}
\definecolor{rust}{rgb}{0.72, 0.26, 0.06}
\definecolor{purp}{RGB}{68, 14, 156}
\definecolor{joshua}{RGB}{251,220,127}

\colorlet{lightsilver}{silver!30!white}
\colorlet{darkorange}{orange!75!black}
\colorlet{darksilver}{silver!65!black}
\colorlet{darklightblue}{lightblue!70!black}
\colorlet{darkrust}{rust!85!black}
\colorlet{darkseagreen}{seagreen!85!black}
```
In particular, I use `darkrust` and `seagreen` quite a bit, as I find them complementary and easy on the eyes.

Setup your hyperrefs this way so that you have an attractive notation of your crossrefs in your document:
```tex
\usepackage[colorlinks=true,linkcolor=darkrust,citecolor=darklightblue,urlcolor=darksilver]{hyperref}
```

### Referencing equations, figures, tables, and sections

#### Figures, tables, sections

To keep things consistent, I recommend using the `cleveref` package
```tex
\usepackage{cleveref}
```
which is invoked for figures, tables, and sections via the commands `\Cref{}` and `\cref{}`, using the former if the reference is at the beginning of a sentence.
Figures, tables, and sections are always treated as nouns.
Check out the paper template in this repository for its use in the `preamble.tex` file.

#### Equations

First, labeling them appropriately as
```tex
\begin{gather}
    Ax=b
    \label{e:lineareqn}
\end{gather}
```
and then reference then via `cleveref`! As `\cref{e:lineareqn}`.

Treat your equations as nouns, and never use the abbreviation "eqn." before it.
* Like this: `The algorithm follows from reducing \eqref{e:someqn} to a first-order system.`
    * Which renders as: 
    > The algorithm follows from reducing (1) to a first-order system.
* Not like this: `The algorithm follows from reducing equation \eqref{e:someqn} to a first-order system.`
* Nor like this: `The algorithm follows from reducing eqn. \eqref{e:someqn} to a first-order system.`

### "Dashes"

Learn the difference between the hyphen (`-` in LaTeX), the en dash (`--` in LaTeX), and the em dash (`---` in LaTeX).
This is easily Google-able. Here are some references:
* https://grammarist.com/usage/hyphen-en-dash-or-em-dash/
* https://www.grammarly.com/blog/hyphens-and-dashes/
* https://editorninja.com/hyphen-vs-en-dash-vs-em-dash/

Some correct examples
* Hyphen
    * Separating words, such as "over-subscribed".
    * Some last names
* En dash
    * Separating two things that are different, like "Runge--Kutta" time stepping
    * Ranges, like "Steps 5--8 are unnecessary for algorithm X".
* Em dash
    * For putting a parenthetical in a sentence, like "I went to the grocery store---one that was extremely far away---and picked up cooking supplies."
        * I recommend avoiding the use of the em dash.


