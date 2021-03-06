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
    <h2 id="top">Latex to Lulu: The Making of AOSA</h2>
    <h3 class="l2l">2. Fonts and Captions</h3>

    <p class="pubdate">Originally posted: May 28, 2012</p>

      <p>
      This article is about specifying fonts and captions in LaTeX.
      </p>

      <h4>Fonts</h4>
      <p>
      Here are our fonts. The <code>fontenc</code> package allows you to
      specify the font encoding, and the <code>T1</code> option specifies the
      <a href="http://en.wikipedia.org/wiki/Cork_encoding">T1 encoding</a>,
      which lets you use fonts with more characters.
      </p>
      <div class="code">
      <pre>
\usepackage[T1]{fontenc}
\usepackage{tgtermes}    % body font
\usepackage{inconsolata} % fixed width font
\usepackage{tgheros}     % sans-serif font</pre>
      </div>
      <p>
        I used the <a href="http://www.tug.dk/FontCatalogue/">LaTeX Font
        Catalogue</a> to find the fonts for the book. One of our requirements
        was that the fonts be open source, or at least free, so that eliminated
        the vast majority of the fonts available from consideration.
      </p>
      <p>
        The body font is <a
        href="http://www.tug.dk/FontCatalogue/tgtermes/">TeX Gyre Termes</a>
        and the sans-serif, which I used for headings and the footer, is <a
        href="http://www.tug.dk/FontCatalogue/tgheros/">TeX Gyre Heros</a>. The
        code font is <a
        href="http://levien.com/type/myfonts/inconsolata.html">Inconsolata</a>.
      </p>
      <p>
        I've read a lot about choosing typefaces, and I know more than I used
        to, but I confess I still mostly do it by trial and error and what
        "looks good". There's a chance that I'll look at these books in five
        years and wonder what on earth made me choose these typefaces, but for
        now I'm very happy with the way they look.
      </p>

      <h4>Captions and Other Text Tweaks</h4>
      <p>
        We made a few changes to LaTeX's default behaviour in terms of
        typefaces.
      </p>
      <p>
        The default in LaTeX is for caption copy to be the same size as the
        body text. We used the <code>caption</code> package to make it smaller,
        which helps differentiate long captions from the surrounding text.
      </p>
      <div class="code">\usepackage[small]{caption}  % make caption text size smaller</div>
      <p>
        I also found there was too much space above and below captions by
        default, so I used <code>setlength</code> to tighten it up a little:
      </p>
      <p>
      <div class="code">
        %% Make the space above and below captions smaller<br />
\setlength{\abovecaptionskip}{1.2ex}<br />
\setlength{\belowcaptionskip}{-1.5ex}</div>
      </p>
      <p>
      I made section headers sans-serif because I wanted them to stand out, and
      for our sans-serif font to do a little more work.
      </p>
      <div class="code">% set all section headers to be sans-serif<br>
      \allsectionsfont{\normalfont\sffamily}</div>
      <p>
        The monospaced font we used, <a
          href="http://levien.com/type/myfonts/inconsolata.html">Inconsolata</a>,
        is a little larger than Termes at the same point size, so I set it 
        smaller to look more graceful.
      </p>
      <div class="code">
        % make all verbatim (code blocks) text smaller<br />
        \let\oldverbatim\verbatim<br />
        \renewcommand\verbatim{\small\oldverbatim}</div>

      <p class="article-nav">
      Previous article: <a href="120528-latex-geometry.html">Geometry, Headers and Footers</a> |
      <a href="#top">Top</a> | 
      Next article: <a href="012/0530-latex-toc-chapter-titles.html">Table of Contents and Chapter Title Pages</a>
     </p>
    </section>

  {% include footer.html %}
  </body>
  </html>
