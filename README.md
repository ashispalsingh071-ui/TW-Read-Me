# Technical Writing: Documents, Code Documentation and Version Control

Technical writing is not just about typing information. A technical document should be arranged in such a way that somebody else can follow an explanation, locate an equation, understand a diagram, and find the details they need. For software, this also means explaining functions and keeping track of changes in project files. The topics covered here include document preparation in LaTeX, creating presentations with Beamer, documenting source code with Doxygen, collaborative writing in Google Docs, and using Git and GitHub to maintain projects.

## Why LaTeX Is Used for Technical Documents

LaTeX is a document preparation system built on TeX. Its main difference from an ordinary word processor is the way a document is written. Instead of changing the look of every heading or formula with buttons, the content is written with commands. LaTeX then uses those commands to prepare the output. This is helpful for lengthy assignments, scientific reports and documents containing mathematical notation.

A LaTeX source file normally ends with .tex. It can contain both ordinary sentences and instructions for page layout, mathematics, tables and figures. After compilation, a PDF can be produced. The source file and the finished document are different things: the .tex file is edited, while the PDF is generally the result that gets shared or printed.

Another useful part of LaTeX is consistency. When sections are declared properly, headings follow the same style across the document. Equation numbers, table numbers and references can also be handled automatically. This becomes especially useful when material is added or moved after the first draft.

## Editors, Distributions and Compiling

A LaTeX editor provides a place to write source code. TeXstudio is one example. A TeX distribution, such as TeX Live or MiKTeX, supplies the programs and packages needed to compile the file. These have different roles even though both are needed in a typical offline setup.

Overleaf is an online option where LaTeX files can be written and compiled in a browser. It is also convenient when a document is being worked on from different computers. The basic idea is the same whether an online or offline editor is used: write a .tex file, compile it, inspect the result and fix any problems.

For a straightforward PDFLaTeX document, a command such as pdflatex report.tex can be used. Compilation sometimes needs to run more than once, especially when the document includes a table of contents or cross-references. A PDF being generated does not always mean the layout is correct, so checking the final pages is important.

## Building the First LaTeX File

A LaTeX document usually starts by declaring its class. For example, \documentclass{article} selects the article class. The command \documentclass[12pt,a4paper]{article} additionally specifies a basic font size and paper size. These options are written in square brackets, while the document class name is placed in braces.

The material before \begin{document} is known as the preamble. Packages and layout settings are commonly written there. The main text comes after \begin{document}, and \end{document} marks the end of the document body. This arrangement is important because instructions meant for the preamble may not work if they are placed in the middle of ordinary text.

Different document classes exist for different types of writing. An article is suitable for shorter reports, a report or book can contain chapters, and the letter class supports formal letters. Beamer is a class used for slide presentations. Selecting the class at the beginning saves the effort of adjusting the entire document structure later.

## Adding Packages and Understanding Commands

A package supplies commands or environments that are not necessarily available in a basic document. For example, \usepackage{amsmath} is helpful for mathematical writing, \usepackage{graphicx} is used to insert images, and \usepackage{xcolor} allows coloured content. Packages are normally included in the preamble.

LaTeX commands often begin with a backslash. Some commands take an argument in braces, and some also accept optional arguments in square brackets. The distinction can be seen in \includegraphics[width=5cm]{diagram.png}. The image filename is the required argument, while the width setting is optional.

Special characters should be handled carefully. A percent sign starts a comment in LaTeX source, so typing 50% directly can cause the rest of the line to be ignored. To print a percent sign, use \%. Similarly, \& prints an ampersand and \_ prints an underscore. These are small details, but many unexpected errors come from a missing escape character or an unmatched brace.

## Titles, Headings and Navigation

A proper report should be easy to navigate. LaTeX provides commands such as \section{Introduction}, \subsection{Background} and \subsubsection{Method}. The levels show which material belongs under which heading. Numbering is generated automatically, so inserting another section does not require manually renumbering the whole document.

The commands \title, \author and \date can hold the information used on the document's title. The command \maketitle displays the title block. A longer report may also contain an abstract, which is written inside the abstract environment. Not every assignment needs all of these parts; the choice depends on the document.

For documents with several sections, \tableofcontents creates a list of headings. LaTeX takes the entries from the sectioning commands rather than requiring the page numbers to be typed by hand. A heading can be left unnumbered by using the starred version, such as \section*{Acknowledgements}. If headings or page numbers change, compiling again updates the contents information.

## Page Layout, Margins and Headers

Page layout includes paper size, margins, numbering and the position of headers or footers. These details may not change the meaning of the writing, but they affect how comfortable the document is to read. A short document with only a few paragraphs might not need special settings, while a report may have a required margin size or header format.

