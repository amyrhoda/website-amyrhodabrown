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
    <h3 class="l2l">5. Useful Packages and Settings</h3>
    <p class="pubdate">Originally posted: June 4, 2012</p>

    <p>
      This post rounds up some of the packages and settings I haven't talked
      about yet.
      </p>
    <p>
      (To tell the truth LaTeX isn't meant to do this kind of custom
      typesetting; it was created to do the work of laying out a document for
      you so you could concentrate on the content. All this rearranging and
      customising and fiddling with layout is beside the point, which is why
      you have to include packages to design each different aspect of your
      document.)
    </p>
    <p>
The <code>epstopdf</code> package converts EPS images to PDF when you run LaTeX. We used this more in the first book; for some reason the authors for the second book submitted mostly PNG and PDF images, not EPSs.
    </p>
    <div class="code">\usepackage{epstopdf}</div>
    <p>
      I needed a package which would display URLs nicely, break them at the ends of lines properly, and ideally have them be clickable in the final PDF.
    </p>
    <div class="code">
    \usepackage[hyphens]{url} % this package doesn't make proper clickable<br />
    % links, but <br />
    % \usepackage{hyperref} % this package breaks the build.
    </div>
    <p> 
      I tried both the <code>url</code> and the <code>hyperref</code> packages, and while the <code>hyperref</code> package promised to do what I wanted, it stopped the book from compiling properly. The <code>url</code> package did everything I wanted except make clickable links, so I left it in and commented out the other, thinking I would come back and figure it out later. Ha.
      </p>
      <p>
        The <code>microtype</code> package provides the ability to
        <em>micro</em>manage your <em>typ</em>ography. When invoked without any
        options it does some nice things, like protrude punctuation over the
        edge of the right margin to make the margin appear smoother. Basically
        it makes your book look more professional with very little effort. It
        also has a ton of options if you want to micromanage even more.
      </p>
      <div class="code">\usepackage{microtype}</div>
      <p>
        The <code>amssymb</code> package allows use of some math symbols.
      </p>
      <div class="code">\usepackage{amssymb}</div>
      <p>
        The <code>sectsty</code> package allowed me to change the font of the section headers.
      </p>
      <div class="code">\usepackage{sectsty}</div>
      <p>
        The <code>mathtools</code> package allowed one of our authors to display a matrix. This is one of several packages which were only used in one place in the book.
      </p>
      <div class="code">\usepackage{mathtools} % for bmatrix in matplotlib</div>
      <p>
        <code>enumitem</code> is the package that allowed me to set all the spacing options in our custom list environments.
      </p>

      <div class="code">\usepackage{enumitem}  % to manage spacing in and around lists</div>
      <p>
The <code>multicol</code> package is another we only used once; we thank a long list of reviewers in the introduction, and I wanted to format the list without using a table. Using a table would mean I'd have to decide where to break the columns (and possibly change it every time we added a name), whereas with <code>multicol</code> LaTeX does the work of flowing the names evenly into three columns.
      </p>
      <div class="code">\usepackage{multicol} % to break the list of reviewers into columns</div>
      <p>
        Then I just called it like this:
      </p>
      <div class="code">
        \begin{multicols}{3}<br />
        list \\<br />
        of \\<br />
        names...<br />
        \end{multicols}
      </div>
      <p>
        You probably know that widows and orphans are single lines separated
        over a page break from the rest of their paragraph. They make text
        harder to read, so LaTeX will get rid of them for you if you set a high
        enough penalty.
      </p>
      <div class="code">
        % introduce penalty for widows and orphans (can increase to 10 000, although<br />
        % not recommended)<br />
        % upped the widow/orphan penalty to 600 from 300; seems to have removed<br />
        % all widows and orphans <br />
        \widowpenalty=600<br />
        \clubpenalty=600</div>
      <p>
        LaTeX does hyphenation for you, and it generally does a pretty good job, but sometimes you have to tell it about unusual words. The <code>hyphenate</code> command takes a list of words with accepted hyphenation. I ended up only passing it one word.
      </p>
      <div class="code">% list of hard-to-hyphenate words with correct possible hyphenation-points<br />
\hyphenation{Free-RTOS}</div>
      <p>
        By default, LaTeX will try and make all your pages the length that you set using the <code>geometry</code> setting. If a page has images, tables, headings or paragraph breaks which make it shorter than that page length, LaTeX will pad the page by adding whitespace between elements. We thought that looked sillier than having pages be different lengths, so we used the <code>raggedbottom</code> command.
        </p>
<div class="code">\raggedbottom</div>
        <p>
          Next time I will talk about the LaTeX which actually generates the book, and about some of the resources I used to find out all these tricks myself.
        </p>

    <p class="article-nav">
    Previous: <a href="0601-latex-custom-commands-and-environments.html">Custom Commands and Environments</a> |
    <a href="/articles.html">Articles</a> | 
    Next: <a href="0607-latex-pulling-it-all-together.html">Pulling It All Together</a>.
   </p>
  </section>

  {% include footer.html %}

</body>
</html>
