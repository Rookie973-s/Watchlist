<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>RTSTUDIOS Watchlist</title>
  <style>
    body {
      font-family: sans-serif;
      background-color: #121212;
      color: #ffffff;
      max-width: 600px;
      margin: 30px auto;
      padding: 20px;
      border-radius: 15px;
      background: linear-gradient(145deg, #1e1e1e, #1c1c1c);
      box-shadow: 0 0 10px rgba(0,0,0,0.6);
    }

    input[type="text"] {
      padding: 10px;
      font-size: 16px;
      width: 70%;
      margin-bottom: 10px;
    }

    button {
      padding: 10px;
      font-size: 16px;
      cursor: pointer;
      background-color: #03dac6;
      border: none;
      color: #000;
      border-radius: 5px;
      margin-left: 5px;
    }

    ul {
      list-style-type: none;
      padding: 0;
    }

    li {
      margin: 10px 0;
      background-color: #1e1e1e;
      padding: 10px;
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    li span {
      flex-grow: 1;
      margin-left: 10px;
    }

    h2 {
      text-align: center;
    }

    #welcomeText {
      font-style: italic;
      margin-bottom: 10px;
    }

    /* RTSTUDIOS Banner Styles */
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
      animation: lightning-in 1s ease-out, show-then-hide 6s ease forwards;
      pointer-events: none;
    }

    .rt-glow {
      font-size: 1.1rem;
      color: #f8e9b0;
      text-shadow:
        0 0 5px #fff3bd,
        0 0 10px #ffe98e,
        0 0 20px #ffd700;
      animation: flicker 1.5s infinite;
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

    @keyframes lightning-in {
      0% { opacity: 0; transform: translateX(-50%) scale(0.8); filter: brightness(1); }
      20% { opacity: 1; transform: translateX(-50%) scale(1); filter: brightness(2.5); }
      40% { filter: brightness(1); }
      60% { filter: brightness(2); }
      80% { filter: brightness(1.2); }
      100% { filter: brightness(1); }
    }

    @keyframes show-then-hide {
      0%, 80% { opacity: 1; }
      100% { opacity: 0; visibility: hidden; }
    }

    @keyframes flicker {
      0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
        opacity: 1;
        text-shadow:
          0 0 5px #fff3bd,
          0 0 10px #ffe98e,
          0 0 20px #ffd700;
      }
      20%, 24%, 55% {
        opacity: 0.4;
        text-shadow: none;
      }
    }
  </style>
</head>
<body>

  <!-- Login area -->
  <input type="text" id="usernameInput" placeholder="Enter your name...">
  <button onclick="loginUser()">Login</button>
  <p id="welcomeText"></p>

  <!-- Series input area -->
  <input type="text" id="seriesInput" placeholder="Enter series name..." disabled>
  <button onclick="addSeries()">Add</button>

  <!-- List display -->
  <ul id="seriesList"></ul>

  <!-- Glowing RTSTUDIOS Banner -->
  <div class="rt-banner">
    <div class="rt-glow">Brought to you by<br><strong>RTSTUDIOS</strong></div>
  </div>

  <script>
    // GLOBAL VARIABLES
    let currentUser = null;
    const seriesList = document.getElementById("seriesList");
    const inputBox = document.getElementById("seriesInput");

    // Function to log in user
    function loginUser() {
      const username = document.getElementById("usernameInput").value.trim();
      if (username !== "") {
        currentUser = username;
        document.getElementById("welcomeText").textContent = `Welcome, ${username}!`;
        inputBox.disabled = false;
        loadList();
      }
    }

    // Function to add a new series
    function addSeries() {
      const seriesName = inputBox.value.trim();
      if (seriesName !== "") {
        const listItem = document.createElement("li");

        const checkbox = document.createElement("input");
        checkbox.type = "checkbox";
        checkbox.addEventListener("change", () => {
          listItem.style.textDecoration = checkbox.checked ? "line-through" : "none";
          saveList();
        });

        const span = document.createElement("span");
        span.textContent = seriesName;

        const deleteBtn = document.createElement("button");
        deleteBtn.textContent = "Delete";
        deleteBtn.addEventListener("click", () => {
          listItem.remove();
          saveList();
        });

        listItem.appendChild(checkbox);
        listItem.appendChild(span);
        listItem.appendChild(deleteBtn);
        seriesList.appendChild(listItem);

        inputBox.value = "";
        saveList();
      }
    }

    // Save user's watchlist to localStorage
    function saveList() {
      if (!currentUser) return;

      const allItems = [];
      const listElements = seriesList.querySelectorAll("li");

      listElements.forEach((li) => {
        const checkbox = li.querySelector("input[type='checkbox']");
        const seriesName = li.querySelector("span").textContent.trim();
        allItems.push({
          name: seriesName,
          watched: checkbox.checked
        });
      });

      localStorage.setItem(`watchlist_${currentUser}`, JSON.stringify(allItems));
    }

    // Load watchlist for current user
    function loadList() {
      seriesList.innerHTML = "";

      if (!currentUser) return;

      const savedList = localStorage.getItem(`watchlist_${currentUser}`);
      if (savedList) {
        const items = JSON.parse(savedList);

        items.forEach((item) => {
          const listItem = document.createElement("li");

          const checkbox = document.createElement("input");
          checkbox.type = "checkbox";
          checkbox.checked = item.watched;
          checkbox.addEventListener("change", () => {
            listItem.style.textDecoration = checkbox.checked ? "line-through" : "none";
            saveList();
          });

          const span = document.createElement("span");
          span.textContent = item.name;

          const deleteBtn = document.createElement("button");
          deleteBtn.textContent = "Delete";
          deleteBtn.addEventListener("click", () => {
            listItem.remove();
            saveList();
          });

          listItem.appendChild(checkbox);
          listItem.appendChild(span);
          listItem.appendChild(deleteBtn);
          listItem.style.textDecoration = item.watched ? "line-through" : "none";

          seriesList.appendChild(listItem);
        });
      }
    }
  </script>
</body>
</html>
