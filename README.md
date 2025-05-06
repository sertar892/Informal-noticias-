# Informal-noticias 
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Informal - Noticias</title>
  <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js" crossorigin="anonymous"></script>
  <style>
    body { font-family: sans-serif; margin: 0; padding: 0; background: #f4f4f4; }
    header, footer { background: #222; color: white; padding: 1rem; text-align: center; }
    .container { max-width: 1200px; margin: auto; padding: 1rem; display: flex; flex-wrap: wrap; gap: 1rem; }
    .main { flex: 3; }
    .sidebar { flex: 1; background: #fff; padding: 1rem; }
    .card { background: white; padding: 1rem; margin-bottom: 1rem; border-radius: 5px; box-shadow: 0 0 5px #ccc; }
    .card img { max-width: 100%; border-radius: 5px; }
    .ads { margin: 1rem 0; text-align: center; }
    a.admin-link { color: white; text-decoration: underline; font-size: 0.9em; }
  </style>
</head>
<body>
  <header>
    <h1>Informal</h1>
    <p><a class="admin-link" href="/admin.html">Panel administrativo</a></p>
    <div class="ads">
      <!-- Publicidad de AdSense en el header -->
      <ins class="adsbygoogle"
        style="display:block"
        data-ad-client="ca-pub-xxxxxxxxxxxxxxxx"
        data-ad-slot="1234567890"
        data-ad-format="auto"
        data-full-width-responsive="true"></ins>
      <script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
    </div>
  </header>

  <div class="container">
    <div class="main" id="news-container">
      <!-- Aquí se cargarán las noticias dinámicamente -->
    </div>

    <aside class="sidebar">
      <h3>Publicidad</h3>
      <!-- Publicidad en la barra lateral -->
      <ins class="adsbygoogle"
        style="display:block"
        data-ad-client="ca-pub-xxxxxxxxxxxxxxxx"
        data-ad-slot="1234567890"
        data-ad-format="auto"
        data-full-width-responsive="true"></ins>
      <script>(adsbygoogle = window.adsbygoogle || []).push({});</script>
    </aside>
  </div>

  <footer>
    <p>&copy; 2025 Informal</p>
  </footer>

  <script>
    // Cargar noticias desde localStorage (simulación de base de datos)
    const newsContainer = document.getElementById("news-container");
    const news = JSON.parse(localStorage.getItem("informal_news")) || [];

    if(news.length === 0) {
      newsContainer.innerHTML = '<p>No hay noticias aún. Agregalas desde el panel administrativo.</p>';
    } else {
      news.reverse().forEach(noticia => {
        const card = document.createElement("div");
        card.className = "card";
        card.innerHTML = `
          <h2>${noticia.titulo}</h2>
          <img src="${noticia.imagen}" alt="Noticia">
          <p>${noticia.descripcion}</p>
        `;
        newsContainer.appendChild(card);
      });
    }
  </script>
</body>
</html>
