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

  <section class="box contact">
    <h2>Contact Me</h2>

    <script language="JavaScript">
      var username = "amy";
      var hostname = "amyrhodabrown.com";
      var emailicon = "img/email.png";
      document.write("<a href='" + "mail" + "to:" + username + "@" + hostname + "'><img src='" + emailicon + "' alt='Email'></a>");
      document.write("<a href='" + "mail" + "to:" + username + "@" + hostname + "'>" + username + "@" + hostname + "</a>");
    </script>
    <br clear="all" />

    <!-- 5 Jul 2016 Removing Twitter (for now?)
    <a href="https://twitter.com/amyrbrown"><img src="img/twitter.png" alt="Twitter"></a>
    <a href="https://twitter.com/amyrbrown">@amyrbrown</a><br clear="all" />
    -->

    <a href="http://ca.linkedin.com/in/amyrbrown/"><img src="img/linkedin.png" alt="LinkedIn"></a>
    <a href="http://ca.linkedin.com/in/amyrbrown/">LinkedIn</a>
  </section>

  <!-- No included footer in this file because the content of the page is the
       same as the content of the footer. -->
</body>
</html>
