<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ananya Shree - CV</title>

  <!-- jsPDF library for PDF generation -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>

  <style>
    body {
      font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
      background-color: #f5f7fa;
      color: #333;
      margin: 0;
      padding: 0;
    }
    .container {
      width: 80%;
      max-width: 900px;
      margin: 50px auto;
      background: #fff;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }
    h1 {
      font-size: 28px;
      margin-bottom: 5px;
    }
    h2 {
      font-size: 20px;
      color: #555;
      border-bottom: 2px solid #ddd;
      padding-bottom: 5px;
    }
    p {
      margin: 5px 0;
    }
    .links a {
      text-decoration: none;
      color: #0077b5;
      font-weight: 500;
      margin-right: 10px;
    }
    .section {
      margin-top: 20px;
    }
    ul {
      list-style-type: square;
      padding-left: 20px;
    }
    #download-btn {
      display: block;
      margin: 0 auto 20px;
      background: #0077b5;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 8px;
      cursor: pointer;
      font-size: 16px;
    }
    #download-btn:hover {
      background: #005f91;
    }
  </style>
</head>

<body>

  <button id="download-btn">⬇️ Download as PDF</button>

  <div class="container" id="cv-content">
    <header>
      <h1>Ananya Shree</h1>
      <p><strong>Computer Science Engineering Student</strong></p>
      <p>Email: ananyashree2633@gmail.com </p>
      <div class="links">
        <a href="https://www.linkedin.com/in/ananya-shree-8b8020314/" target="_blank">LinkedIn</a>
        <a href="https://github.com/ananyashree2633" target="_blank">GitHub</a>
      </div>
    </header>

    <div class="section">
      <h2>Education</h2>
      <p><strong>Amity University, Patna</strong></p>
      <p>B.Tech in Computer Science Engineering — 2024–2028</p>
    </div>

    <div class="section">
      <h2>Skills</h2>
      <ul>
        <li>Web Development (HTML, CSS, JavaScript, PHP)</li>
        <li>Python Programming</li>
      </ul>
    </div>

    <div class="section">
      <h2>Projects</h2>
      <ul>
        <li><strong>Event Registration System</strong> — Built with PHP and MySQL</li>
        <li><strong>Portfolio Website</strong> — Personal static site using HTML & CSS</li>
      </ul>
    </div>

    <div class="section">
      <h2>Certifications</h2>
      <ul>
        <li>100 Days of Code: Python Bootcamp by Angela Yu (Udemy)</li>
        <li>Many more personal projects.</li>
      </ul>
    </div>

    <div class="section">
      <h2>About Me</h2>
      <p>Enthusiastic engineering student passionate about coding, web technologies, and problem-solving. Aiming to grow as a software engineer and contribute to impactful projects.</p>
    </div>
  </div>

  <script>
    document.getElementById("download-btn").addEventListener("click", async () => {
      const { jsPDF } = window.jspdf;
      const doc = new jsPDF("p", "pt", "a4");
      const cv = document.getElementById("cv-content");

      // Convert HTML to canvas then PDF
      await doc.html(cv, {
        callback: function (pdf) {
          pdf.save("Ananya_Shree_CV.pdf");
        },
        margin: [20, 20, 20, 20],
        x: 0,
        y: 0,
        html2canvas: { scale: 0.6 }
      });
    });
  </script>

</body>
</html>
