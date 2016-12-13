---
layout: post
title: "[LaTeX] Reducing the space below the title"
subtitle: "tips and tricks"
date: 2016-09-22 17:00:00
comments: true
categories: [LaTeX, ACM, USENIX, template]
---

One of the fun parts of using LaTeX is that every details of the document can be adjusted, and what makes it more exciting is that you can define a new set of commands that can be applied to here and there of the document. But, it can be annoying sometimes, when it does not work as you have intended.

One of such frustration may come form reducing or increasing the space after or before the title of the document.

The `\title{}` command creates and decorates the text inside the brackets on the top matter of the document. Here is the MWE of the `\title{}`. `\maketitle` generates the top matter of the document.

~~~~
\documentclass{article}
\usepackage{lipsum} % for Lorem ipsum
\title{The new document}
\date{} % no date
\begin{document}
\maketitle
\lipsum[1-4]
\end{document}
~~~~

Yes, the top matter includes other information such as the date, author, subtitle, and perhaps a footnote of the title. When you are not using them, it would be unnecessary to keep such wide space unused in the document, especially when you are trying to create a compact one.

One easy step to reduce the space in between the title and the main body is to add `\vspace{}` inside the title command.

~~~~
\title{The new document\vspace{-3em}}
~~~~

In the example, the vertical space is introduced with reduce the space with height of `-3em`. The unit used in the exmple is `em` (Nominal m-width) which represents the length of 0.35cm or 10pt.

In a complex documents with beautifully decorated/designed documents, this would now work. Or, if you are working with redefined `\maketitle` command, then it also would not work in most cases. For example, if you are working with templates provided in [USENIX related sites](https://www.usenix.org/sites/default/files/usenix.sty_.txt) or one of [ACM hosted sites](http://www.sigapp.org/sac/sac2017/downloads/2017_SAC_LaTex_Template-Paper.zip), the trick described earlier does not work.


If you are looking for the solution or trick to adjust the space, here is the help.

First one works for ACM hosted sites. It changes the definition of `\maketitle` with `\etoolbox` package.
~~~~
\usepackage{etoolbox}
\makeatletter
\patchcmd{\@maketitle}
  {\advance\dimen0 by -12.75pc\relax}
  {}
  {}
  {}
% if more space needs to be reduced; change the value inside vspace as needed
\patchcmd{\@maketitle}
  {\end{center}}
  {\end{center}\vspace{-3em}}
  {}
  {}
\makeatother
~~~~

Next one works for USENIX hosted sites.
~~~~
\usepackage{etoolbox}
\makeatletter
\patchcmd{\maketitle}
	{\@maketitle}
	{\@maketitle\vspace{-2em}}% change the value as needed
	{}
	{}
\makeatother
~~~~

To make appropriate changes on other documents, you have to read the class or template style definitions for `\maketitle`.
