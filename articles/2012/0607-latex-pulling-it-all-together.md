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
    <h2 id="top">LaTeX to Lulu: The Making of AOSA</h2>
    <h3 class="l2l">6. Pulling it All Together</h3>
    <p class="pubdate">Originally posted: June 7, 2012</p>

    <p>
      This article is about the LaTeX that pulls the whole book together.
    </p>
    <p>
      I think I mentioned this before: we used the <code>book</code> document
      class, which allows chapters and two-sided printing by default. That's
      the very first line in our LaTeX file:
    </p>
    <div class="code">\documentclass{book}</div>
    <p>
      Then we include all the packages and set up all the settings and custom
      environments I've been posting about for days, and then finally...
    </p>
    <div class="code">\begin{document}</div>
    <p>
      Whoo hoo!
    </p>
    <div class="code">\frontmatter</div>
    <p>
      The <code>frontmatter</code> command is defined by the <code>book</code>
      class. It affects numbering, specifically setting the page numbers to
      Roman in the front matter. By calling it here, we're saying, "This is 
      where the front matter begins, so number the pages with Roman numerals."
    </p>
    <p>
      Then we include a file called <code>frontmatter.tex</code> which defines
      the half-title page, title page, and dedication.
    </p>
      <div class="code">\include{frontmatter}</div>
    <p>
      The <code>tableofcontents</code> command tells LaTeX to (guess what!)
      generate a table of contents.
    </p>
    <div class="code">\tableofcontents</div>
    <p>
      Then we include the <code>intro</code> file, which is our introduction
      and list of contributors.
    </p>
    <div class="code">\include{intro}</div>
    <p>
      <code>mainmatter</code> tells it to switch to Arabic numerals, then we
      include all the chapters.
    </p>
    <div class="code">\mainmatter<br />
      \include{distsys}<br />
      \include{ffreleng}<br />
      \include{freertos}<br />
      ...<br />
      \include{zeromq}</div>
    </p>
    <p>
      Then we set the style of the bibliography. <code>alpha</code> means the
      labels for the bibliography entries are based on the the authors'
      initials and publication year, so an article by Donald Knuth published in
      1986 would be labelled <strong>[Knu86]</strong>.
    </p>
    <p>
      The <code>bibliography</code> command tells LaTeX which file to use for
      the bibliography.
    </p>
    <div class="code">\bibliographystyle{alpha}<br />
      \bibliography{aosa2}</div>
    <p>
      I copied this next bit from somewhere on the web because I wanted to get
      rid of the blank page after the bibliography, and honestly I'm not
      entirely sure how it works. <code>makeatletter</code> makes the
      <code>@</code> sign into a letter, for some reason. Then
      <code>@openrightfalse</code> does the no-blank-page magic, and
      <code>makeatother</code> returns <code>@</code> to its rightful status as
      whatever-it-is.
    </p>
    <div class="code">
      %% This prevents LaTeX from adding a blank page after the bibliography<br />
      \makeatletter<br />
      \@openrightfalse<br />
      \makeatother</div>

    <p>
      <code>backmatter</code> ends the main matter, and thus the page
      numbering. Then we include the colophon, and that's the end!
    </p>
    <div class="code">
      \backmatter<br />
      <br />
      \include{colophon}<br />
      <br />
      \end{document}</div>

<h4>Resources</h4>
    </p>
    <p>
      I literally could not have made this book without the power of Google.
      (Well, I suppose there are books, but then you wouldn't be reading
      <em>our</em> book until 2015.) Some of the sites which popped up again
      and again were <a href="http://en.wikibooks.org/wiki/LaTeX">the LaTeX
        WikiBook</a>, <a href="http://stackoverflow.com/">Stack Overflow</a>,
      <a href="http://tex.stackexchange.com/">StackExchange's TeX site</a>, and
      the <a href="http://www.latex-community.org">LaTeX Community</a>. In
      particular, <a
        href="http://tex.stackexchange.com/users/213/stefan-kottwitz">Stefan
        Kottwitz</a> furnished so many helpful answers he practically earned a
      place in the acknowledgments.
    </p>

    <p class="article-nav">
    Previous: <a href="0604-latex-useful-packages-and-settings.html">Useful Packages and Settings</a> |
    <a href="/articles.html">Articles</a> 
   </p>
  </section>

  {% include footer.html %}

</body>
</html>
