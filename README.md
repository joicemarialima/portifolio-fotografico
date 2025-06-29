<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Portfólio Aprimorado</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
    :root {
      --bg: #f5f5f5;
      --text: #333;
      --accent: #222;
    }
    .dark {
      --bg: #222;
      --text: #eee;
      --accent: #f5f5f5;
    }
    *, *::before, *::after { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: 'Roboto', sans-serif;
      background: var(--bg);
      color: var(--text);
      scroll-behavior: smooth;
      transition: background 0.3s, color 0.3s;
    }
    nav {
      position: fixed;
      width: 100%;
      background: var(--accent);
      color: var(--bg);
      padding: 1rem;
      display: flex;
      justify-content: space-between;
      z-index: 1000;
    }
    nav a {
      color: var(--bg);
      margin: 0 0.5rem;
      text-decoration: none;
      font-weight: bold;
    }
    .theme-toggle {
      cursor: pointer;
    }
    header, footer { text-align: center; padding: 4rem 1rem; background: var(--accent); color: var(--bg); }
    main.gallery {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px,1fr));
      gap: 1rem;
      padding: 6rem 1rem 2rem;
    }
    .gallery img {
      width: 100%;
      display: block;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      cursor: pointer;
      transition: transform 0.3s;
      opacity: 0;
      object-fit: cover;
    }
    .gallery img:hover { transform: scale(1.05); }
    .loaded { opacity: 1 !important; }
    /* Lightbox */
    .lightbox {
      position: fixed; top:0;left:0;right:0;bottom:0;
      background: rgba(0,0,0,0.8);
      display: none;
      justify-content: center;
      align-items: center;
      z-index: 2000;
    }
    .lightbox img {
      max-width: 90%; max-height: 80%;
      border-radius: 8px;
    }
    .lightbox:target {
      display: flex;
    }
    .lightbox span {
      position: absolute; top:2%; right:4%;
      color: var(--bg); font-size: 2rem;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <nav>
    <div><a href="#sobre">Sobre</a><a href="#portfolio">Portfólio</a><a href="#contato">Contato</a></div>
    <div class="theme-toggle">🌓</div>
  </nav>
  <header id="sobre"><h1>Joice Maria Lima</h1><p>Portfólio Fotográfico</p></header>
  <main id="portfolio" class="gallery">
    <!-- Repita estas divs com suas imagens -->
    <a href="#img1"><img src="https://source.unsplash.com/random/400x300?sig=1" alt="Foto 1" loading="lazy"></a>
    <a href="#img2"><img src="https://source.unsplash.com/random/400x300?sig=2" alt="Foto 2" loading="lazy"></a>
    <a href="#img3"><img src="https://source.unsplash.com/random/400x300?sig=3" alt="Foto 3" loading="lazy"></a>
    <a href="#img4"><img src="https://source.unsplash.com/random/400x300?sig=4" alt="Foto 4" loading="lazy"></a>
  </main>
  <footer id="contato">
    <p>📧 joice@mail.com | <a href="#">WhatsApp</a> | <a href="#">Instagram</a></p>
    <p>&copy; 2025</p>
  </footer>

  <!-- Lightboxes -->
  <div id="img1" class="lightbox"><span onclick="location.hash=''">×</span><img src="https://source.unsplash.com/random/800x600?sig=1"></div>
  <div id="img2" class="lightbox"><span onclick="location.hash=''">×</span><img src="https://source.unsplash.com/random/800x600?sig=2"></div>
  <div id="img3" class="lightbox"><span onclick="location.hash=''">×</span><img src="https://source.unsplash.com/random/800x600?sig=3"></div>
  <div id="img4" class="lightbox"><span onclick="location.hash=''">×</span><img src="https://source.unsplash.com/random/800x600?sig=4"></div>

  <script>
    // Fade-in das imagens
    window.addEventListener('load', () => {
      document.querySelectorAll('.gallery img').forEach((img, i) => {
        img.onload = () => img.classList.add('loaded');
      });
    });
    // Alternar tema
    document.querySelector('.theme-toggle').onclick = () => {
      document.body.classList.toggle('dark');
    };
  </script>
</body>
</html>
