# Latex Preamble File Repository

:exclamation: NOTE: Some of the package are comment out, check the TEX file for real inclusion.

- [Latex Preamble File Repository](#latex-preamble-file-repository)
  - [Usage](#usage)
  - [Detail Description of Settings](#detail-description-of-settings)
    - [Encoding Settings](#encoding-settings)
    - [Multi Columns Settings](#multi-columns-settings)
    - [Font Settings](#font-settings)
    - [Paragraph Settings](#paragraph-settings)
    - [Reference Settings](#reference-settings)
    - [Figure Settings](#figure-settings)
    - [Table Settings](#table-settings)
    - [Hyper-reference Settings](#hyper-reference-settings)
    - [Mathematical Settings](#mathematical-settings)
    - [Algorithm Settings](#algorithm-settings)
    - [Enumerate Settings](#enumerate-settings)
    - [Line Number Settings](#line-number-settings)
    - [Code Settings](#code-settings)
    - [Subfile Settings](#subfile-settings)
    - [Attach File Settings](#attach-file-settings)
    - [New Symbol Settings](#new-symbol-settings)
    - [Information Block Settings](#information-block-settings)

## Usage

Put following code in the main file:

```latex
\input{preamble.tex}
```

## Detail Description of Settings

### Encoding Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set the encoding setting of latex files.
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage[T1]{fontenc}  % This is especially useful for European languages that use accented characters.
\usepackage[utf8]{inputenc}  % Use UTF-8 encoding
```

### Multi Columns Settings

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

### Font Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Specify Times New Roman as the font used in the file.
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{times}
```

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

### Paragraph Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set space between paragraphs
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{setspace}
\onehalfspacing
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set indent of paragraphs
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{parskip}
\setlength{\parindent}{0in}
```

### Reference Settings

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

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Elegantly break long doi field
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\setcounter{biburllcpenalty}{100}
\setcounter{biburlucpenalty}{100}
\setcounter{biburlnumpenalty}{100}
```

### Figure Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Basic figure package
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{graphicx}  % Required for inserting images
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Rename figure name from "Figure." to "Fig."
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\renewcommand{\figurename}{\textbf{Fig.}}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable figure floating
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{float}
```

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

### Table Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Basic Array package
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{array}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define three column types with automatic math mode
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcolumntype{R}{>{$}r<{$}} % math-mode version of "r" column type
\newcolumntype{C}{>{$}c<{$}} % math-mode version of "c" column type
\newcolumntype{L}{>{$}l<{$}} % math-mode version of "l" column type
```

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

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Modify the space on the bottom and top of each cell
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{cellspace}
\addtolength{\cellspacetoplimit}{5pt}
\addtolength{\cellspacebottomlimit}{5pt}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Some package required by www.tablesgenerator.com
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{multirow}
\usepackage{tabularx,booktabs}
\usepackage{longtable}
\usepackage{relsize}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Rename the Table name in supplymentary file from "Table X" to "Table SX"
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\renewcommand{\thetable}{S\arabic{table}}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Equally spread columns to fulfill the whole page
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\begin{longtable}[c]{@{\extracolsep{\fill}}Lllllllll}
\end{longtable}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define a horizontal line that only appears in specific columns:
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{hhline}

% Command templage:
\hhline{~----~~}  % Use as \hline, but the column with ~ will not have a horizontal line.
```

### Hyper-reference Settings

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

### Mathematical Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Some basic mathmatical packages
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{mathtools}
\usepackage{amssymb,mathrsfs}  % Typical maths resource packages
\usepackage{amsthm}
\usepackage{amsmath}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Narrow paragraph skip between equation and its previous paragraph
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{nccmath}

% Command template:
\useshortskip
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable the usage of some symbols in the math mode
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\mathds{P}  % Symbol for probability
\mathbb{E}  % Symbol for expectation

\usepackage{cancel}  % Enable cancel symbol in equations. Template: \cancel{XXX}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Set equation counting irrelevant to paragraph counting
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\counterwithout{equation}{chapter}
```

### Algorithm Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Some basic sudo-algorithm packages
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{algorithmic}
\usepackage{algpseudocodex}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Reset the algorithm "Acquire" and "Ensure" to "Input" and "Output"
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\renewcommand{\algorithmicrequire}{\textbf{Input:}}
\renewcommand{\algorithmicensure}{\textbf{Output:}}
```

### Enumerate Settings

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

### Line Number Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable line number of the document
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{lineno}
\linenumbers  % Uncomment this line to turn on the line number settings
```

### Code Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable code display by importing code from a file
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{courier}
\usepackage{minted}
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Basic packages for inline and code block printings
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{color,soul}
\definecolor{codegray}{gray}{0.9}  % Define a new color for code block background.
\usepackage{upquote}  % Ensure the ' mark is displayed correctly.
\usepackage{listings}  % Used for code printing.
```

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Define an inline code display using gray background and ttfamily fonts
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newcommand{\codeinline}[1]{\colorbox{codegray}{\lstinline[basicstyle=\ttfamily,breaklines=true]|#1|}}

% Command template:
\codeinline{Your codes here}
```

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

### Subfile Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable each subfile to be compile independently but sharing the preamble of the main file
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{subfiles}  % Manage large LaTeX projects by splitting them into multiple smaller files.
\providecommand{\topdir}{.}  % Create a consistent reference point for all files
\addglobalbib{\topdir/references.bib}
```

### Attach File Settings

```latex
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Enable a PDF file to be attached to another PDF file
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{attachfile}

% Command template:
\attachfile[icon=Paperclip]{Test.pdf}
```

### New Symbol Settings

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

### Information Block Settings

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
