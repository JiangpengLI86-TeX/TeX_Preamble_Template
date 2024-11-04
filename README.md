# Latex Preamble Files Repository

- [Latex Preamble Files Repository](#latex-preamble-files-repository)
- [Usage](#usage)
- [Detail Description of Settings](#detail-description-of-settings)
    - [Algorithm Settings](#algorithm-settings)
    - [Attach File Settings](#attach-file-settings)
    - [Code Settings](#code-settings)
    - [Enumerate Settings](#enumerate-settings)
    - [Encoding Settings](#encoding-settings)
    - [Figure Settings](#figure-settings)
    - [Font Settings](#font-settings)
    - [Hyper-reference Settings](#hyper-reference-settings)
    - [Information Block Settings](#information-block-settings)
    - [Line Number Settings](#line-number-settings)
    - [Mathematical Settings](#mathematical-settings)
    - [Multi Columns Settings](#multi-columns-settings)
    - [New Symbol Settings](#new-symbol-settings)
    - [Paragraph Settings](#paragraph-settings)
    - [Reference Settings](#reference-settings)
    - [Subfile Settings](#subfile-settings)
    - [Table Settings](#table-settings)

# Usage

1. Include the main preamble file in the main latex file.
2. Select what options you want just like the following:

```latex
\input{src/preambles/main_preamble.tex}

\mypreamble{%
  core,
}
```

Your options are:

1. `core`, includes:
    1. [encoding-core](#encoding-core)
    2. [figure-core](#figure-core)
    3. [font-core](#font-core)
    4. [hyper-reference-core](#hyper-reference-core)
    5. [math-core](#math-core)
    6. [paragraph-core](#paragraph-core)
    7. [reference-core](#reference-core)
    8. [table-core](#table-core)
2. `algorithm-core`, includes:
    1. [algorithm-core](#algorithm-core)
3. `algorithm-change-input`, includes:
    1. [algorithm-core](#algorithm-core)
    2. [algorithm-change-input](#algorithm-change-input)
4. `attach-file-core`, includes:
    1. [attachfile-core](#attachfile-core)
5. `code-core`, includes:
    1. [code-core](#code-core)
6. `code-inline`, includes:
    1. [code-core](#code-core)
    2. [code-inline](#code-inline)
7. `code-block`, includes:
    1. [code-core](#code-core)
    2. [code-block](#code-block)
8. `enumerate-different-tag`, includes:
    1. [enumerate-different-tag](#enumerate-different-tag)
9. `figure-two-figures-in-one-line`, includes:
    1. [figure-core](#figure-core)
    2. [figure-two-figures-in-one-line](#figure-two-figures-in-one-line)
10. `font-tinyb`, includes:
    1. [font-core](#font-core)
    2. [font-tinyb](#font-tinyb)
11. `information-block`, includes:
    1. [information-block](#information-block)
12. `line-number`, includes:
    1. [line-number](#line-number)
13. `math-narrow-skip`, includes:
    1. [math-core](#math-core)
    2. [math-narrow-skip](#math-narrow-skip)
14. `math-more-symbols`, includes:
    1. [math-core](#math-core)
    2. [math-more-symbols](#math-more-symbols)
15. `math-unified-counting`, includes:
    1. [math-core](#math-core)
    2. [math-unified-counting](#math-unified-counting)
16. `multi-columns-core`, includes:
    1. [multi-columns-core](#multi-columns-core)
17. `new-checkbox`, includes:
    1. [new-checkbox](#new-checkbox)
18. `reference-break-long-doi`, includes:
    1. [reference-core](#reference-core)
    2. [reference-break-long-doi](#reference-break-long-doi)
19. `subfile-core`, includes:
    1. [subfile-core](#subfile-core)
20. `table-math-column`, includes:
    1. [table-core](#table-core)
    2. [table-math-column](#table-math-column)
21. `table-auto-width-column`, includes:
    1. [table-core](#table-core)
    2. [table-math-auto-width-column](#table-math-auto-width-column)
22. `table-modify-cell-space`, includes:
    1. [table-core](#table-core)
    2. [table-math-modify-cell-space](#table-math-modify-cell-space)
23. `table-supplementary-table`, includes:
    1. [table-core](#table-core)
    2. [table-supplementary-table](#table-supplementary-table)
24. `table-horizontal-line`, includes:
    1. [table-core](#table-core)
    2. [table-horizontal-line](#table-horizontal-line)

# Detail Description of Settings

## Algorithm Settings

***<u>algorithm-core</u>***
<a id="algorithm-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Some basic sudo-algorithm packages
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{algorithmic}
\usepackage{algpseudocodex}
```

</details>

***<u>algorithm-change-input</u>***
<a id="algorithm-change-input"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Reset the algorithm "Acquire" and "Ensure" to "Input" and "Output"
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\renewcommand{\algorithmicrequire}{\textbf{Input:}}
\renewcommand{\algorithmicensure}{\textbf{Output:}}
```

</details>

## Attach File Settings

***<u>attachfile-core</u>***
<a id="attachfile-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable a PDF file to be attached to another PDF file
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{attachfile}

% Command template:
\attachfile[icon=Paperclip]{Test.pdf}
```

</details>

## Code Settings

***<u>code-core</u>***
<a id="code-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable code display by importing code from a file
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{courier}
\usepackage{minted}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Basic packages for inline and code block printings
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{color,soul}
\definecolor{codegray}{gray}{0.9}  % Define a new color for code block background.
\usepackage{upquote}  % Ensure the ' mark is displayed correctly.
\usepackage{listings}  % Used for code printing.
```

</details>

***<u>code-inline</u>***
<a id="code-inline"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define an inline code display using gray background and ttfamily fonts
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcommand{\codeinline}[1]{\colorbox{codegray}{\lstinline[basicstyle=\ttfamily,breaklines=true]|#1|}}

% Command template:
\codeinline{Your codes here}
```

</details>

***<u>code-block</u>***
<a id="code-block"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define a text field that can store the code without line-breaking. 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Command template:
\codeblock{Your codes here}

% Note: hyperref package is required.

% Set up a counter for auto-labelling
\newcounter{codeCounter}

% Setup the text field command. Check the hyperref package documentation for more set up options
\newcommand{\codeblock}[1]
{   
   \stepcounter{codeCounter}
   \TextField[default=\detokenize{#1}, width=0.9\columnwidth, height=15pt, charsize=12pt,
   ]{\thecodeCounter}
}
% suppress the label behind the text field:
\def\LayoutTextField#1#2{% label, field
 #2%
}
```

</details>

## Enumerate Settings

***<u>enumerate-different-tag</u>***
<a id="enumerate-different-tag"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set the enumerate item to use arabic tag
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{enumitem}

% Command template:
\begin{enumerate}[label={(\arabic*).}]
    \item XXX
    \item XXX
\end{enumerate}
```

</details>

## Encoding Settings

***<u>encoding-core</u>***
<a id="encoding-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set the encoding setting of latex files.
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage[T1]{fontenc}  % This is especially useful for European languages that use accented characters.
\usepackage[utf8]{inputenc}  % Use UTF-8 encoding
```

</details>

## Figure Settings

***<u>figure-core</u>***
<a id="figure-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Basic figure package
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{graphicx}  % Required for inserting images
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Rename figure name from "Figure." to "Fig."
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\renewcommand{\figurename}{\textbf{Fig.}}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable figure floating
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{float}
```

</details>

***<u>figure-two-figures-in-one-line</u>***
<a id="figure-two-figures-in-one-line"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable two figures in one line
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{subfig}

% Command template:
\begin{figure}[htbp!]
  \centering
  \subfloat[Before re-initialization]{\includegraphics[width=0.5\textwidth]{Figures/Before re-initialization.pdf}\label{fig:f1}}
  \hfill
  \subfloat[After re-initialization]{\includegraphics[width=0.5\textwidth]{Figures/After re-initialization.pdf}\label{fig:f2}}
  \centering
  \caption{Swarm distribution before and after reinitializing transitional particles on a one-dimensional problem}
  \label{fig:before_and_after_reinitialization}
\end{figure}
```

</details>

## Font Settings

***<u>font-core</u>***
<a id="font-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Specify Times New Roman as the font used in the file.
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{times}
```

</details>

***<u>font-tinyb</u>***
<a id="font-tinyb"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define a font type, called Tinyb, that will not be elongated in extremely small font size. 
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\Tinyb  % Define a new font type, Tinyb.
\usepackage{lmodern}  % Provide better scalability and font shapes for different sizes and weights.
\rmfamily
\DeclareFontShape{T1}{lmr}{bx}{sc}{<-> cmr10}{}
\DeclareFontFamily{OML}{zlmm}{}
\DeclareFontShape{OML}{zlmm}{m}{it}{<-> lmmi10}{}
\DeclareFontShape{OML}{zlmm}{b}{it}{<->ssub * zlmm/m/it}{}
\DeclareFontShape{OML}{zlmm}{bx}{it}{<->ssub * zlmm/m/it}{}
\DeclareMathVersion{Tinyb}
\SetSymbolFont{operators}{Tinyb}{T1}{lmr}{bx}{sc}
\SetSymbolFont{letters}{Tinyb}{OML}{zlmm}{m}{it}
\newenvironment{tinyb}{\bgroup\tiny\bfseries\scshape\mathversion{Tinyb}}{\egroup}
```

</details>

## Hyper-reference Settings

***<u>hyper-reference-core</u>***
<a id="hyper-reference-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Hyperref package setting, including link, cite and url color
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{hyperref}
\hypersetup{
    colorlinks=true,
    linkcolor=cyan,
    citecolor=cyan,
    urlcolor=cyan,
}
\makeatletter  % Allow manipulation of internal LaTeX macros.
\AtBeginDocument{\def\@citecolor{cyan}}  % Redefines the internal LaTeX color used for citation links. Executed at the beginning of the document.
\AtBeginDocument{\def\@urlcolor{cyan}}
\AtBeginDocument{\def\@linkcolor{cyan}}
\makeatother
```

</details>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Make the brackets of equation citation blue
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Command template:
\hyperref[eq:clpso_velocity]{(\ref*{eq:clpso_velocity})}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Some redundant link color settings
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% The hypcap package is used to fix a common issue with hyperlinks in documents that contain figures and tables. By default, when clicking on a hyperlink to a figure or table, the link takes you to the beginning of the caption instead of the figure or table itself.
% The all option tells hypcap to apply this fix to all types of floats
\usepackage[all]{hypcap}
```

## Information Block Settings

***<u>information-block</u>***
<a id="information-block"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Print a information block
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% #1: Course Code, #2: Course Name, #3 Assignment Index, #4 Date
\newcommand{\assignment}[4]{
  \noindent
  \begin{center}
  \framebox{
    \vbox{
      \hbox to 6in {\bf #1 - #2 \hfill EEE @ NTU, Singapore}
      \vspace{5mm}
      \hbox to 6in { {\Large \hfill Assignment ~#3  \hfill} }
      \vspace{5mm}
      \hbox to 6in { {\bf Li Jiangpeng, G2304933F  \hfill #4}}
    }
  }
  \end{center}
  \vspace*{4mm}
}

% Command template:
\assignment{EE7401}{Probability and Random Processes}{2}{September 2023}
```

</details>

## Line Number Settings

***<u>line-number</u>***
<a id="line-number"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable line number of the document
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{lineno}
\linenumbers  % Uncomment this line to turn on the line number settings
```

</details>

## Mathematical Settings

***<u>math-core</u>***
<a id="math-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Some basic mathmatical packages
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{mathtools}
\usepackage{amssymb,mathrsfs}  % Typical maths resource packages
\usepackage{amsthm}
\usepackage{amsmath}
```

</details>

***<u>math-narrow-skip</u>***
<a id="math-narrow-skip"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Narrow paragraph skip between equation and its previous paragraph
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{nccmath}

% Command template:
\useshortskip
```

</details>

***<u>math-more-symbols</u>***
<a id="math-more-symbols"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable the usage of some symbols in the math mode
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\mathds{P}  % Symbol for probability
\mathbb{E}  % Symbol for expectation

\usepackage{cancel}  % Enable cancel symbol in equations. Template: \cancel{XXX}
```

</details>

***<u>math-unified-counting</u>***
<a id="math-unified-counting"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set equation counting irrelevant to paragraph counting
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\counterwithout{equation}{chapter}
```

</details>

## Multi Columns Settings

***<u>multi-columns-core</u>***
<a id="multi-columns-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable multicolumn format in the page
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{multicol}
\usepackage{color}  % For color used column separator
\setlength{\columnsep}{0.2cm}  % Set Column separation
\setlength{\columnseprule}{1pt}
\def\columnseprulecolor{\color{blue}}  % Add a vertical line between two columns.

% Command template:
\begin{multicols}{4}  % Four column format

\end{multicols}
```

</details>

## New Symbol Settings

***<u>new-checkbox</u>***
<a id="new-checkbox"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define a new symbol: "Checkbox"
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcommand{\checkbox}[1]{%
  \ifnum#1=1
    \makebox[0pt][l]{\raisebox{0.15ex}{\hspace{0.1em}$\checkmark$}}%
  \fi
  $\square$%
}
```

</details>

## Paragraph Settings

***<u>paragraph-core</u>***
<a id="paragraph-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set space between paragraphs
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{setspace}
\onehalfspacing
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set indent of paragraphs
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{parskip}
\setlength{\parindent}{0in}
```

</details>

## Reference Settings

***<u>reference-core</u>***
<a id="reference-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set biblatex format and reference source file.
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage[
    backend=biber,  % It supports UTF-8 encoding and offers better handling of modern bibliography features, such as sorting and field mapping.
    style=ieee,
    maxbibnames=3,  % Maximum number of authors to be displayed in the bibliography
    citestyle=numeric-comp,  % Put multiple citations in one bracket
    hyperref=true,  % Enable hyperlinks in the bibliography
    backref=true,  % Enable back references in the bibliography
]{biblatex}
\addbibresource{references.bib}
```

</details>

***<u>reference-break-long-doi</u>***
<a id="reference-break-long-doi"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Elegantly break long doi field
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\setcounter{biburllcpenalty}{100}
\setcounter{biburlucpenalty}{100}
\setcounter{biburlnumpenalty}{100}
```

</details>

## Subfile Settings

***<u>subfile-core</u>***
<a id="subfile-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable each subfile to be compile independently but sharing the preamble of the main file
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{subfiles}  % Manage large LaTeX projects by splitting them into multiple smaller files.
\providecommand{\topdir}{.}  % Create a consistent reference point for all files
\addglobalbib{\topdir/references.bib}
```

</details>

## Table Settings

***<u>table-core</u>***
<a id="table-core"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Basic Array package
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{array}
\usepackage{tabularx}
\usepackage{multirow}
\usepackage{booktabs}
\usepackage{longtable}
\usepackage{relsize}
```

</details>

***<u>table-math-column</u>***
<a id="table-math-column"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define three column types with automatic math mode
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcolumntype{R}{>{$}r<{$}} % math-mode version of "r" column type
\newcolumntype{C}{>{$}c<{$}} % math-mode version of "c" column type
\newcolumntype{L}{>{$}l<{$}} % math-mode version of "l" column type
```

</details>

***<u>table-math-auto-width-column</u>***
<a id="table-math-auto-width-column"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define a type of column using small font, align to right and adjust space automatically
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Defines a new type of column called Y based on a X column (this column type 
% is defined by the tabularx package and it is basically a p{ <width>} column,
% where <width> is calculated by the package) but typesets the content using 
% \small font size and with ragged-right text.
\newcolumntype{Y}{>{\small\raggedright\arraybackslash}X}
```

</details>

***<u>table-math-modify-cell-space</u>***
<a id="table-math-modify-cell-space"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Modify the space on the bottom and top of each cell
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{cellspace}
\addtolength{\cellspacetoplimit}{5pt}
\addtolength{\cellspacebottomlimit}{5pt}
```

</details>

***<u>table-supplementary-table</u>***
<a id="table-supplementary-table"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Rename the Table name in supplymentary file from "Table X" to "Table SX"
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\renewcommand{\thetable}{S\arabic{table}}
```

</details>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Equally spread columns to fulfill the whole page
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\begin{longtable}[c]{@{\extracolsep{\fill}}Lllllllll}
\end{longtable}
```

***<u>table-horizontal-line</u>***
<a id="table-horizontal-line"></a>

<details>
<summary class="custom-summary">Click to expand</summary>

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define a horizontal line that only appears in specific columns:
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{hhline}

% Command templage:
\hhline{~----~~}  % Use as \hline, but the column with ~ will not have a horizontal line.
```

</details>

<style>
.custom-summary {
    color: blue;
    font-weight: bold;
    text-decoration: underline;
    font-size: 0.8em;
    padding: 5px;
    border-radius: 4px;
    cursor: pointer;
    transition: color 0.3s ease;
}
.custom-summary:hover {
    color: red;
}
</style>

<!-- background-color: lightyellow;
border: 1px solid #ccc; -->