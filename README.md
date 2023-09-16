# Latex Preamble File Repository

:exclamation: NOTE: Some of the package are comment out, check the TEX file for real inclusion.

## 1. Table of Contents
- [Base Preamble](#2-base-preamble)
- [Assignment Preamble](#3-preamble-for-assignments)


## 2. Base Preamble
### - File
- preamble.tex

### - Usage
> \input{preamble.tex}

### - Table of Settings
- [Encoding Settings](#-encoding-settings)
  - Set latex encoding mode.
- [Font Settings](#-font-settings)
  - Specify font to Times New Roman.
  - Define a font that will not be elongated in extremely small font size.
- [Paragraph Settings](#-paragraph-settings)
  - Set space between paragraphs
  - Set indent of paragraphs
- [Reference Settings](#-reference-settings)
  - Set biblatex format and set reference source file
  - Wrap long doi strings in reference
- [Figure Settings](#-figure-settings)
  - Basic figure package
  - Rename figure name from "Figure." to "Fig."
  - Enable figure floating
  - Enable two figures in one line
- [Array Settings](#-array-settings)
  - Basic Array pakcage
  - Define three column types with automatic math mode
  - Define a type of column using small font, align to right and adjust space automatically
  - Modify the space on the bottom and top of each cell
  - Some package required by www.tablesgenerator.com
  - Rename the Table name in supplymentary file from "Table X" to "Table SX"
  - Equally spread columns to fulfill the whole page
  - Define a horizontal line that only appears in specific columns:
- [Hyper-reference Settings](#-hyper-reference-settings)
  - Hyperref package setting, including link, cite and url color
  - Some redundent link color settings
  - Make the brackets of equation citation blue
- [Mathematical Settings](#-mathematical-settings)
  - Some basic mathmatical packages
  - Narrow paragraph skip between two equations
- [Equation Settings](#-equation-settings)
  - Set equation countings irrelevant to paragraph countings
- [Algorithm Settings](#-algorithm-settings)
  - Some basic sudo-algorithm packages
  - Reset the algorithm "Acquire" and "Ensure" to "Input" and "Output"
- [Enumerate Settings](#-enumerate-settings)
  - Set the enumerate item to use arabic tag
- [Line Number Settings](#-line-number-settings)
  - Enable line number of the document
- [Code Settings](#-code-settings)
  - Enable code display by importing code from a file
- [Subfile Settings](#-subfile-settings)
  - Enable each subfile to be compile independently but sharing the preamble of the main file
- [Attach File Settings](#-attach-file-settings)
  - Enable a PDF file to be attached to another PDF file
- [Additional Settings](#-additional-settings)
  - Define a new symbol: "Checkbox"

### - Detail Description of Settings:
#### \>>> Encoding Settings

```latex
% This two lines of code is used to set the encoding setting of latex files.
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
```

#### \>>> Font Settings

```latex
% Specify Times New Roman as the font used in the file.
\usepackage{times}
```

```latex
% Define a font type, called Tinyb, that will not be elongated in extremely small font size. 
\Tinyb  % Use just like \tiny or \normalsize
\usepackage{lmodern}
\rmfamily
\DeclareFontShape{T1}{lmr}{bx}{sc}{<-> cmr10}{}  % USE BOLD SCSHAPE NOT OTHERWISE DEFINED
%%% MATH FONT FIX
\DeclareFontFamily{OML}{zlmm}{}
\DeclareFontShape{OML}{zlmm}{m}{it}{<-> lmmi10}{}
\DeclareFontShape{OML}{zlmm}{b}{it}{<->ssub * zlmm/m/it}{}
\DeclareFontShape{OML}{zlmm}{bx}{it}{<->ssub * zlmm/m/it}{}
\DeclareMathVersion{Tinyb}
\SetSymbolFont{operators}{Tinyb}{T1}{lmr}{bx}{sc}
\SetSymbolFont{letters}{Tinyb}{OML}{zlmm}{m}{it}
\newenvironment{tinyb}{\bgroup\tiny\bfseries\scshape\mathversion{Tinyb}}{\egroup}
```

#### \>>> Paragraph Settings

```latex
% Set space between paragraphs
\usepackage{setspace}
\onehalfspacing
```

```latex
% Set indent of paragraphs
\usepackage{parskip}
\setlength{\parindent}{0in}
```

#### \>>> Reference Settings

```latex
% Set biblatex format and reference source file.
\usepackage[
    backend=biber,
    style=ieee,
]{biblatex}
\addbibresource{References.bib}
```

```latex
% Wrap long doi strings in reference
\setcounter{biburllcpenalty}{100}
\setcounter{biburlucpenalty}{100}
\setcounter{biburlnumpenalty}{100}
```

#### \>>> Figure Settings

```latex
% Basic figure package
\usepackage{graphicx} % Required for inserting images
```

```latex
% Rename figure name from "Figure." to "Fig."
\renewcommand{\figurename}{\textbf{Fig.}}
```

```latex
% Enable figure floating
\usepackage{float}
```

```latex
% Enable two figures in one line
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

#### \>>> Array Settings

```latex
% Basic Array pakcage
\usepackage{array}
```

```latex
% Define three column types with automatic math mode
\newcolumntype{R}{>{$}r<{$}} % math-mode version of "r" column type
\newcolumntype{C}{>{$}c<{$}} % math-mode version of "c" column type
\newcolumntype{L}{>{$}l<{$}} % math-mode version of "l" column type
```

```latex
% Define a type of column using small font, align to right and adjust space automatically
% Defines a new type of column called Y based on a X column (this column type 
% is defined by the tabularx package and it is basically a p{ <width>} column,
% where <width> is calculated by the package) but typesets the content using 
% \small font size and with ragged-right text.
\newcolumntype{Y}{>{\small\raggedright\arraybackslash}X}
```

```latex
% Modify the space on the bottom and top of each cell
\usepackage{cellspace}
\addtolength{\cellspacetoplimit}{5pt}
\addtolength{\cellspacebottomlimit}{5pt}
```

```latex
% Some package required by www.tablesgenerator.com
\usepackage{multirow}
\usepackage{tabularx,booktabs}
\usepackage{longtable}
\usepackage{relsize}
```

```latex
% Rename the Table name in supplymentary file from "Table X" to "Table SX"
\renewcommand{\thetable}{S\arabic{table}}
```

```latex
% Equally spread columns to fulfill the whole page
\begin{longtable}[c]{@{\extracolsep{\fill}}Lllllllll}
```

```latex
% Define a horizontal line that only appears in specific columns:
\usepackage{hhline}

% Command templage:
\hhline{~----~~}  % Use as \hline, but the column with ~ will not have a horizontal line.
```

#### \>>> Hyper-reference Settings

```latex
% Hyperref package setting, including link, cite and url color
\usepackage{hyperref}
\hypersetup{
    colorlinks=true,
    linkcolor=cyan,
    citecolor=cyan,
    urlcolor=cyan,
}
```

```latex
% Some redundent link color settings
\usepackage[all]{hypcap} 
\makeatletter
\AtBeginDocument{\def\@citecolor{cyan}}  % Define citing 
\AtBeginDocument{\def\@urlcolor{cyan}}
\AtBeginDocument{\def\@linkcolor{cyan}}
\makeatother
```

```latex
% Make the brackets of equation citation blue
\hyperref[eq:clpso_velocity]{(\ref*{eq:clpso_velocity})}
```

#### \>>> Mathematical Settings

```latex
% Some basic mathmatical packages
\usepackage{mathtools}
\usepackage{amssymb,mathrsfs}  % Typical maths resource packages
\usepackage{amsthm}
\usepackage{amsmath}
```

```latex
% Narrow paragraph skip between two equations
\usepackage{nccmath}

% Command template:
\useshortskip
```

#### \>>> Equation Settings

```latex
% Set equation countings irrelevant to paragraph countings
\counterwithout{equation}{chapter}
```

#### \>>> Algorithm Settings

```latex
% Some basic sudo-algorithm packages
\usepackage{algorithmic}
\usepackage{algpseudocodex}
```

```latex
% Reset the algorithm "Acquire" and "Ensure" to "Input" and "Output"
\renewcommand{\algorithmicrequire}{\textbf{Input:}}
\renewcommand{\algorithmicensure}{\textbf{Output:}}
```

#### \>>> Enumerate Settings

```latex
% Set the enumerate item to use arabic tag
\usepackage{enumitem}
\begin{enumerate}[label={(\arabic*).}]
    \item XXX
    \item XXX
\end{enumerate}
```

#### \>>> Line Number Settings

```latex
% Enable line number of the document
\usepackage{lineno}
\linenumbers  % Uncomment this line to turn on the line number settings
```
#### \>>> Code Settings

```latex
% Enable code display by importing code from a file
\usepackage{courier}
\usepackage{minted}
```

#### \>>> Subfile Settings

```latex
% Enable each subfile to be compile independently but sharing the preamble of the main file
\usepackage{subfiles}
\providecommand{\topdir}{.}
\addglobalbib{\topdir/References.bib}
```

#### \>>> Attach File Settings

```latex
% Enable a PDF file to be attached to another PDF file
\usepackage{attachfile}

% Command template:
\attachfile[icon=Paperclip]{Test.pdf}
```
 

#### \>>> Additional Settings

```latex
% Define a new symbol: "Checkbox"
\newcommand{\checkbox}[1]{%
  \ifnum#1=1
    \makebox[0pt][l]{\raisebox{0.15ex}{\hspace{0.1em}$\checkmark$}}%
  \fi
  $\square$%
}
```

## 3. Preamble for Assignments
### - File
- assignment_preamble.tex

### - Usage
> \input{assignment_preamble.tex}

Note: Do not `\input{preamble.tex}` again, since it is already input in the assignment_preamble.tex.

### - Table of Settings
- [Information Block Settings](#-information-block-settings) 

### - Detail Description of Settings:
#### \>>> Information Block Settings
```latex
% Print a information block
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