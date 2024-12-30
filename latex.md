# LaTex

References:

- [Wikibooks LaTeX Mathematics](https://en.wikibooks.org/wiki/LaTeX/Mathematics).
- Getting to Grip with LaTex — [Part 1](https://www.andy-roberts.net/latex/mathematics_1/) and [Part 2](https://www.andy-roberts.net/latex/mathematics_2/)
- Warbrick and Rivera. Essential LaTeX [PDF](https://us.mirrors.cicku.me/ctan/info/latex-essential/ess2e.pdf).
- David Carlisle. Summary of mathematical symbols available in LaTeX [PDF](http://mirrors.ctan.org/info/symbols/math/maths-symbols.pdf).

## Markdown

Keep in mind that your mathematics is part of a Markdown document, so you need to be aware of the special characters used by Markdown as part of its markup.

**GitHub** is [moving toward](https://github.blog/2017-03-14-a-formal-spec-for-github-markdown/) the CommonMark specification.

- In order to fully specify the version of Markdown we use at GitHub (known as GFM), we had to [formally define](https://github.github.com/gfm/) the syntax and semantics of these features &hellip;
- To ensure that the rendered Markdown in our website is fully compliant with the [CommonMark spec](https://spec.commonmark.org/), the new backend implementation for GitHub Flavored Markdown or GFM parsing on GitHub is based on `cmark` &hellip;
- From [2022-05-19](https://github.blog/2022-05-19-math-support-in-markdown/), you can use the `$` and `$$` delimiters natively in Markdown on GitHub to insert math expressions in TeX and LaTeX style syntax. This content is then rendered using the `MathJax` library.

**VS Code**

- [targets](https://code.visualstudio.com/docs/languages/markdown) the CommonMark Markdown specification using the `markdown-it` library, according to its document [site]()
- its built-in [Markdown preview](https://code.visualstudio.com/docs/languages/markdown#_math-formula-rendering) renders math equations using [KaTeX](https://katex.org/)


**Jupyter Notebook** interfaces use

- [Jupyter Notebook Markdown](https://jupyterbook.org/en/stable/file-types/markdown.html) is an extension of a flavour of Markdown called CommonMark Markdown.
- Jupyter Book also supports a more fully-featured version of Markdown called [MyST Markdown](https://mystmd.org/).
- [MathJax](http://docs.mathjax.org/) for [typesetting math](https://jupyterbook.org/en/stable/content/math.html) in your HTML book build.

Thus, mathematical expression renderers include:

- **MathJax**: A JavaScript display engine for mathematics.
  - [the MathJax documentation](http://docs.mathjax.org/en/latest/input/tex/index.html#tex-and-latex-support)
  - [the MathJax Accessibility Extensions Documentation](https://mathjax.github.io/MathJax-a11y/docs/#reader-guide)
- **KaTeX**: The fastest math typesetting library for the web.
  - [Supported Functions](https://katex.org/docs/supported)
  - [Common Issues](https://katex.org/docs/issues)

Refer to
- [CommonMark Spec](https://spec.commonmark.org/)
