<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RTSTUDIOS Watchlist</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Poppins&display=swap" rel="stylesheet">
  <style>
    /* ------------------  BODY CARD  ------------------ */
    body {
      font-family: 'Poppins', sans-serif;
      background: radial-gradient(circle at top, #0e0e0e 20%, #1a1a1a 100%);
      color: #ffffff;
      max-width: 700px;
      margin: 30px auto;
      padding: 30px;
      border-radius: 15px;
      position: relative;
      overflow-y: auto;

      /* removed the old, static shadows … */
      /* box-shadow: 0 0 40px rgba(255, 0, 0, 0.1);          */
      /* box-shadow: 10px 20px 10px 20px #800000;            */

      /* … and replaced them with a softer inner shadow       */
      /* (the real neon edge lives in body::before below)     */
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.35);
      background-image: url('https://www.transparenttextures.com/patterns/asfalt-dark.png');
      background-repeat: repeat;
    }

    /* ===== NEON GLOW FRAME (continuous, banner-style) ===== */
    body::before {
      content: "";
      position: fixed;          /* glued to viewport */
      top: -12px;               /* pulls it slightly outside the card */
      left: -12px;
      right: -12px;
      bottom: -12px;
      border-radius: 26px;      /* match card corners + offset */
      pointer-events: none;
      z-index: 9998;            /* just below your floating banner */

      box-shadow:
        0 0 10px  #fff3bd,
        0 0 20px  #ffe98e,
        0 0 40px  #ffd700,
        0 0 80px  #ffdd00,
        inset 0 0 10px #fff3bd,
        inset 0 0 20px #ffe98e,
        inset 0 0 40px #ffd700;

      animation: flicker 3.5s infinite;
    }

    /* ------------------  HEADINGS  ------------------ */
    h2 {
      font-family: 'Bebas Neue', cursive;
      font-size: 32px;
      text-align: center;
      color: #e50914;
      letter-spacing: 2px;
      margin-bottom: 20px;
      z-index: 1;
      position: relative;
    }

    /* ------------------  INPUTS  ------------------ */
    input[type="text"] {
      border: solid;
      border-radius: 20px;
      padding: 10px;
      font-family: 'Arial Black', sans-serif;
      font-size: 16px;
      width: 65%;
      margin: 10px 0;
      background-color: #2a2a2a;
      color: #fff;
      box-shadow: 0 0 20px 5px #000;
    }

    /* --------------  BUTTONS (auto width) -------------- */
    button {
      border-radius: 20px;
      padding: 10px 18px;            /* wider side padding */
      font-family: 'Arial Black', sans-serif;
      font-size: 16px;
      width: auto;                  /* <— FITS TEXT */
      white-space: nowrap;          /* keeps long labels on one line */
      margin: 10px 0;
      background-color: maroon;
      color: #fff;
      transition: background 0.3s ease, transform 0.2s ease;
      box-shadow: 0 0 10px rgba(229, 9, 20, 0.4);
      cursor: pointer;
    }

    button:hover {
      background-color: #ff3333;
      transform: scale(1.05);
    }

    /* ------------------  LIST  ------------------ */
    ul {
      list-style-type: none;
      padding: 0;
      z-index: 1;
      position: relative;
    }

    li {
      margin: 12px 0;
      background-color: rgba(40, 40, 40, 0.85);
      padding: 12px;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      box-shadow: 0 0 15px rgba(229, 9, 20, 0.2);
      transition: transform 0.2s ease;
    }

    li:hover { transform: scale(1.01); }
    li span  { flex-grow: 1; margin-left: 10px; }

    /* ------------------  FLOATING WATERMARK  ------------------ */
    .floating-text {
      position: fixed;
      z-index: 0;
      font-size: 30px;
      font-family: 'Bebas Neue', cursive;
      color: rgba(255, 255, 255, 0.05);
      animation: moveRT 30s linear infinite;
      pointer-events: none;
      font-weight: 200;
      text-align: center;
      text-shadow:
        2px 2px 0 rgba(255, 255, 255, 0.08),
        4px 4px 0 rgba(0, 0, 0, 0.15);
    }

    @keyframes moveRT {
      0%   { transform: translateY(-100vh) rotate(0deg); }
      100% { transform: translateY(100vh)  rotate(360deg); }
    }

    /* ------------------  RT BANNER (unchanged)  ------------------ */
    .rt-banner {
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      padding: 1.5rem 2rem;
      background: rgba(10, 10, 10, 0.85);
      border-radius: 12px;
      border: 1px solid #555;
      box-shadow: 0 0 20px rgba(255, 255, 255, 0.1);
      color: #fff;
      font-family: 'Georgia', serif;
      text-align: center;
      z-index: 9999;
      animation: lightning-in 4s ease-out, show-then-hide 10s ease forwards;
      pointer-events: none;
    }

    .rt-glow {
      font-size: 1.1rem;
      color: #f8e9b0;
      text-shadow:
        0 0 5px #fff3bd,
        0 0 10px #ffe98e,
        0 0 20px #ffd700;
      animation: flicker 3.5s infinite;
    }

    .rt-glow strong {
      display: block;
      margin-top: 0.5rem;
      font-size: 1.8rem;
      color: #fdf6c9;
      text-shadow:
        0 0 5px #fff,
        0 0 10px #ffe95e,
        0 0 25px #ffdd00,
        0 0 40px #ffe34d;
    }

    /* ------------  KEYFRAMES (re-used)  ------------ */
    @keyframes lightning-in {
      0%   { opacity: 0; transform: translateX(-50%) scale(0.8); filter: brightness(1); }
      20%  { opacity: 1; transform: translateX(-50%) scale(1);   filter: brightness(2.5); }
      40%  { filter: brightness(1); }
      60%  { filter: brightness(2); }
      80%  { filter: brightness(1.2); }
      100% { filter: brightness(1); }
    }

    @keyframes show-then-hide {
      0%, 80% { opacity: 1; }
      100%    { opacity: 0; visibility: hidden; }
    }

    /* Same flicker animation drives both the banner text and the body glow */
    @keyframes flicker {
      0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% { opacity: 1; }
      20%, 24%, 55%                           { opacity: 0.4; }
    }
  </style>