The geometry package provides a direct way to set margins. For example, \usepackage[margin=2.5cm]{geometry} gives a common margin value on all sides. Separate left, right, top and bottom values can also be used when needed. Page styles include plain, empty and headings. The plain style typically displays a page number; empty omits header and footer information.

More detailed headers and footers can be made through the fancyhdr package. The commands provided by that package allow text or page numbers to be placed at different positions. A document should not be filled with formatting changes without a reason. Keeping the same margin and header style throughout a report is usually more useful than changing them on each page.

## Paragraphs, Lists and Text Appearance

LaTeX usually treats a blank line in the source as the start of a new paragraph. Pressing Enter only once inside a paragraph generally does not create a separate paragraph in the PDF. This can be confusing at first because the source file and compiled document do not have identical line breaks.

Text can be changed using commands such as \textbf{important}, \textit{example} and \underline{term}. They make text bold, italic or underlined. Alignment can be changed with environments such as center, flushleft and flushright. Space can be adjusted using commands including \hspace and \vspace, though these should be used only when the ordinary layout needs adjustment.

Lists are written using environments. The itemize environment creates a bulleted list, while enumerate produces numbering. Individual entries use \item. The description environment is suitable when a short term is followed by an explanation. Lists help when there are several related steps, but a paragraph is often clearer for a concept that needs a continuous explanation.

## Mathematics: Inline and Display Equations

Mathematical writing is one of the strongest reasons for using LaTeX. A small expression can appear within a sentence in inline math mode, such as $a+b=c$. A more important equation can be displayed on its own line using \[ and \]. Display equations are easier to notice and usually have more room for fractions and symbols.

For equations that need a number, the equation environment can be used. The align environment from amsmath is useful for calculations written over several lines. It allows equal signs or other parts of expressions to line up instead of appearing at slightly different positions. An equation does not need to be numbered merely because it is mathematical; numbering is most useful when it will be discussed later.

Superscripts use ^ and subscripts use _. For example, a^2 produces a square, and a_{12} places 12 as a subscript. Braces matter when more than one character belongs in the exponent or subscript. Fractions use \frac{numerator}{denominator}, and roots can be written with \sqrt{value} or \sqrt[3]{value} for a cube root. Reading the commands as instructions for the structure of an expression makes them easier to remember.

## Greek Symbols and Larger Mathematical Expressions

Technical documents often contain Greek letters and operators that would be difficult to type using only a normal keyboard. LaTeX uses commands such as \alpha, \beta, \gamma, \lambda, \pi and \theta for Greek symbols. These commands are normally written inside math mode.

For longer expressions, the commands \sum, \prod and \int represent summation, product and integration. Limits can be attached with subscripts and superscripts. The commands \lim and \infty are also common in mathematical writing. For example, a summation with a lower index and upper limit can be formed using \sum_{i=1}^{n} i.

LaTeX also provides relational symbols and arrows for equations and definitions. Writing mathematical notation with these commands keeps the symbols consistent with the rest of the document. The surrounding explanation is still important: a formula should be introduced and its variables should be explained rather than placed on the page without context.

## Matrices, Arrays and Cases

Some mathematical expressions need several entries arranged in rows and columns. The matrix environments provided by mathematical packages are useful for this. For example, pmatrix places parentheses around a matrix and bmatrix places square brackets. Entries on the same row are separated using &, and a new row is indicated with \\.

The array environment is more flexible when entries need a specified column alignment. It follows a structure similar to a table, but it is used within mathematics. For example, c, l and r can be used to indicate centred, left-aligned and right-aligned columns. The cases environment is especially useful for piecewise functions, where one expression applies under one condition and another expression applies under a different condition.

The choice between a matrix, array and cases environment depends on what the mathematical expression represents. Using the correct environment makes formulas easier to read and avoids trying to align every symbol manually with spaces.

## Making Tables in LaTeX

Tables are helpful for comparing values or arranging repeated measurements. The tabular environment builds the rows and columns. Column alignment is given at the beginning, usually with l, c or r. An ampersand separates entries across a row, and \\ ends the row. A horizontal rule can be added with \hline.

For example, a table of students' marks could use one column for names and another for marks. If the first column contains long sentences, it may be better to use a p-type column with a fixed width so the text can wrap instead of extending beyond the page. This is different from simply making every column wider.

The table environment is used when a table needs a caption and automatic numbering. LaTeX treats tables inside this environment as floats, which means they may be moved to a suitable place on a page. The \multicolumn command can join columns for a common heading, while \multirow can make one entry cover several rows when the required package is loaded. These commands are useful for more complex table layouts.

## Inserting Pictures, Graphs and Captions

A technical report frequently needs images, plots or circuit diagrams. The graphicx package supplies \includegraphics, which imports an external image into a LaTeX document. The filename should be correct and the image should be stored in a location that the compiler can find. Width or height options help keep the image within the page margins.

