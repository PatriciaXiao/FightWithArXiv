# Fighting with ArXiv

As a beginner, I suffered from uploading to ArXiv, a lot.

I hope recording these struggles down will help others solve these issues more easily.

## Error 1: .bbl not found (Overlead user)

When ArXiv tells you to find the .bbl file, there are [ways](https://tex.stackexchange.com/questions/329198/how-to-obtain-and-use-the-bbl-file-in-my-tex-document-for-arxiv-submission) of manually create it, however, the best way to solve it is to let Overleaf generate it for you.

Click Submission and find ArXiv, you'll know how to follow the steps.

## Error 2: hyperref problem

```
! LaTeX Error: Option clash for package hyperref.
```
You might want to remove where hyperref is included to solve it, but in fact this is not the best solution.

Sometimes removing the hyperref options might cause you some unexpected problems.

To solve it, the best way is to try forcing ArXiv to use pdflatex first, see whether or not it works.

## Error 3: no error message, simply can't generate PDF file

I don't know what exactly went wrong.

At this stage, I suspect that the problem was: figures / other files couldn't be recognized by tex. Have to use pdflatex to do process it.
* [official explanation on how to force the use of pdflatex](https://arxiv.org/help/submit_tex#pdflatex)
* [otherwise how could there be problems (e.g. ps/eps formats for figures only)](https://arxiv.org/help/faq/mistakes)

The fixation of this (**as well as Error 2 I've faced**):
```
\pdfoutput=1
```
added in the first 5 lines of my main tex file.

It could be done on Overleaf, and then use the submit option again => this time everything works perfectly

## Error 4: not found family_i in .bbl

I suspect that this was version issue. It happened for an old project I have, in 2016 ver (now it is 2019).

