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
    <h2 id="top">Making AOSA: The Tools we Used</h2>
    <p class="pubdate">Originally posted: June 12, 2012</p>

    <p>
    <a href="http://www.aosabook.org/"><em>The Architecture of Open Source
        Applications</em></a> books were multi-month projects involving dozens
    of people. Each book is a compilation of chapters written by different
    people or teams of people, and each chapter was reviewed by two more
    people. It took a battery of different tools and processes to keep it
    all in line. This is the Academy Awards "thank you" speech post, where I
    acknowledge all the software that made this possible.
    </p>
    <h4>Managing the People</h4>
    <p>
      The heart of the whole operation was a Google Docs spreadsheet accessed
      by Greg and I. We had an "Authors/Editors" sheet which listed each
      author, their email address, chapter name, and Subversion ID and
      password. A separate sheet listed all the reviewers with their email, the
      two chapters they reviewed, and their status (e.g., waiting for a
      chapter, review expected in <em>n</em> days, etc.)
    </p>
    <p>
      <a href="http://www.mozilla.org/thunderbird/">Thunderbird</a> was
      invaluable for figuring out where each author was in the process. 
      Thunderbird's archiving system just puts 
      every archived email in one place, the "archive" &mdash; no need to
      tag anything or save it to a particular folder. Then when you need that
      email again, you use Thunderbird's search function to search for an email
      address or text string within the subject or body of the email.
    </p>
    <p>
      I was able to search the email address of the author I was interested in,
      click "date" to sort the results by date, and immediately see the last
      conversation I had with that author. So if I searched for "Jane Doe"
      (say) and the latest email was from her saying, three weeks ago, "I
      should have my chapter ready in two weeks", I knew it was time for a
      gentle nag.
    </p>
    <p>
      <img title="thunderbird" src="images/thunderbird1.jpg" alt="Thunderbird
        mail client showing search results" width="590" height="359" />
    </p>

    <h4>Managing the Project</h4>

    <p>
      We used <a href="http://subversion.apache.org/">Subversion</a> for
      version control. Lots of people have lots of opinions about Subversion,
      but I hadn't used a version control system since CVS in university, and
      it seemed pretty okay to me. Each author had an account, but lots of
      people chose to submit their chapters by email instead. That worked fine,
      since there wasn't a whole lot of back-and-forthing with edits.
    </p>
    <p>
      I used a little app called <a
        href="http://www.hogbaysoftware.com/products/taskpaper">TaskPaper</a>
      to manage a few processes within the project. TaskPaper is a very simple
      app for creating and using checklists. For example, when we added a new
      contributor there was a long list of things to do: send them a welcome
      message, add them to Subversion, add empty placeholder files for their
      chapter to the repository, add them to the author list on the website...
      I was worried I would miss something, until I created a TaskPaper list.
    </p>
      <img title="taskpaper" src="images/taskpaper1.jpg" alt="Taskpaper showing
        list of actions for new contributor" width="590" height="221" /></a>
    <p>
      <a href="http://culturedcode.com/things/">Things</a> also helped keep the
      train on the tracks. Things is a productivity app designed to implement
      the <a href="http://www.davidco.com/about-gtd">Getting Things Done</a>
      system and I couldn't do anything without it. Well, I suppose I could but
      I would exhaust the world's supply of sticky notes.
    </p>
      <img title="things" src="images/things.jpg" alt="Things list of AOSA
        actions" width="590" height="342" /></a>
    
    <p>
      <a href="http://notational.net/">Notational Velocity</a> is another part
      of my daily keeping-it-together arsenal. It's a note-taking app which
      works with the <a href="http://simplenoteapp.com/">Simplenote</a>
      database. I used it to store information about the books (the required
      dimensions of the cover, the ISBNs), email snippets like the email I sent
      to reviewers or new contributors, and the solutions to different problems
      I had.
    </p>
    
      <img title="notVel" src="images/notvel.jpg" alt="Notational Velocity
        showing notes pertaining to AOSA" width="590" height="380" /></a>

    <p>
      Finally, the Google Docs spreadsheet had a very important role to play in
      managing the process. I created a "Chapter Status" sheet with one line
      per chapter, and used it to track where each chapter was in the process:
      first draft, first review, second draft, second review, copyediting,
      formatting, etc. Because I'm very visual and a colour junkie, I coded
      each status with a colour so I could look at the spreadsheet and
      immediately "feel" how we were doing.
    </p>
      <img title="progressSpreadsheet" src="images/progressspreadsheet.jpg"
        alt="Google spreadsheet showing progress of chapters" width="590"
        height="194" /></a>
    <p>
      I also used <a href="http://www.vim.org/">vi</a> for all the editing, <a
        href="http://flyingmeat.com/acorn/">Acorn</a> for image editing
      (including creating the covers), and, reluctantly, Adobe Acrobat Pro to
      munge the final PDF so Lulu's printers could reliably deal with it.
    </p>
    <p>
      Thank you all! I couldn't have done it without you!
    </p>

  </section>

  {% include footer.html %}

</body>
</html>