The figure environment groups a figure with details such as its placement, caption and label. \centering positions the image in the centre, \caption provides a description, and \label assigns an identifier that can be referred to later. The \ref command is then used to refer to the figure number. This is more reliable than typing a number manually, especially if figures are inserted or removed during editing.

Placement options include h for approximately here, t for the top, and b for the bottom. These are suggestions to LaTeX, not guarantees. Older workflows may use EPS or PostScript graphics, while a typical PDFLaTeX workflow can use PDF, PNG or JPEG files. Images should be checked after compilation because a technically successful import can still produce an unreadable or poorly sized diagram.

## Drawing with the Picture Environment

LaTeX can also draw basic figures without importing a separate image file. The picture environment works by positioning objects at coordinates. The command \setlength{\unitlength}{1mm} can define the unit used for these coordinates, and \begin{picture}(100,40) gives the drawing area a width and height in those units.

Within the picture environment, \put(x,y){object} places an item at a chosen position. A line can be made using \line, an arrow using \vector, and a circle using \circle. A rectangular box can be created with \framebox. These commands are useful for small block diagrams, labelled shapes or simple arrows between stages of a process.

There are also commands such as \multiput for repeating an object at regular intervals and \oval for a shape with rounded corners. This method requires some care because objects are placed by coordinates rather than being dragged into position. It is most suitable for relatively simple drawings where the location of each element is known.

## Using Colours without Changing the Whole Document

The xcolor package provides commands for coloured text and other coloured objects. For example, \textcolor{blue}{Important} displays the word in blue. The package also supports coloured backgrounds and custom colour definitions. Colour can be applied to text or mathematical expressions, depending on what needs emphasis.

Colour choices should still serve the document. Making every heading and sentence a different colour may draw attention away from the actual explanation. For a report, it is generally easier to read when ordinary text stays consistent and colour is used sparingly — mainly in diagrams or selected labels.

## References, Citations and Index Entries

A cross-reference connects an explanation with a numbered figure, table, section or equation. The item is given an identifier using \label, and \ref displays the corresponding number later in the document. This saves time when the order of material changes. For example, a diagram may move from Figure 2 to Figure 4 after more figures are added, but its reference can still update correctly.

Citations are related but serve a different purpose. They identify external sources such as books, articles or websites. A bibliography can be prepared using entries stored in a .bib file. The \cite command places a citation, while a bibliography style controls how references are displayed. Depending on the setup, additional compilation steps may be necessary to resolve citations.

An index is not the same thing as a bibliography. An index lists selected terms with their page numbers, which can help readers find topics in a large document. Entries can be marked using \index and processed with MakeIndex. Keeping cross-references, citations and index terms separate makes it easier to understand which tool to use for each task.

## Beamer for Slide Presentations

Beamer is a LaTeX document class made for presentations. A Beamer file starts with \documentclass{beamer}, and slides are created inside frame environments. A frame can have a title and contain normal text or an itemize list. Instead of creating a long continuous page, the document produces a set of slides.

For a simple presentation, \begin{frame}{Introduction} starts a slide titled Introduction, and \end{frame} closes it. An itemize environment inside the frame can display key points. Beamer also supports overlays, which allow information to appear in stages during a presentation. This is useful when an explanation should be revealed gradually rather than showing everything at once.

Because Beamer is part of the LaTeX workflow, mathematical expressions can be written in much the same way as in a report. It suits technical presentations where equations and consistent slide formatting are important. The uploaded LaTeX lecture introduces Beamer through its slide class and frame syntax, so these are the main commands included here.

## Doxygen for Documenting Source Code

A separate type of documentation is needed for programming projects. A code file may contain many functions and classes, and their names alone may not explain how they are meant to be used. Doxygen is an open-source tool that generates reference documentation by reading specially formatted comments in source code. It supports several languages, including C, C++, Java and Python.

In C++ code, a special comment block can be written above a function or class. The \brief tag gives a short description, \param explains a parameter, and \return describes the returned value. Other tags include \note for additional information and \see for related items. The aim is to provide useful details that are not obvious from the function name.

Suppose a function takes the radius of a circle and calculates the area. Its documentation should explain that the input is a radius, what kind of value the function returns, and any assumptions that matter. Simply writing "calculates area" may not be enough for someone using a larger software library. Doxygen can organise these descriptions into pages where related functions and classes are linked together.

## Preparing and Running Doxygen

Doxygen uses a configuration file known as Doxyfile. The command doxygen -g Doxyfile creates a starting configuration. This file controls settings such as which source folders will be read and which output types should be produced. The generated configuration may need editing before the documentation is built.

