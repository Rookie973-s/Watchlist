<html lang="en">
<head>
  <!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-7P8G6MP4Q6"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-7P8G6MP4Q6');
</script>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RTSTUDIOS Watchlist</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Poppins&display=swap" rel="stylesheet">
  <style>
    /* ▸▸ your existing styles stay the same … ◂◂ */
    /* (they’re collapsed here for brevity)                                      */
    /* ------------------------------------------------------------------------ */
    body{font-family:'Poppins',sans-serif;background:radial-gradient(circle at top,#0e0e0e 20%,#1a1a1a 100%);color:#fff;max-width:700px;margin:30px auto;padding:30px;border-radius:15px;position:relative;overflow-y:auto;box-shadow:0 0 15px rgba(0,0,0,.35);background-image:url('https://www.transparenttextures.com/patterns/asfalt-dark.png');background-repeat:repeat}
    body::before{content:"";position:absolute;inset:-10px;border-radius:inherit;pointer-events:none;z-index:9998;box-shadow:0 0 10px #c08081,0 0 20px #cc6666,0 0 40px #c08081,0 0 80px #c08081,inset 0 0 10px #fff3bd,inset 0 0 20px #c08081,inset 0 0 40px #c08081;animation:flicker 3.5s infinite}
    @keyframes flicker{0%,19%,21%,23%,25%,54%,56%,100%{opacity:1}20%,24%,55%{opacity:.4}}
    h2{font-family:'Bebas Neue',cursive;font-size:32px;text-align:center;color:#e50914;letter-spacing:2px;margin-bottom:20px;z-index:1;position:relative}
    input[type=text]{border:solid;border-radius:20px;padding:10px;font-family:'Arial Black',sans-serif;font-size:16px;width:65%;margin:10px 0;background:#2a2a2a;color:#fff;box-shadow:0 0 20px 5px #000}
    button{border-radius:20px;padding:10px 18px;font-family:'Arial Black',sans-serif;font-size:16px;width:auto;white-space:nowrap;margin:10px 0;background:maroon;color:#fff;transition:background .3s,transform .2s;box-shadow:0 0 10px rgba(229,9,20,.4);cursor:pointer}
    button:hover{background:#ff3333;transform:scale(1.05)}
    ul{list-style:none;padding:0;z-index:1;position:relative}
    li{margin:12px 0;background:rgba(40,40,40,.85);padding:12px;border-radius:10px;display:flex;align-items:center;justify-content:space-between; flex-wrap: wrap;
       box-shadow:0 0 15px rgba(229,9,20,.2);transition:transform .2s}
    li:hover{transform:scale(1.01)}li span{flex-grow:1;margin-left:10px}
    .floating-text{position:fixed;z-index:0;font-size:30px;font-family:'Bebas Neue',cursive;color:rgba(255,255,255,.05);animation:moveRT 30s linear infinite;pointer-events:none;font-weight:200;text-align:center;text-shadow:2px 2px 0 rgba(255,255,255,.08),4px 4px 0 rgba(0,0,0,.15)}
    @keyframes moveRT{0%{transform:translateY(-100vh) rotate(0)}100%{transform:translateY(100vh) rotate(360deg)}}
    .rt-banner{position:fixed;bottom:20px;left:50%;transform:translateX(-50%);padding:1.5rem 2rem;background:rgba(10,10,10,.85);border-radius:12px;border:1px solid #555;box-shadow:0 0 20px rgba(255,255,255,.1);color:#fff;font-family:'Georgia',serif;text-align:center;z-index:9999;animation:lightning-in 4s ease-out,show-then-hide 10s ease forwards;pointer-events:none}
    .rt-glow{font-size:1.1rem;color:#f8e9b0;text-shadow:0 0 5px #fff3bd,0 0 10px #ffe98e,0 0 20px #ffd700;animation:flicker 3.5s infinite}
    .rt-glow strong{display:block;margin-top:.5rem;font-size:1.8rem;color:#fdf6c9;text-shadow:0 0 5px #fff,0 0 10px #ffe95e,0 0 25px #ffdd00,0 0 40px #ffe34d}
    @keyframes lightning-in{0%{opacity:0;transform:translateX(-50%) scale(.8);filter:brightness(1)}20%{opacity:1;transform:translateX(-50%) scale(1);filter:brightness(2.5)}40%{filter:brightness(1)}60%{filter:brightness(2)}80%{filter:brightness(1.2)}100%{filter:brightness(1)}}
    @keyframes show-then-hide{0%,80%{opacity:1}100%{opacity:0;visibility:hidden}}

    /* === NEW: autocomplete dropdown === */
    #autocomplete {
      position: absolute;
      width: 65%;                /* same width as input */
      max-height: 260px;
      overflow-y: auto;
      background:#1e1e1e;
      border-radius:12px;
      border:1px solid #444;
      box-shadow:0 0 12px rgba(0,0,0,.45);
      z-index:10000;
      display:none;
    }
    .ac-item {
      display:flex;
      align-items:center;
      padding:6px 10px;
      cursor:pointer;
    }
    .ac-item img{
      width:46px;height:69px;object-fit:cover;border-radius:4px;flex-shrink:0;
    }
    .ac-item span{
      margin-left:10px;
      font-size:15px;
      color:#eee;
    }
    .ac-item:hover{
      background:#333;
    }
  </style>
</head>
<body>

  <!-- Floating watermarks -->
  <div class="floating-text" style="top: 10%; left: 10%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 30%; left: 70%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 60%; left: 40%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 80%; left: 20%;">RTSTUDIOS</div>

  <!-- Login -->
  <input type="text" id="usernameInput" placeholder="Enter your name...">
  <button onclick="loginUser()">Login</button>
  <p id="welcomeText" style="color: black;"></p>

  <!-- Add series -->
  <div style="position:relative;">
    <input type="text" id="seriesInput" placeholder="Enter series name..." disabled autocomplete="off">
    <!-- NEW dropdown -->
    <div id="autocomplete"></div>
  </div>  <button onclick="addSeries()">Add</button>

  <!-- List -->
  <ul id="seriesList"></ul>

  <!-- Banner -->
  <div class="rt-banner">
    <div class="rt-glow">Brought to you by<br><strong>RTSTUDIOS</strong></div>
  </div>
<a href="https://t.me/rtmoviesera" target="_blank">
  <button style="
    background-color: #229ED9;
    color: #fff;
    border: 1px solid #00bfff;
    padding: 10px 16px;
    font-size: 15px;
    border-radius: 6px;
    margin-top: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.3);
  ">
    📲 Click To Join Telegram Channel
  </button>
</a>
  <script>
    /* -------------------------  YOUR JS  ------------------------- */
    const TMDB_KEY = "276ce1441c92d4989b5a0080e47e0633";
    const IMG_BASE = "https://image.tmdb.org/t/p/w92";
    let currentUser = null;
    const seriesList = document.getElementById("seriesList");
    const inputBox   = document.getElementById("seriesInput");
    const acBox      = document.getElementById("autocomplete");

    /* ========== ACCOUNT ========== */
    function loginUser() {
      const username = document.getElementById("usernameInput").value.trim();
      if (!username) return;
      currentUser = username;
      document.getElementById("welcomeText").textContent = `Welcome, ${username}!`;
      inputBox.disabled = false;
      loadList();
    }

    /* ========== AUTOCOMPLETE ========== */
    let debounceTimer;
    inputBox.addEventListener("input", () => {
      const q = inputBox.value.trim();
      clearTimeout(debounceTimer);
      if (!q) return acBox.style.display="none";
      debounceTimer = setTimeout(() => fetchSuggestions(q), 350);
    });

    async function fetchSuggestions(query){
      const url = `https://api.themoviedb.org/3/search/multi?api_key=${TMDB_KEY}&language=en-US&page=1&include_adult=false&query=${encodeURIComponent(query)}`;
      try{
        const res = await fetch(url);
        const data = await res.json();
        acBox.innerHTML = "";
        data.results.slice(0,7).forEach(item=>{
          if(!item.poster_path) return;
          const div = document.createElement("div");
          div.className="ac-item";
          div.innerHTML = `<img src="${IMG_BASE}${item.poster_path}" alt=""><span>${item.title||item.name}</span>`;
          div.addEventListener("click",()=>{
            inputBox.value = item.title||item.name;
            inputBox.dataset.poster = IMG_BASE+item.poster_path;
            acBox.style.display="none";
          });
          acBox.appendChild(div);
        });
        acBox.style.display = acBox.childElementCount ? "block":"none";
      }catch(e){ console.error(e); }
    }

    /* close dropdown when clicking elsewhere */
    document.addEventListener("click",e=>{
      if(!acBox.contains(e.target) && e.target!==inputBox) acBox.style.display="none";
    });

    /* ========== ADD SERIES ITEM ========== */
    function addSeries() {
      const seriesName = inputBox.value.trim();
      if (!seriesName) return;

      const li        = document.createElement("li");
      const checkbox  = document.createElement("input");
      const span      = document.createElement("span");
      const deleteBtn = document.createElement("button");

      checkbox.type="checkbox";
      checkbox.addEventListener("change",()=>{li.style.textDecoration=checkbox.checked?"line-through":"none";saveList();});

      /* poster (if user picked from dropdown) */
      const posterUrl = inputBox.dataset.poster || "";
      if(posterUrl){
        const img = document.createElement("img");
        img.src  = posterUrl;
        img.style.width="60px";
        img.style.height="90px";
        img.style.objectFit="cover";
        img.style.borderRadius="6px";
        li.appendChild(img);
      }

      span.textContent = seriesName;
      deleteBtn.textContent="Delete";
      deleteBtn.addEventListener("click",()=>{li.remove();saveList();});

      li.append(checkbox,span,deleteBtn);
      seriesList.appendChild(li);

      /* reset */
      inputBox.value="";
      delete inputBox.dataset.poster;
      acBox.style.display="none";
      saveList();
    }

    /* ========== STORAGE ========== */
    function saveList(){
      if(!currentUser) return;
      const data = [...seriesList.querySelectorAll("li")].map(li=>{
        const name    = li.querySelector("span").textContent.trim();
        const watched = li.querySelector("input").checked;
        const imgEl   = li.querySelector("img");
        return {name,watched,poster: imgEl?imgEl.src:""};
      });
      localStorage.setItem(`watchlist_${currentUser}`,JSON.stringify(data));
    }

    function loadList(){
      seriesList.innerHTML="";
      if(!currentUser) return;
      const saved = localStorage.getItem(`watchlist_${currentUser}`);
      if(!saved) return;
      JSON.parse(saved).forEach(item=>{
        const li        = document.createElement("li");
        const checkbox  = document.createElement("input");
        const span      = document.createElement("span");
        const deleteBtn = document.createElement("button");

        checkbox.type="checkbox";
        checkbox.checked=item.watched;
        checkbox.addEventListener("change",()=>{li.style.textDecoration=checkbox.checked?"line-through":"none";saveList();});

        if(item.poster){
          const img = document.createElement("img");
          img.src=item.poster;
          img.style.width="60px";img.style.height="90px";img.style.objectFit="cover";img.style.borderRadius="6px";
          li.appendChild(img);
        }

        span.textContent=item.name;
        deleteBtn.textContent="Delete";
        deleteBtn.addEventListener("click",()=>{li.remove();saveList();});

        li.append(c<html lang="en">
<head>
  <!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-7P8G6MP4Q6"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-7P8G6MP4Q6');
</script>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>RTSTUDIOS Watchlist</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Poppins&display=swap" rel="stylesheet">
  <style>
    /* ▸▸ your existing styles stay the same … ◂◂ */
    /* (they’re collapsed here for brevity)                                      */
    /* ------------------------------------------------------------------------ */
    body{font-family:'Poppins',sans-serif;background:radial-gradient(circle at top,#0e0e0e 20%,#1a1a1a 100%);color:#fff;max-width:700px;margin:30px auto;padding:30px;border-radius:15px;position:relative;overflow-y:auto;box-shadow:0 0 15px rgba(0,0,0,.35);background-image:url('https://www.transparenttextures.com/patterns/asfalt-dark.png');background-repeat:repeat}
    body::before{content:"";position:absolute;inset:-10px;border-radius:inherit;pointer-events:none;z-index:9998;box-shadow:0 0 10px #c08081,0 0 20px #cc6666,0 0 40px #c08081,0 0 80px #c08081,inset 0 0 10px #fff3bd,inset 0 0 20px #c08081,inset 0 0 40px #c08081;animation:flicker 3.5s infinite}
    @keyframes flicker{0%,19%,21%,23%,25%,54%,56%,100%{opacity:1}20%,24%,55%{opacity:.4}}
    h2{font-family:'Bebas Neue',cursive;font-size:32px;text-align:center;color:#e50914;letter-spacing:2px;margin-bottom:20px;z-index:1;position:relative}
    input[type=text]{border:solid;border-radius:20px;padding:10px;font-family:'Arial Black',sans-serif;font-size:16px;width:65%;margin:10px 0;background:#2a2a2a;color:#fff;box-shadow:0 0 20px 5px #000}
    button{border-radius:20px;padding:10px 18px;font-family:'Arial Black',sans-serif;font-size:16px;width:auto;white-space:nowrap;margin:10px 0;background:maroon;color:#fff;transition:background .3s,transform .2s;box-shadow:0 0 10px rgba(229,9,20,.4);cursor:pointer}
    button:hover{background:#ff3333;transform:scale(1.05)}
    ul{list-style:none;padding:0;z-index:1;position:relative}
    li{margin:12px 0;background:rgba(40,40,40,.85);padding:12px;border-radius:10px;display:flex;align-items:center;justify-content:space-between; flex-wrap: wrap;
       box-shadow:0 0 15px rgba(229,9,20,.2);transition:transform .2s}
    li:hover{transform:scale(1.01)}li span{flex-grow:1;margin-left:10px}
    .floating-text{position:fixed;z-index:0;font-size:30px;font-family:'Bebas Neue',cursive;color:rgba(255,255,255,.05);animation:moveRT 30s linear infinite;pointer-events:none;font-weight:200;text-align:center;text-shadow:2px 2px 0 rgba(255,255,255,.08),4px 4px 0 rgba(0,0,0,.15)}
    @keyframes moveRT{0%{transform:translateY(-100vh) rotate(0)}100%{transform:translateY(100vh) rotate(360deg)}}
    .rt-banner{position:fixed;bottom:20px;left:50%;transform:translateX(-50%);padding:1.5rem 2rem;background:rgba(10,10,10,.85);border-radius:12px;border:1px solid #555;box-shadow:0 0 20px rgba(255,255,255,.1);color:#fff;font-family:'Georgia',serif;text-align:center;z-index:9999;animation:lightning-in 4s ease-out,show-then-hide 10s ease forwards;pointer-events:none}
    .rt-glow{font-size:1.1rem;color:#f8e9b0;text-shadow:0 0 5px #fff3bd,0 0 10px #ffe98e,0 0 20px #ffd700;animation:flicker 3.5s infinite}
    .rt-glow strong{display:block;margin-top:.5rem;font-size:1.8rem;color:#fdf6c9;text-shadow:0 0 5px #fff,0 0 10px #ffe95e,0 0 25px #ffdd00,0 0 40px #ffe34d}
    @keyframes lightning-in{0%{opacity:0;transform:translateX(-50%) scale(.8);filter:brightness(1)}20%{opacity:1;transform:translateX(-50%) scale(1);filter:brightness(2.5)}40%{filter:brightness(1)}60%{filter:brightness(2)}80%{filter:brightness(1.2)}100%{filter:brightness(1)}}
    @keyframes show-then-hide{0%,80%{opacity:1}100%{opacity:0;visibility:hidden}}

    /* === NEW: autocomplete dropdown === */
    #autocomplete {
      position: absolute;
      width: 65%;                /* same width as input */
      max-height: 260px;
      overflow-y: auto;
      background:#1e1e1e;
      border-radius:12px;
      border:1px solid #444;
      box-shadow:0 0 12px rgba(0,0,0,.45);
      z-index:10000;
      display:none;
    }
    .ac-item {
      display:flex;
      align-items:center;
      padding:6px 10px;
      cursor:pointer;
    }
    .ac-item img{
      width:46px;height:69px;object-fit:cover;border-radius:4px;flex-shrink:0;
    }
    .ac-item span{
      margin-left:10px;
      font-size:15px;
      color:#eee;
    }
    .ac-item:hover{
      background:#333;
    }
  </style>
</head>
<body>

  <!-- Floating watermarks -->
  <div class="floating-text" style="top: 10%; left: 10%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 30%; left: 70%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 60%; left: 40%;">RTSTUDIOS</div>
  <div class="floating-text" style="top: 80%; left: 20%;">RTSTUDIOS</div>

  <!-- Login -->
  <input type="text" id="usernameInput" placeholder="Enter your name...">
  <button onclick="loginUser()">Login</button>
  <p id="welcomeText" style="color: black;"></p>

  <!-- Add series -->
  <div style="position:relative;">
    <input type="text" id="seriesInput" placeholder="Enter series name..." disabled autocomplete="off">
    <!-- NEW dropdown -->
    <div id="autocomplete"></div>
  </div>  <button onclick="addSeries()">Add</button>

  <!-- List -->
  <ul id="seriesList"></ul>

  <!-- Banner -->
  <div class="rt-banner">
    <div class="rt-glow">Brought to you by<br><strong>RTSTUDIOS</strong></div>
  </div>
<a href="https://t.me/rtmoviesera" target="_blank">
  <button style="
    background-color: #229ED9;
    color: #fff;
    border: 1px solid #00bfff;
    padding: 10px 16px;
    font-size: 15px;
    border-radius: 6px;
    margin-top: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.3);
  ">
    📲 Click To Join Telegram Channel
  </button>
</a>
  <script>
    /* -------------------------  YOUR JS  ------------------------- */
    const TMDB_KEY = "276ce1441c92d4989b5a0080e47e0633";
    const IMG_BASE = "https://image.tmdb.org/t/p/w92";
    let currentUser = null;
    const seriesList = document.getElementById("seriesList");
    const inputBox   = document.getElementById("seriesInput");
    const acBox      = document.getElementById("autocomplete");

    /* ========== ACCOUNT ========== */
    function loginUser() {
      const username = document.getElementById("usernameInput").value.trim();
      if (!username) return;
      currentUser = username;
      document.getElementById("welcomeText").textContent = `Welcome, ${username}!`;
      inputBox.disabled = false;
      loadList();
    }

    /* ========== AUTOCOMPLETE ========== */
    let debounceTimer;
    inputBox.addEventListener("input", () => {
      const q = inputBox.value.trim();
      clearTimeout(debounceTimer);
      if (!q) return acBox.style.display="none";
      debounceTimer = setTimeout(() => fetchSuggestions(q), 350);
    });

    async function fetchSuggestions(query){
      const url = `https://api.themoviedb.org/3/search/multi?api_key=${TMDB_KEY}&language=en-US&page=1&include_adult=false&query=${encodeURIComponent(query)}`;
      try{
        const res = await fetch(url);
        const data = await res.json();
        acBox.innerHTML = "";
        data.results.slice(0,7).forEach(item=>{
          if(!item.poster_path) return;
          const div = document.createElement("div");
          div.className="ac-item";
          div.innerHTML = `<img src="${IMG_BASE}${item.poster_path}" alt=""><span>${item.title||item.name}</span>`;
          div.addEventListener("click",()=>{
            inputBox.value = item.title||item.name;
            inputBox.dataset.poster = IMG_BASE+item.poster_path;
            acBox.style.display="none";
          });
          acBox.appendChild(div);
        });
        acBox.style.display = acBox.childElementCount ? "block":"none";
      }catch(e){ console.error(e); }
    }

    /* close dropdown when clicking elsewhere */
    document.addEventListener("click",e=>{
      if(!acBox.contains(e.target) && e.target!==inputBox) acBox.style.display="none";
    });

    /* ========== ADD SERIES ITEM ========== */
    function addSeries() {
      const seriesName = inputBox.value.trim();
      if (!seriesName) return;

      const li        = document.createElement("li");
      const checkbox  = document.createElement("input");
      const span      = document.createElement("span");
      const deleteBtn = document.createElement("button");

      checkbox.type="checkbox";
      checkbox.addEventListener("change",()=>{li.style.textDecoration=checkbox.checked?"line-through":"none";saveList();});

      /* poster (if user picked from dropdown) */
      const posterUrl = inputBox.dataset.poster || "";
      if(posterUrl){
        const img = document.createElement("img");
        img.src  = posterUrl;
        img.style.width="60px";
        img.style.height="90px";
        img.style.objectFit="cover";
        img.style.borderRadius="6px";
        li.appendChild(img);
      }

      span.textContent = seriesName;
      deleteBtn.textContent="Delete";
      deleteBtn.addEventListener("click",()=>{li.remove();saveList();});

      li.append(checkbox,span,deleteBtn);
      seriesList.appendChild(li);

      /* reset */
      inputBox.value="";
      delete inputBox.dataset.poster;
      acBox.style.display="none";
      saveList();
    }

    /* ========== STORAGE ========== */
    function saveList(){
      if(!currentUser) return;
      const data = [...seriesList.querySelectorAll("li")].map(li=>{
        const name    = li.querySelector("span").textContent.trim();
        const watched = li.querySelector("input").checked;
        const imgEl   = li.querySelector("img");
        return {name,watched,poster: imgEl?imgEl.src:""};
      });
      localStorage.setItem(`watchlist_${currentUser}`,JSON.stringify(data));
    }

    function loadList(){
      seriesList.innerHTML="";
      if(!currentUser) return;
      const saved = localStorage.getItem(`watchlist_${currentUser}`);
      if(!saved) return;
      JSON.parse(saved).forEach(item=>{
        const li        = document.createElement("li");
        const checkbox  = document.createElement("input");
        const span      = document.createElement("span");
        const deleteBtn = document.createElement("button");

        checkbox.type="checkbox";
        checkbox.checked=item.watched;
        checkbox.addEventListener("change",()=>{li.style.textDecoration=checkbox.checked?"line-through":"none";saveList();});

        if(item.poster){
          const img = document.createElement("img");
          img.src=item.poster;
          img.style.width="60px";img.style.height="90px";img.style.objectFit="cover";img.style.borderRadius="6px";
          li.appendChild(img);
        }

        span.textContent=item.name;
        deleteBtn.textContent="Delete";
        deleteBtn.addEventListener("click",()=>{li.remove();saveList();});

        li.append(checkbox,span,deleteBtn);
        li.style.textDecoration=item.watched?"line-through":"none";
        seriesList.appendChild(li);
      });
    }
  </script>
</body>
</html>
heckbox,span,deleteBtn);
        li.style.textDecoration=item.watched?"line-through":"none";
        seriesList.appendChild(li);
      });
    }
  </script>
</body>
</html>
