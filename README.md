<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Arcade Hub</title>
  <style>
    :root {
      --bg-color: #0f172a;
      --card-bg: #1e293b;
      --text-color: #f8fafc;
      --accent-color: #38bdf8;
      --accent-hover: #0284c7;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      background-color: var(--bg-color);
      color: var(--text-color);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    header {
      background-color: var(--card-bg);
      padding: 1.5rem 2rem;
      text-align: center;
      border-bottom: 2px solid #334155;
    }

    header h1 {
      color: var(--accent-color);
      font-size: 2rem;
      margin-bottom: 0.5rem;
    }

    main {
      flex: 1;
      max-width: 1100px;
      width: 100%;
      margin: 2rem auto;
      padding: 0 1rem;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 1.5rem;
    }

    .card {
      background-color: var(--card-bg);
      border-radius: 8px;
      padding: 1.5rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      border: 1px solid #334155;
      transition: transform 0.2s, border-color 0.2s;
    }

    .card:hover {
      transform: translateY(-4px);
      border-color: var(--accent-color);
    }

    .card h2 {
      margin-bottom: 0.5rem;
      font-size: 1.25rem;
    }

    .card p {
      color: #94a3b8;
      margin-bottom: 1rem;
      font-size: 0.95rem;
    }

    .card button {
      background-color: var(--accent-color);
      color: #0f172a;
      border: none;
      padding: 0.6rem 1rem;
      border-radius: 4px;
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.2s;
    }

    .card button:hover {
      background-color: var(--accent-hover);
      color: #ffffff;
    }

    .screen-container {
      margin-top: 2rem;
      background-color: var(--card-bg);
      border-radius: 8px;
      padding: 1rem;
      border: 1px solid #334155;
      display: none;
      text-align: center;
    }

    .screen-container iframe {
      width: 100%;
      height: 600px;
      border: none;
      border-radius: 4px;
      background: #000;
    }

    footer {
      text-align: center;
      padding: 1.5rem;
      color: #64748b;
      font-size: 0.875rem;
      border-top: 1px solid #1e293b;
    }
  </style>
</head>
<body>

  <header>
    <h1>Web Arcade Hub</h1>
    <p>Select a game below to launch and play directly in your browser.</p>
  </header>

  <main>
    <div class="grid">
      <!-- Game Card 1 -->
      <div class="card">
        <div>
          <h2>2048</h2>
          <p>Join the numbers and get to the 2048 tile in this classic puzzle game.</p>
        </div>
        <button onclick="loadGame('https://play2048.co/')">Play Game</button>
      </div>

      <!-- Game Card 2 -->
      <div class="card">
        <div>
          <h2>Hextris</h2>
          <p>A fast-paced puzzle game inspired by Tetris played on a hexagon grid.</p>
        </div>
        <button onclick="loadGame('https://hextris.io/')">Play Game</button>
      </div>

      <!-- Game Card 3 -->
      <div class="card">
        <div>
          <h2>Pac-Man (Web)</h2>
          <p>Navigate the maze, eat dots, and avoid ghosts in this arcade classic.</p>
        </div>
        <button onclick="loadGame('https://pacman.place/')">Play Game</button>
      </div>
    </div>

    <!-- Active Game Screen Container -->
    <div id="game-screen" class="screen-container">
      <h2 id="now-playing" style="margin-bottom: 1rem;">Playing Game</h2>
      <iframe id="game-frame" src="about:blank"></iframe>
    </div>
  </main>

  <footer>
    <p>Hosted on GitHub Pages</p>
  </footer>

  <script>
    function loadGame(url) {
      const frame = document.getElementById('game-frame');
      const screen = document.getElementById('game-screen');
      
      frame.src = url;
      screen.style.display = 'block';
      screen.scrollIntoView({ behavior: 'smooth' });
    }
  </script>

</body>
</html>
