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
    <h2 id="top">Working with Lulu</h2>
    <p class="pubdate">Originally posted: June 21, 2012</p>

    <p>
      Lots of people have asked us how it is working with <a
        href="http://www.lulu.com/">Lulu</a>. I've published three books with
      Lulu now, and the fact that I'll continue to use them and recommend them
      speaks for itself. However, that path is not without potholes.
    </p>
    <h3>The Lows</h3>
    <h4>Technical Difficulties</h4>
    <p>
      We had a couple of technical problems with Lulu, both of which were more
      problems with the arcanery of the printing process than with Lulu per se.
    </p>
    <p>
      The first problem was with a "corrupt font table" in the PDF. I learned
      about the problem when I got an email from Lulu Support out of the blue
      telling me that the <em>AOSA I</em> had "errors that are preventing the
      project from printing", and that the status of the book had been changed
      to "Available Only to Me". (Note that I got the email some time after I
      uploaded the book and made it public &mdash; I wasn't notified immediately on
      upload.)
    </p>
    <p>
      I contacted tech support and they were kind enough to send me the PDF
      inspection report ("We don't typically provide this much information (as
      it's somewhat technical), but based on the subject of your project, we
      hope that it is useful for you") and it turned out the problem was with
      the Microsoft Cambria font. It was news to me that that was even in the
      book, because I certainly didn't use it, but it turns out that any font
      used in an EPS or PDF diagram in turn becomes part of the book's PDF.
      Once I changed the diagram, the problem went away.
    </p>
    <p>

      The second technical issue wasn't so easy to resolve. The first proof of
      AOSA II had a few blank pages, so I contacted Lulu Support and they said
      it was a problem with unsupported transparencies. Their suggested fix was
      to save the file as PostScript and then redistill it with Adobe
      Distiller, which is part of Acrobat.
    </p>
    <p>

      I ignored that and tried to remove all the transparencies from all the
      diagrams, but there were so many files from so many sources that it was
      extremely hard, if not impossible. (And I didn't even know if it would
      fix the problem.) I looked around for tools to strip transparency from
      PDFs, but none of them worked. There's even a built-in PDF flattening
      capability on OS X, but it didn't work either.
    </p>
    <p>

      The "fix" was to buy Adobe Acrobat, which I did, and once I followed
      Lulu's suggested workflow the file was accepted.
    </p>
    <p>

      Again, neither of those problems were with Lulu per se, but with the
      limitations of the printing process (and Adobe's stranglehold on the
      industry). Lulu uses different printers all over the world, so to ensure
      a consistent result they make sure that source files are as solid as
      possible.
    </p>
    
<h4>Usability Issues</h4>
   
    <p>
      The Lulu website has a few usability problems which drive me nuts. For
      example, when you're creating a "Marketing Image" for a PDF, the upload
      dialog says "Your picture should be about 536 pixels wide and 697 pixels
      tall", but when you upload a picture that's a little smaller the error
      message says the image should be <em>at least</em> 536 pixels wide and
      697 pixels tall.
    </p>
    <p>
      Little things like that, that more usability testing would uncover.
    </p>
    <p>

      Another thing: a few months ago the PDF for <em>AOSA I</em> disappeared
      off the Lulu website. It turned out they changed the PDF distribution
      system, so that instead of selling your PDF as an addendum to an existing
      project, you have to create a new project to distribute it. They said
      they emailed everyone about it, and maybe they did, but it must have gone
      into my spam folder because I don't tend to ignore email.
    </p>
    <p>

      Lulu doesn't send books to P.O. boxes, which isn't a problem for most
      people, but for the rest of us it's a <em>big</em> problem.
    </p>
    <p>
      The worst thing about Lulu, though, is with the extended distribution
      system. When you choose extended distribution for your book (that is, for
      it to be sold through Amazon.com) it has to conform to a long list of <a
        href="http://connect.lulu.com/t5/ISBN-Distribution/Mandatory-Requirements-for-Print-Books-with-Distribution/ta-p/33632">format
        requirements</a>. Which is fine, whatever, I'm sure it has something to
      do with self-published books looking/acting like "real books". However,
      in order to move through the process of getting your book distributed,
      you have to order a copy of the book and then declare that it meets the
      requirements (presumably once you have the printed book in your grubby
      hands).
    </p>
    <p>

      Which is all very well, except that once you have your book in the
      extended distribution process, it's all-too-easy to click on something
      which sends the book right back to the beginning of the process. If you
      edit the author name (even if you don't change it but just open the edit
      page) or I don't even know what else, the system demands that you buy a
      new copy of your book and reconfirm that it meets the requirements.
      <em>Even if you haven't uploaded a new file and nothing has changed!</em>
      It doesn't make sense, and I have started to develop a phobia about
      clicking anywhere near a project which is in extended distribution, for
      fear of waking the dragon.
    </p>

    <h3>The Highs</h3>
   
    <p>
      Those are the things that bother me about Lulu. These are the things that
      redeem them:
    </p>
    <p>
      I love their tech support. Every time I've had a problem
      I have had the full, patient and committed assistance of their tech
      support department to help me resolve it. They send me reports, they
      explain their printing process, they refund orders when there's a
      printing glitch. The tech support isn't incredibly fast, but once a
      particular member of staff is assigned to your problem, that is who works
      with you until it's resolved, so you don't have to explain things over
      and over.
    </p>
    <p>

      Honestly, even with the usability problems I mentioned above, the website
      is pretty easy to use. There are wizards to walk you through things and
      the explanatory text keeps it unstressful most of the time. It's not a
      flawless experience, like <a
        href="http://www.freshbooks.com/">Freshbooks</a>, but it's pretty good.
    </p>
    <p>
      And I love the final product. I've been delighted with
      the quality of the books: the paper is thick and bright, the colours on
      the cover are true. There is nothing more satisfying than holding your
      beautiful, finished book in your hand.
    </p>

  </section>

  {% include footer.html %}

</body>
</html>
