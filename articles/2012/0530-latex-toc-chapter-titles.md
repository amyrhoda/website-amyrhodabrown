---
layout: none
---
<html>
<head>
  {% include head.html %}
</head>

<body>
  {% include nav.html %}
  {% include banner.html %}

  <section class="content box">
    <h2 id="top">LaTeX to Lulu</h2>
    <h3 class="l2l">3. Table of Contents and Chapter Headings</h3>
    <p class="pubdate">Originally posted: May 30, 2012</p>

     <p>
       This post is about how <a href="http://www.third-bit.com">Greg
       Wilson</a> and I styled the tables of contents and the chapter titles
       for the two <a href="http://www.aosabook.org/">Architecture of Open
       Source Applications</a> books.
     </p>
     <p>
        First, you need a package which allows you to control the appearance of
        your table of contents:
      </p>
      <div class="code">\usepackage{tocloft}  % to typeset table of contents</div>
      <p>
        I changed the font for the table of contents to Heros, our sans-serif
        font.
      </p>
      <div class="code">
      % set TOC entries to sans-serif:<br />
      \renewcommand{\cftchapfont}{\sffamily}<br />
      <br />
      % set TOC page numbers to sans-serif:<br />
      \renewcommand{\cftchappagefont}{\sffamily} 
      </div>
      <p> 
        Then I wanted to change the size and layout of the title for the contents page.
      </p>
      <div class="code">
        % format title of table of contents (make sure this matches <br />
        % chapter head format as set below): <br />
        \renewcommand{\cfttoctitlefont}{\hfill\Huge\sffamily}
      </div>
      <p>
        Even though you probably want your chapter titles and your contents
        page to have roughly the same look, they are set in different places in
        LaTeX. As you can see, I made a note to myself in the comment in the above
        code snippet to make sure the table
        of contents title matches the chapter title pages. I'm looking at the
        book right now and it turns out they don't match at all: the table of
        contents header is right-justified and the chapter headers are
        left-justified; the table of contents header is set to LaTeX's
        <code>Huge</code> size and the chapter headers are merely
        <code>huge</code>. 
      </p>
      <div>
      <a class="img" 
         href="images/titlescomparison.jpg"><img src="images/titlescomparison.jpg"
         alt="Comparison between TOC title and chapter title" 
         width="590" height="132" /></a>
     </div>
     <p>
        Well, at least they're the same typeface. I
        won't make that mistake again!
      </p>

      <p>
        You can control how many levels of header you want to display in the
        table of contents, and how many of the levels should be numbered:
      </p>
      <div class="code">
     % set what level of header is shown in the TOC: <br />
     \setcounter{tocdepth}{0} <br /> 
     <br />
     % set what level of subsection are numbered: <br />
     \setcounter{secnumdepth}{1} </div>
     <p>
       In this case, we set the header level to 0 because we only wanted to
       list chapter names, not section names. (Since each chapter was
       written by a different author or team of authors, everyone was using
       sections differently and listing them wouldn't have been consistent or
       helpful.)
     </p>
     <p>
       LaTeX doesn't expect each chapter to have a different author, so we had
       to set up some custom commands:
     </p>
     <div class="code">
       \newcommand{\chapterauthor}{}<br />
       \newcommand{\chapterauthortoc}{}
     </div>
      <p>
        We created a custom chapter enviroment called <code>aosachapter</code>
        to declare the title, label and authors of each chapter. Each chapter
        starts something like this:
      </p>
      <div class="code">
        \begin{aosachapter}{Scalable Web Architecture and Distributed Systems}{s:distsys}{Kate Matsudaira}
      </div>
      <p>
        Here's the declaration for the <code>aosachapter</code> environment:
      </p>
      <div class="code"><pre>\newenvironment{aosachapter}[3]
{ \renewcommand{\chapterauthor}{#3} \chapter{#1} \label{#2}
   \addtocontents{toc}{\hspace{1cm}\textit{\textsf{by \chapterauthor}}\protect\par} } {  }</pre></div>
      <p>
        The <code>addtocontents</code> command builds the table of contents
        using, among other things, the <code>chapterauthor</code> value we
        defined. (The <code>chapter</code> and <code>label</code> settings are
        built in to LaTeX.)
      </p>
      <p>
        In Volume I we ran into a problem. Some chapters had a long list of
        authors which didn't break nicely in the table of contents or the
        chapter title pages &mdash; it would break between someone's first and
        last name, or before the last author's name so the next line would be
        too short. So we inserted LaTeX's newline command (<code>\\</code>)
        into the list of names, to force the list to break evenly.
      </p>
      <p>
        However, in the table of contents the second line didn't indent
        properly &mdash; it started flush with the left margin instead of lined
        up under the first line of names. So we created a new environment
        called <code>aosachaptertoc</code> based on <code>aosachapter</code>,
        but which took an extra parameter: a second list of
        authors with the same newlines, but with an
        <code>\hspace*{0.9cm}</code> at the beginning of the second line. We
        used <code>aosachaptertoc</code> to populate the table of contents.
      </p>
      <div class="code"><pre>\newenvironment{aosachaptertoc}[4]
{ \renewcommand{\chapterauthor}{#3}
  \renewcommand{\chapterauthortoc}{#4}
  \chapter{#1} \label{#2}
  \addtocontents{toc}{\hspace{1cm}\textit{\textsf{by \chapterauthortoc}}\protect\par} } {  }</pre></div>

      <p>
        So in the chapters with many authors, we declared the chapter with
        <code>\begin{aosachaptertoc}</code> instead of
        <code>\begin{aosachapter}</code>, like this:
      </p>
      <div class="code">\begin{aosachaptertoc}{VisTrails}{s:vistrails}{Juliana Freire, David Koop, Emanuele Santos, \\ Carlos Scheidegger, Claudio Silva, and Huy T.\ Vo}{Juliana Freire, David Koop, Emanuele Santos, \\ \hspace*{0.9cm} Carlos Scheidegger, Claudio Silva, and Huy T.\ Vo}
      </div>
      <p>
        I know, incredibly kludgy. You do what you have to do.
      </p>
      <p>
        Here's how table of contents entries ended up looking:
      </p>
      <p style="text-align:center;">
      <a class="img" href="images/toc.jpg"><img style="border:1px solid black;" 
         src="images/toc.jpg" alt="Table of contents" 
         width="590" height="146" /></a>
      </p>

      <h4>Chapter Title Pages</h4>
      <p>
        LaTeX has a perfectly sensible default for chapter title pages, but it's 
        boring and we thought our chapters deserved better.
        <a
        href="http://www.ctan.org/tex-archive/macros/latex/contrib/titlesec/"><code>titlesec</code></a>
        is the package that gives you control over the format of chapter title
        pages:
      </p>
      <div class="code">
        \usepackage{titlesec} % to format chapter title pages
      </div>
      <p>
        Here's how we defined chapter title pages in Volume II:
      </p>
      <div class="code">
      <pre>% format chapter title pages
\titleformat{\chapter}
  [display]     % shape/type of title
  {\ttfamily}   % formatting commands applied to both label and title
  {\vspace{-2cm} \hfill \large [chapter\kern0.15em\thechapter]}
  {2cm} % separation between number and chapter title
  {\huge\sffamily} % code preceding title. Last cmd can take arg, which is title
  [  % everything inside [] comes after the title
     \Large % make text that follows large
     \thispagestyle{plain} % suppress page numbers
     \chapterauthor % insert chapter author name
  ]% end of what comes after title</pre>
  </div>
      <p>
        Let's break that down. <code>titleformat</code> is a command provided by
        <code>titlesec</code>. The <code>display</code> option means I want the
        label ("Chapter N") in a different paragraph than the chapter title.
      </p>
      <p>
        The next line says I want the label and the title to be in our code
        font (<code>ttfamily</code>), but I actually override that later and
        put the title in the sans-serif font.
      </p>
      <p>
        The next line defines the label. I put in some vertical space to push
        the label down the page, and then a <code>hfill</code> which
        right-aligns the text by "filling" the horizontal space before it. Then
        I set the text size to be <code>large</code> and finally define the
        actual label: "<code>[chapter n]</code>", in square brackets, all lower
        case. (It's probably the most stylistically daring thing in the entire
        book!)
      </p>
      <p>
        I had to use the <code>kern</code> command to bring the chapter number
        a little closer to the "chapter" label, because the spacing in
        Inconsolata is very loose.
      </p>
      <p>
        The next line defines the horizontal space between the label and the
        title, and the line after it sets up the size and typeface for the
        title itself.
      </p>
      <p>
        Next there's the title, and then there's the stuff after the title: in
        our case, the author name(s). I set the text size to be
        <code>Large</code> (a little smaller than the title), make the
        <code>pagestyle</code> plain (so there's no page number on the first
        page of the chapter) and then display the <code>chapterauthor</code>,
        which you'll remember we set in the <code>aosachapter</code>
        environment.
      </p>
      <p>
        (I don't know why I set the pagestyle in the middle of all that instead
        of at the end.)
      </p>
      <p>
        Chapter titles are one of the few layout things I did differently from
        Volume I to Volume II. Here's what they looked like in Volume I:
      </p>
      <p>
        <a class="img" href="images/chaptertitlevol1.jpg"><img
        src="images/chaptertitlevol1.jpg" alt="Chapter title page for AOSA
        Volume I" width="590" height="276" /></a>
      </p>
      <p>
        I never liked how the chapter label looked. I wanted something really
        dramatic,
        like a really huge number, but LaTeX doesn't like you to set type
        really huge. So I tried to create drama in the difference between the
        type size of "Chapter" and the number, but that ended up looking
        awkward, especially since I couldn't get the kerning right for each
        chapter. I ended up throwing up my hands for Volume I, but I'm glad I
        got to revisit it for Volume II because I really like the funny little
        square-brackets-and-code-font label I came up with:
      </p>
      <p>
        <a class="img" href="images/chaptertitlevol2.jpg"><img
        src="images/chaptertitlevol2.jpg" alt="Chapter title for AOSA Volume
        II" width="590" height="295" /></a>
      </p>

    <p class="article-nav">
    Previous article: <a href="0528-latex-fonts-and-captions.html">Fonts and 
      Captions</a> |
    <a href="/articles.html">Articles</a> | 
    Next article: <a href="0601-latex-custom-commands-and-environments.html">Custom Commands and Environments</a>
   </p>
  </section>

  {% include footer.html %}

</body>
</html>