</head>
<body>

  <!-- Floating watermarks -->
  <div class="floating-text" style="top: 10%; left: 10%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 30%; left: 70%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 60%; left: 40%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 80%; left: 20%;">RTSTUDIOS</div>

  <h2>Movies/Series</h2>

  <!-- Login -->
  <input type="text" id="usernameInput" placeholder="Enter your name...">
  <button onclick="loginUser()">Login</button>
  <p id="welcomeText" style="color: black;"></p>

  <!-- Add series -->
  <input type="text" id="seriesInput" placeholder="Enter series name..." disabled>
  <button onclick="addSeries()">Add</button>

  <!-- List -->
  <ul id="seriesList"></ul>

  <!-- Banner -->
  <div class="rt-banner">
    <div class="rt-glow">Brought to you by<br><strong>RTSTUDIOS</strong></div>
  </div>

  <script>
    let currentUser = null;
    const seriesList = document.getElementById("seriesList");
    const inputBox   = document.getElementById("seriesInput");

    function loginUser() {
      const username = document.getElementById("usernameInput").value.trim();
      if (username) {
        currentUser = username;
        document.getElementById("welcomeText").textContent = `Welcome, ${username}!`;
        inputBox.disabled = false;
        loadList();
      }
    }

    function addSeries() {
      const seriesName = inputBox.value.trim();
      if (!seriesName) return;

      const li        = document.createElement("li");
      const checkbox  = document.createElement("input");
      const span      = document.createElement("span");
      const deleteBtn = document.createElement("button");

      checkbox.type = "checkbox";
      checkbox.addEventListener("change", () => {
        li.style.textDecoration = checkbox.checked ? "line-through" : "none";
        saveList();
      });

      span.textContent      = seriesName;
      deleteBtn.textContent = "Delete";
      deleteBtn.addEventListener("click", () => { li.remove(); saveList(); });

      li.append(checkbox, span, deleteBtn);
      seriesList.appendChild(li);

      inputBox.value = "";
      saveList();
    }

    function saveList() {
      if (!currentUser) return;
      const data = [...seriesList.querySelectorAll("li")].map(li => ({
        name: li.querySelector("span").textContent.trim(),
        watched: li.querySelector("input").checked
      }));
      localStorage.setItem(`watchlist_${currentUser}`, JSON.stringify(data));
    }

    function loadList() {
      seriesList.innerHTML = "";
      if (!currentUser) return;

      const saved = localStorage.getItem(`watchlist_${currentUser}`);
      if (!saved) return;

      JSON.parse(saved).forEach(item => {
        const li        = document.createElement("li");
        const checkbox  = document.createElement("input");
        const span      = document.createElement("span");
        const deleteBtn = document.createElement("button");

        checkbox.type = "checkbox";
        checkbox.checked = item.watched;
        checkbox.addEventListener("change", () => {
          li.style.textDecoration = checkbox.checked ? "line-through" : "none";
          saveList();
        });

        span.textContent      = item.name;
        deleteBtn.textContent = "Delete";
        deleteBtn.addEventListener("click", () => { li.remove(); saveList(); });

        li.append(checkbox, span, deleteBtn);
        li.style.textDecoration = item.watched ? "line-through" : "none";
        seriesList.appendChild(li);
      });
    }
  </script>
</body>
</html>
