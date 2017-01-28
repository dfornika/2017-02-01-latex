# Intro to LaTeX

## Preliminaries
1. Log in to [ShareLaTeX](https://www.sharelatex.com/) (create a free account if you haven't already).
2. Create a new project, name it whatever you'd like (eg. 'latex workshop')

## Basic Writing and Document Structure
1. Copy the paragraphs below into your `main.tex` file after `\maketitle`

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla ac euismod diam, a semper neque. Vivamus ullamcorper enim et ultrices sodales. Pellentesque in neque quis justo tristique mollis eget luctus ligula. Nam enim elit, pretium at metus et, sodales aliquet nisl. Donec gravida elit varius arcu condimentum eleifend. Donec vitae commodo dui. Vivamus finibus enim at congue ultrices. In hac habitasse platea dictumst. Ut tincidunt urna quis mauris facilisis lacinia. Integer lorem augue, porttitor faucibus varius ac, vulputate et lectus. Pellentesque non mauris eget orci volutpat congue vel in ipsum. Aliquam tincidunt, metus vestibulum vestibulum dignissim, neque lectus ultrices mauris, non faucibus ante diam vel enim. Nullam tristique vel erat vel tempus. Nulla at elementum lectus.

    Etiam vel augue in sapien euismod congue vitae a justo. Sed facilisis dolor eu lacus rhoncus placerat. Aliquam eu urna convallis, convallis eros quis, scelerisque dolor. Maecenas condimentum ligula nibh, quis finibus lorem blandit nec. Nulla tristique facilisis ex eget placerat. Maecenas tincidunt, sapien vel accumsan placerat, augue leo fringilla leo, at suscipit risus massa eget purus. Proin sit amet sapien sit amet sapien dapibus facilisis in vitae ipsum. Phasellus consequat iaculis sodales. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nullam sed convallis mauris. Maecenas finibus elementum dignissim. In eleifend nisi id risus tincidunt convallis hendrerit at lacus. Pellentesque gravida ipsum vitae orci luctus, quis pulvinar sapien ornare.

2. Hit the blue `Recompile` button to update your .pdf preview.
3. Divide the text into several sections using the `\section{}` and `\subsection{}`
4. Insert a table of contents by adding `\tableofcontents` after `\maketitle`

### Challenge
If you're writing a large document (book, thesis etc.) it is good practice to create a separate file for each chapter, then insert it into your `main.tex` file with the `\input{}` command.

1. Create a new file, called `chapter1.tex` and enter some filler text.
2. Add `\input{chapter1}` to your `main.tex` file at the location where you'd like the contents of the `chapter1.tex` file inserted.

## Mathematical Equations
Equations can be inserted in-line between `$$` symbols, or inside an `equation` block:

```tex
\begin{equation}
  \sum_{x=0}^n f(x)
\end{equation}
```

Note that equations are automatically numbered. We can give equations labels and then refer to them within the body of our text.

```tex
\begin{equation}
  \label{eqn:sum}
  \sum_{x=0}^n f(x)
\end{equation}
```

We use the command `\ref{eqn:sum}` to generate a numbered reference to that equation. References will update automatically if equations are moved around or re-ordered.

### Some Useful Equation-Building Notation
- Exponent: `^` eg: `e^{x}`
- Subscript: `_` eg: `x_{i}`
- Multiplication: `\times` eg: `5 \times 8`
- Fractions: `\frac{}{}` eg: `\frac{x}{y}`
- Summation: `\sum{}` eg: `\sum_{n=0}^{\infty} x_{n}`
- Product: `\prod_{n=1}^{100} x_{n}`
- Radicals: `\sqrt[]{}` eg: `\sqrt{64}` or `\sqrt[3]{64}`

### Challenge
1. Use the equation-building notation above to build a big, complex equation (don't worry about mathematical validity). Look up one additional mathematical symbol or operator to use (factorials? trigonometric functions? set operations?)
2. Refer to your big complex equation somewhere in your text body.

## Bibliography & References
LaTeX uses a system called BibTeX to insert references. You can get BibTeX references from Google Scholar.

1. Create a new file called `references.bib`
2. Paste this into your `.bib` file

```
    @article{venter2001sequence,
      title={The sequence of the human genome},
      author={Venter, J Craig and Adams, Mark D and Myers, Eugene W and Li, Peter W and Mural, Richard J and Sutton, Granger G and Smith, Hamilton O and Yandell, Mark and Evans, Cheryl A and Holt, Robert A and others},
      journal={science},
      volume={291},
      number={5507},
      pages={1304--1351},
      year={2001},
      publisher={American Association for the Advancement of Science}
    }
```

3. Enter the following into the top of your `main.tex` file:

```
    \usepackage[
    backend=biber,
    style=numeric,
    sorting=ynt
    ]{biblatex}
    
    \addbibresource{references.bib}
``` 

4. Include a citation somewhere in your text by adding `\cite{venter2001sequence}`

### Challenge
1. Include three references in your file.
2. Change the reference style.

## Figures & Images
Let's insert a figure into our document. Use this one, or find another picture from the web. You'll need to upload it into your ShareLaTeX project before you can insert it into the document.
![Geometry](http://latex.artofproblemsolving.com/4/7/7/4776110780647e87b624afb7a2d6e65612ad4595.png)

```tex
\begin{figure}[h]
  \label{fig:geometry}
  \centering
  \includegraphics[width=0.5\textwidth]{figures/geometry}
  \caption{Ultimate proof of the secrets of the universe.}
\end{figure}
```

## Tables
Tables can be a real pain in LaTeX! For large or complex tables, find a tool to help generate your table:
- http://www.tablesgenerator.com/

```tex
\begin{table}[]
  \centering
  \caption{It gets colder every day.}
  \label{table:temperature}
    \begin{tabular}{l l}
      Date       & Temperature \\
      2016-11-18 & 10          \\
      2016-11-19 & 9           \\
      2016-11-20 & 6          
  \end{tabular}
\end{table}
```

## Additional Resources
- https://www.sharelatex.com/learn
- http://tex.stackexchange.com/
- https://en.wikibooks.org/wiki/LaTeX
- http://www.lib.sfu.ca/help/publish/thesis/templates#latex
- https://www.tug.org/texlive/
