tex2gv
======

Imagine you're working on a paper, it's almost finished, but then you
realize that there is a critical mistake in a highly technical
lemma. How do you figure out which results you need to update?

_tex2gv_ aims to help with this task. It puts out a dependency diagram
generated for LaTeX-refs that roughly look like this:

![Example output](https://g.gravizo.com/source/custom_mark10?https%3A%2F%2Fraw.githubusercontent.com%2Foqpvc%2Ftex2gv%2Fmaster%2FREADME.md)

<details>
<summary></summary>
custom_mark10
	digraph G {
       "lm:lovely-lemma" -> "prop:some-prop";
	   "lm:lovely-lemma" -> "thm:main-thm";
	   "lm:highly-technical-lemma" -> "prop:another-prop";
	   "lm:turns-out-to-be-wrong-lemma" -> "prop:another-prop";
	   "prop:another-prop" -> "thm:main-thm";
	}
custom_mark10
</details>

The more religously you correctly reference your own results, the more
information the graph of course contains. `tex2gv
very-important-paper.tex` outputs `very-important-paper.png` if
`graphviz` is installed.
