<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Portfolio - Brenda Torres </title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header class="site-header">
    <div class="container">
      <h1 id="profile-name">Brenda Torres </h1>
      <p class="subtitle">Frontend Developer • Designer • Problem Solver</p>
    </div>
  </header>

  <main class="container">
    <section class="contact-card">
      <h2>Contact</h2>
      <ul>
        <li><strong>:</strong> <span id="phone"> </span></li>
        <li><strong>Email:</strong> <a id="email" href="mailto:youremail@example.com">brenda.torres05@utrg.edu</a></li>
      </ul>
      <div class="actions">
        <a id="email-btn" class="button" href="mailto:youremail@example.com">Email Me</a>
        <a id="download-vcard" class="button outline" download="contact.vcf" href="#">Download vCard</a>
      </div>
    </section>

    <section class="about">
      <h2>About Me</h2>
      <p id="about">
        Hello — I'm YOUR NAME. Replace this paragraph with a short description about you.
        Example: I'm a web developer with experience building responsive websites and
        simple web apps. I enjoy working on accessible, well-crafted user interfaces
        and learning new tools and techniques.
      </p>
    </section>

    <section class="more">
      <h2>Skills & Links</h2>
      <p class="small">
        Skills: HTML • CSS • JavaScript • React (update as needed)
      </p>
      <p class="small">
        Links:
        <a href="#" id="portfolio-link">Portfolio</a> |
        <a href="#" id="linkedin-link">LinkedIn</a> |
        <a href="#" id="github-link">GitHub</a>
      </p>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container">
      <p>&copy; <span id="year"></span> YOUR NAME — Built with ❤️</p>
    </div>
  </footer>

  <script>
    // Small script to set year and create a simple vCard download
    document.getElementById('year').textContent = new Date().getFullYear();

    // Replace these values in the HTML or set them here:
    const name = "YOUR NAME";
    const phone = "YOUR PHONE";
    const email = "youremail@example.com";

    // If you prefer to set values through script, uncomment below:
    // document.getElementById('profile-name').textContent = name;
    // document.getElementById('phone').textContent = phone;
    // document.getElementById('email').textContent = email;
    // document.getElementById('email').href = 'mailto:' + email;
    // document.getElementById('email-btn').href = 'mailto:' + email;

    // vCard generation (simple)
    document.getElementById('download-vcard').addEventListener('click', function (e) {
      e.preventDefault();
      const vcf = [
        "BEGIN:VCARD",
        "VERSION:3.0",
        "FN:" + name,
        "TEL;TYPE=WORK,VOICE:" + phone,
        "EMAIL;TYPE=INTERNET:" + email,
        "END:VCARD"
      ].join("\\n");
      const blob = new Blob([vcf], { type: 'text/vcard' });
      const url = URL.createObjectURL(blob);
      this.href = url;
      // After click the browser will download the generated vCard
      setTimeout(() => URL.revokeObjectURL(url), 10000);
    });
  </script>
</body>
</html>
