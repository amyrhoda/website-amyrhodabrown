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
    <h3 class="l2l">1. Geometry, Headers and Footers</h3>

    <p class="pubdate">Originally posted: May 25, 2012</p>

     <p>
      This article is about specifying the size of the book, and setting up
      headers and footers.
    </p>
    <h4>Book Size and Margins</h4>
    <p>
      First, we used the <code>book</code> document class, which allows
      chapters and two-sided printing by default.
    </p>
    <div class="code">
      \documentclass{book}
    </div>
    <p>
      We used the <code>geometry</code> package to define the size of the book,
      and the margins.
    </p>
    <div class="code">\usepackage[includefoot]{geometry}</div>
    <p>
      The <code>includefoot</code> option tells LaTeX that the footer should
      come within the textblock (that is, the footer isn't in the bottom
      margin). There's an <code>includehead</code> option, but we didn't have a
      running header.
    </p>
    <p>
      Later in the preamble we define the size of the book:
    </p>
    <div class="code">
      % define page size and margins etc<br />
      \geometry{paperwidth=18.91cm,paperheight=24.589cm,<br />
      vmargin=1.9cm, % top and bottom margins<br />
      inner=1.9cm, % inside margin<br />
      outer=2.29cm, % outside margin<br />
      bindingoffset=0.89cm % gutter<br />
      }</div>
    <p>
      Lulu has a whole host of book sizes, but <code>geometry</code> makes this
      one of the easiest parts of the layout job. We used Lulu's Crown Quarto
      size, and I set the margins to exactly match the MS Word template that
      Lulu provides.
    </p>
    <p>
      I realized later that I didn't need to stick so closely to that template,
      but those settings kept me safely within the <a
      href="http://connect.lulu.com/t5/ISBN-Distribution/Mandatory-Requirements-for-Print-Books-with-Distribution/ta-p/33632">extended
      distribution requirements</a>, which are the requirements your book must
      meet to be distributed on Amazon.
    </p>

    <h4>Setting Up Headers and Footers</h4>
    <p>
      The <code>fancyhdr</code> package gives you control over the style of
      your footers and headers.
    </p>
    <div class="code">\usepackage{fancyhdr} % to format headers/footers</div>
    <p>
      Setting <code>pagestyle</code> to <code>fancy</code> tells LaTeX you want
      to use <code>fancyhdr</code>.
    </p>
    <div class="code">\pagestyle{fancy}</div>
    <p>
      Here's a tricky bit, and I confess some of this I don't really understand
      myself&thinsp;&mdash;&thinsp;I copied it from the Internet and hoped for
      the best.
    </p>
    <div class="code">
      %% fiddle with chaptermark so we can make it not all caps<br />
      \renewcommand{\chaptermark}[1]{\markboth{#1}{}}<br />
      \renewcommand{\sectionmark}[1]{\markright{#1}{}}</div>
    <p>
      I'm not sure why those two lines make footers not all caps, but that's
      what the Internet said and it seemed to work.
    </p>
    <p>
      Next I define the header and footer to be empty, and get rid of the line
      that LaTeX puts under the header:
    </p>
    <div class="code">
      %% next get rid of existing header and footer and header rule<br />
      \fancyhead{}<br />
      \fancyfoot{}<br />
      \renewcommand{\headrulewidth}{0pt}</div>
    </p>
    <p>
      Now that we've got a blank slate, here's where we define the footer:
    </p>
    <div class="code">
      % now make the footer the way we want it:<br />
      % page number on right side of footer for odd pages<br />
      \rfoot[]{\small{\textsf{\chapterauthor \hspace{0.25cm} \thepage}}}<br />
      <br />
      % the following looks like it doesn't do anything, but<br />
      % it seems to remind it to line up headers with the<br />
      % rest of the text:<br />
      \fancyhfoffset[EL]{0cm} <br />
      <br />
      % page number and chapter name on left side of footer for even pages<br />
      \lfoot[\small{\textsf{\thepage \hspace{0.25cm} \leftmark}}]{}</div>
    <p>
      We have the page number and chapter name on the left pages, and the
      author name and page number on the right, all in sans-serif font. Why? I
      thought it looked nice.
    </p>

    <h4>Footnotes</h4>
    <p>
      We didn't do much with footnotes&thinsp;&mdash;&thinsp;the default way
      LaTeX handles them
      worked for us. We did change one thing: LaTeX treats footnotes as a
      paragraph and indents the first line, but since many of our footnotes are
      simply URls, they are less than one line long and it looked weird to have
      them indented. So I used the <code>footmisc</code> package:
    </p>
    <div class="code">\usepackage[hang,flushmargin]{footmisc}  % To not indent footnotes</div>
    <p>
      The <code>footmisc</code> package provides an assortment of ways to style
      footnotes. The <code>hang</code> option sets the footnote flush with the
      margin rather than indenting it.
    </p>
    <p>
      The <code>flushmargin</code> option places the footnote marker; the
      documentation says it "sets the footnote marker flush with, but just
      inside the margin from, the text of the footnote". I'm not exactly sure
      what that means, but I like the way our footnotes look so I left it.
    </p>
    <p class="article-nav">
    <a href="#top">Top</a> | Next article: <a href="0528-latex-fonts-and-captions.html">Fonts and 
      Captions</a>.
   </p>
  </section>

  {% include footer.html %}
</body>
</html>
