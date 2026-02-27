
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Housing Market Trends</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">

<style>
html { scroll-behavior: smooth; }

body {
    font-family: 'Segoe UI', sans-serif;
}

/* Navbar */
.navbar {
    background: #0d6efd;
}

.navbar .nav-link,
.navbar-brand {
    color: white !important;
    font-weight: 500;
}

/* Sections Animation */
section {
    min-height: 100vh;
    padding: 100px 0;
    opacity: 0;
    transform: translateY(40px);
    transition: 0.8s ease-in-out;
}

section.show {
    opacity: 1;
    transform: translateY(0);
}

/* Home */
.home {
    background: linear-gradient(to right, #4e73df, #1cc88a);
    color: white;
    text-align: center;
}

/* Buttons */
.btn-custom {
    padding: 10px 25px;
    border-radius: 30px;
    transition: 0.3s;
}

.btn-custom:hover {
    transform: scale(1.08);
}

/* Iframe */
iframe {
    border-radius: 15px;
    box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    transition: 0.3s;
}

iframe:hover {
    transform: scale(1.02);
}

footer {
    background: #0d6efd;
    color: white;
    text-align: center;
    padding: 15px;
}
</style>
</head>

<body>

<!-- NAVBAR -->
<nav class="navbar navbar-expand-lg fixed-top">
  <div class="container">
    <a class="navbar-brand" href="#home">🏠 Housing Trends</a>
    <div>
      <a class="nav-link d-inline" href="#home">Home</a>
      <a class="nav-link d-inline" href="#dashboard">Dashboard</a>
      <a class="nav-link d-inline" href="#story">Story</a>
    </div>
  </div>
</nav>

<!-- HOME -->
<section id="home" class="home show d-flex align-items-center">
<div class="container">
    <h1 class="display-4 fw-bold" id="title"></h1>
    <p class="lead mt-3">Interactive Tableau Dashboard & Story using Flask</p>

    <a href="#dashboard" class="btn btn-light btn-custom mt-4">
        View Dashboard ↓
    </a>
</div>
</section>

<!-- DASHBOARD -->
<section id="dashboard" class="bg-light">
<div class="container text-center">
    <h2 class="mb-4">📊 Housing Market Dashboard</h2>

    <iframe 
    src="https://public.tableau.com/views/Book1_17696952321770/Dashboard1?:showVizHome=no&:embed=true"
    width="100%" 
    height="700"
    frameborder="0"
    allowfullscreen>
    </iframe>

    <br><br>

    <a href="#home" class="btn btn-primary btn-custom">Home</a>
    <a href="#story" class="btn btn-success btn-custom">Next → Story</a>
</div>
</section>

<!-- STORY -->
<section id="story" class="bg-white">
<div class="container text-center">
    <h2 class="mb-4">📖 Housing Market Story</h2>

    <iframe 
    src="https://public.tableau.com/views/Book1_17696952321770/Story1?:showVizHome=no&:embed=true"
    width="100%" 
    height="700"
    frameborder="0"
    allowfullscreen>
    </iframe>

    <br><br>

    <a href="#home" class="btn btn-dark btn-custom">Back to Home</a>
</div>
</section>

<footer>
© 2026 Internship Project | Tableau + Flask
</footer>

<script>

/* Scroll Animation */
const sections = document.querySelectorAll("section");

window.addEventListener("scroll", () => {
    const trigger = window.innerHeight * 0.85;
    sections.forEach(sec => {
        if(sec.getBoundingClientRect().top < trigger){
            sec.classList.add("show");
        }
    });
});

/* Typewriter Effect */
const text = "Visualizing Housing Market Trends";
let i = 0;
function typing(){
    if(i < text.length){
        document.getElementById("title").innerHTML += text.charAt(i);
        i++;
        setTimeout(typing, 50);
    }
}
typing();

</script>

</body>
</html>