After the settings are ready, the command doxygen Doxyfile starts documentation generation. HTML output is commonly used because it can be viewed in a browser, often beginning at html/index.html. Doxygen can also generate LaTeX material, which can be processed further to make printable documentation. Other available formats include XML and RTF.

Doxygen is not limited to individual function descriptions. With suitable settings it can produce links between source elements, class relationships, call graphs and other diagrams. Graphviz can help with graphical output when enabled in the configuration. These features are especially useful in projects where several functions call each other or a class inherits from another class.

## Google Docs for Writing with Others

Google Docs is a browser-based document editor that is useful when a report has several contributors. Rather than keeping different local copies of the same file, the team can work on a shared document. Each person can be allowed to view, comment on or edit the document, depending on the permissions given by the owner.

The editor includes headings, paragraphs, lists, tables, images and links. Using proper heading styles keeps a long document more organised. Comments are useful for asking questions or pointing out a problem without changing the original sentence. Suggesting mode allows a reviewer to propose an edit that can later be accepted or rejected.

Version history is another important feature. It records earlier states of the document, allowing the team to inspect changes and restore an older version when necessary. Google Docs can also export documents in formats such as PDF and Microsoft Word. It is suited to collaborative reports and planning documents, whereas Doxygen is mainly used for documentation tied closely to source code.

## What Version Control Solves

Programming projects change repeatedly. A file may work correctly in one version but stop working after a later edit. Without version control, people sometimes create many copies named things like final, final_new or latest_fixed. This makes it hard to identify what changed and which copy should actually be used.

Git is a distributed version-control system that records changes over time. A repository contains project files together with their history. Each recorded set of changes is called a commit. Because commits have identifiers and messages, it is possible to inspect earlier states of the work and understand how the project developed.

Git works locally, so making commits does not require being connected to GitHub. This distinction matters because Git and GitHub are not the same thing. Git is the tool used for version control; GitHub is a service used to host repositories online and provide collaboration features such as pull requests and issue discussions.

## Working Directory, Staging Area and Commits

In a normal Git workflow, files are first changed in the working directory. The next step is staging, where the changes intended for the next commit are selected. A commit then records the staged changes in the local repository history. This separation allows a developer to work on several files but commit only the changes that belong together.

The command git status reports the state of a repository, including modified, staged and untracked files. The command git add README.md stages a particular file, while git add . stages relevant changes from the current directory. It is useful to check git status before committing so that unwanted files are not included.

The command git commit -m "Add project notes" creates a commit with a message. A specific message is easier to understand later than a message such as "changes". The command git log displays commit history, and git diff helps examine changes. The command git diff --staged is useful for checking the changes that have already been staged but not yet committed.

## From a Local Repository to GitHub

A new local Git repository can be started using git init. If a repository already exists online, git clone can create a local copy. A remote named origin can be connected using git remote add origin followed by the repository URL. The remote acts as a link between the local history and the online repository.

After making commits locally, git push sends them to the remote repository. The first push of a new main branch may use git push -u origin main to establish the upstream relationship. If someone else has updated the remote, those changes may need to be brought into the local copy before pushing further work.

The command git fetch downloads information about remote updates without automatically combining them with the current branch. The command git pull obtains updates and integrates them into the current branch, normally through merging or rebasing depending on the setup. Fetch is helpful when the changes should be reviewed first, while pull is often used when the intention is to bring a local branch up to date.

## Branches, Merging and Pull Requests

A branch is a separate line of development inside a Git repository. It allows work on a feature or correction without immediately changing the main branch. For example, someone can work on improving documentation in a new branch while another person continues working on the main version of the project.

Branches can be created or switched using git branch and git switch commands. After completing work and making commits, changes from one branch can be merged into another. A merge combines the work when Git can do so safely. If both branches modify the same part of a file in incompatible ways, Git may stop and report a merge conflict.

A merge conflict is not the same as losing the project. It means a decision is needed about which content to keep or how to combine the competing edits. After fixing the conflicting lines, the resolved file can be staged and the merge completed. On GitHub, a pull request is a way to propose changes from one branch, discuss them and review them before merging. This helps keep collaborative changes visible and organised.

## README Files and Repository Information

A README.md file is usually the first explanation a visitor sees when opening a repository on GitHub. It can describe what a repository contains, the main topics, how to use the files and any instructions that would help someone understand the work. The .md extension means the file uses Markdown, which supports headings and other simple text formatting.

A GitHub repository can contain a README alongside source files, diagrams or other documents. When the file is named README.md and placed at the repository's top level, GitHub generally displays it beneath the file listing. This makes the README useful as a starting point for someone who has not seen the repository before.

For a documentation-focused repository, it is often better to keep the README readable and accurate than to fill it with decorative elements. Clear section names and explanations help a reader find the material without having to open every file. Changes to the README can also be tracked through Git commits, just like changes to any other project file.
