# LaTeX

## Agenda
1. Preliminaries
2. Basic Writing and Document Structure
3. Mathematical Equations
4. Sharing and Collaborative Editing
5. Bibliographies and References
6. Figures and Images
7. Tables
8. Show and Tell(?)

## Preliminaries
1. Log in to [Overleaf](https://www.overleaf.com/) (create a free account if you haven't already).
2. Create a new project, using the 'Blank Paper' template.

## Basic Writing and Document Structure
Our template gives us some bare minimal text to start a valid `.tex` file:

```tex
\documentclass{article}
\usepackage[utf8]{inputenc}
\begin{document}
(Type your content here.)
\end{document}
```

1. Write some prose, gibberish or grab some text to insert into your document.
2. Divide the text into several sections using the `\section{}` and `\subsection{}`
3. Insert a table of contents by adding `\tableofcontents` after `\maketitle`

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

Much more detailed instructions for mathematical typesetting can be found on the [LaTeX WikiBook](https://en.wikibooks.org/wiki/LaTeX/Mathematics)

## Sharing and Collaborative Editing
1. Find a buddy (or two) to work with for a brief collaborative editing exercise
2. Click on the 'Share' button at the top of the site.
3. Choose a collaborative editing method that works well for you (link sharing or git repository)

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
      style=ieee,
      sorting=ynt
    ]{biblatex}
    
    \addbibresource{references.bib}
``` 

4. Include a citation somewhere in your text by adding `\cite{venter2001sequence}`

### Challenge
1. Include three references in your file.
2. Change the reference style.

## Figures & Images
Let's insert a figure into our document. Use this one, or find another picture from the web. You'll need to upload it into your Overleaf project before you can insert it into the document. Use these images or find some of your own on the web:

<img src="images/urchin-01.jpg" width="100">

<img src="images/urchin-02.jpg" width="100">

<img src="images/urchin-03.jpg" width="100">

<img src="images/urchin-04.jpg" width="100">

### Adding a Single Figure

```tex
\begin{figure}[h]
  \label{fig:urchin-01}
  \centering
  \includegraphics[width=0.5\textwidth]{images/urchin-01}
  \caption{Ultimate proof of the secrets of the universe.}
\end{figure}
```

### Adding Multiple Figures

```tex
\begin{figure}
    \centering
    \begin{subfigure}[b]{0.25\textwidth}
        \includegraphics[width=\textwidth]{images/urchin-01}
        \caption{An urchin}
        \label{fig:urchin-01}
    \end{subfigure}
    ~ %add desired spacing between images, e. g. ~, \quad, \qquad, \hfill etc. 
      %(or a blank line to force the subfigure onto a new line)
    \begin{subfigure}[b]{0.25\textwidth}
        \includegraphics[width=\textwidth]{images/urchin-02}
        \caption{Another urchin}
        \label{fig:urchin-02}
    \end{subfigure}
    \caption{Urchins.}
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
