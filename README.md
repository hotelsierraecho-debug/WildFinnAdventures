That is the exact code. PerfecThat is the exact code. Perfect.
But you just pasted it to me in our chat. You need to paste that exact block into GitHub.
Here is the tactical correction to keep us moving. Open a new tab in your browser and go to GitHub.
 * Click "Add file" -> "Create new file".
 * Name it: manifest.json
 * Paste that exact code you just sent me into the big black box on GitHub.
 * Click the green "Commit changes" button at the top right.
Once you click "Commit" on GitHub and see manifest.json sitting in your repository, tell me. We are 2 minutes away from having this live.

# WildFinnAdventures
Bocas del Toro Guide
t.
But you just pasted it to me in our chat. You need to paste that exact block into GitHub.
Here is the tactical correction to keep us moving. Open a new tab in your browser and go to GitHub.
 * Click "Add file" -> "Create new file".
 * Name it: manifest.json
 * Paste that exact code you just sent me into the big black box on GitHub.
 * Click the green "Commit changes" button at the top right.
Once you click "Commit" on GitHub and see manifest.json sitting in your repository, tell me. We are 2 minutes away from having this live.

# WildFinnAdventures
Bocas del Toro Guide
const CACHE_NAME = 'wild-finn-core-v2';
const CORE_ASSETS = [
  './',
  './index.html',
  './manifest.json',
  './sw.js'
];

self.addEventListener('install', (event) => {
  self.skipWaiting();
  event.waitUntil(
    caches.open(CACHE_NAME).then((cache) => {
      console.log("Wild Finn: Caching Core Assets");
      return cache.addAll(CORE_ASSETS);
    })
  );
});

self.addEventListener('activate', (event) => {
  event.waitUntil(
    caches.keys().then((cacheNames) => {
      return Promise.all(
        cacheNames.map((cache) => {
          if (cache !== CACHE_NAME) return caches.delete(cache);
        })
      );
    })
  );
});

self.addEventListener('fetch', (event) => {
  event.respondWith(
    caches.match(event.request).then((cachedResponse) => {
      return cachedResponse || fetch(event.request);
    }).catch(() => {
      console.error("Master Audit: Network failure and asset not in cache.");
    })
  );
});



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Wild Finn</title>
    <link rel="manifest" href="./manifest.json">
    
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="apple-mobile-web-app-title" content="Wild Finn">
    <link rel="apple-touch-icon" href="https://img.icons8.com/color/192/compass--v1.png">

  {
  "name": "Wild Finn: Artisan's Adventure",
  "short_name": "Wild Finn",
  "description": "Biological Intelligence & Lead Guide Survival for Bocas del Toro.",
  "start_url": "./index.html",
  "display": "standalone",
  "background_color": "#121212",
  "theme_color": "#27ae60",
  "orientation": "portrait-primary",
  "icons": [
    {
      "src": "https://img.icons8.com/color/192/compass--v1.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "https://img.icons8.com/color/512/compass--v1.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}


<style>
        /* THE ARTISAN AESTHETIC */
        :root {
            --bg: #121212; --surface: #1e1e1e; --surface-border: #333;
            --primary: #27ae60; --secondary: #b8860b; --danger: #e74c3c;
            --text-main: #ffffff; --text-muted: #aaaaaa;
        }
        body, html { 
            margin: 0; padding: 0; height: 100%; width: 100%;
            font-family: "Georgia", serif; /* Educated Base */
            background-color: var(--bg); color: var(--text-main);
            overflow: hidden; 
        }
        header { padding: 20px 15px; background-color: var(--surface); border-bottom: 2px solid var(--primary); text-align: center; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }
        header h1 { margin: 0; font-size: 24px; letter-spacing: 1px; text-transform: uppercase; }
        .grit-quote { font-size: 12px; color: var(--text-muted); margin-top: 5px; font-style: italic; font-family: "Georgia", serif; }

        #app-content { height: calc(100% - 150px); overflow-y: auto; padding: 15px; padding-bottom: 80px; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }
        .tab-content { display: none; animation: fadeIn 0.3s ease; }
        .tab-content.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(5px); } to { opacity: 1; transform: translateY(0); } }

        .card { background: var(--surface); border: 1px solid var(--surface-border); border-radius: 12px; padding: 15px; margin-bottom: 15px; }
        h2 { margin-top: 0; font-size: 18px; color: var(--primary); border-bottom: 1px solid var(--surface-border); padding-bottom: 8px; font-family: "Georgia", serif; }
        
        .action-list { list-style: none; padding: 0; margin: 0; }
        .action-list li { margin-bottom: 10px; }
        .btn { display: block; width: 100%; text-align: center; padding: 14px; border-radius: 8px; text-decoration: none; font-weight: bold; box-sizing: border-box; border: none; cursor: pointer; text-transform: uppercase; font-size: 14px; }
        .btn-danger { background-color: rgba(231, 76, 60, 0.1); color: var(--danger); border: 1px solid var(--danger); }
        .btn-whatsapp { background-color: rgba(39, 174, 96, 0.1); color: var(--primary); border: 1px solid var(--primary); }
        .btn-action { background-color: var(--primary); color: #000; }

        #camera-feed { width: 100%; border-radius: 8px; background: #000; height: 300px; object-fit: cover; margin-bottom: 10px; }
        
        nav { position: fixed; bottom: 0; width: 100%; background: var(--surface); border-top: 1px solid var(--surface-border); display: flex; justify-content: space-around; padding: 10px 0 20px 0; z-index: 1000; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }
        .nav-item { color: var(--text-muted); font-size: 12px; text-align: center; text-transform: uppercase; font-weight: bold; cursor: pointer; padding: 10px; flex: 1; }
        .nav-item.active { color: var(--primary); }
        .nav-icon { font-size: 24px; display: block; margin-bottom: 4px; }
    </style>
</head>
<body>

    <header>
        <h1>Wild Finn</h1>
        <div class="grit-quote">"The Archipelago doesn't compromise. Neither do we."</div>
    </header>

    <div id="app-content">
        
        <div id="tab-lens" class="tab-content active">
            <div class="card">
                <h2>Bio-Lens Identifier</h2>
                <p style="font-size: 13px; color: var(--text-muted);">Primary: Live API. Secondary: Offline Stash.</p>
                
                <video id="camera-feed" autoplay playsinline></video>
                <canvas id="capture-canvas" style="display:none;"></canvas>
                
                <div style="display: flex; gap: 8px; margin-top: 10px;">
                    <button class="btn btn-action" onclick="activateLens()" style="flex: 1; padding: 10px; font-size: 12px;">1. LENS ON</button>
                    <button class="btn" onclick="identifyLive()" style="flex: 1; padding: 10px; font-size: 12px; background: var(--secondary); color: #000;">2. LIVE ID</button>
                    <button class="btn" onclick="stashOffline()" style="flex: 1; padding: 10px; font-size: 12px; background: #333; color: white;">3. STASH</button>
                </div>
                
                <div id="lens-status" style="margin-top: 15px; font-weight: bold; text-align: center; font-family: -apple-system, BlinkMacSystemFont, sans-serif;">CAMERA STANDBY</div>
                <div id="stash-count" style="font-size: 12px; color: var(--secondary); margin-top: 5px; text-align: center;">STASHED: 0</div>
                
                <div id="ai-result" style="display:none; margin-top: 15px; padding: 10px; background: #2c2c2c; border-left: 4px solid var(--primary); border-radius: 4px;">
                    <strong style="color: var(--primary); font-family: -apple-system, BlinkMacSystemFont, sans-serif;">ANALYSIS:</strong>
                    <p id="result-text" style="margin: 5px 0; font-size: 14px;"></p>
                </div>
            </div>
        </div>

        <div id="tab-medical" class="tab-content">
            <div class="card" style="border-left: 4px solid var(--danger);">
                <h2 style="color: var(--danger);">Tactical Triage</h2>
                <ul class="action-list">
                    <li><a href="tel:911" class="btn btn-danger">911 - NATIONAL DISPATCH</a></li>
                    <li><a href="tel:*455" class="btn btn-danger">*455 - RED CROSS (CRUZ ROJA)</a></li>
                    <li><a href="tel:+5073175000" class="btn btn-danger">U.S. EMBASSY (24/7)</a></li>
                </ul>
            </div>
            <div class="card" style="border-left: 4px solid var(--primary);">
                <h2>Private Evac & Labs</h2>
                <ul class="action-list">
                    <li><a href="https://wa.me/50764218289" target="_blank" class="btn btn-whatsapp">🏥 HOSP. CHIRIQUÍ (WHATSAPP)</a></li>
                    <li><a href="https://wa.me/5077579366" target="_blank" class="btn btn-whatsapp">🏥 BOCAS MEDICAL CARE</a></li>
                </ul>
            </div>
        </div>

        <div id="tab-logistics" class="tab-content">
            <div class="card">
                <h2>The Ground Game</h2>
                <ul class="action-list">
                    <li><a href="https://wa.me/50627550617" target="_blank" class="btn btn-whatsapp">🚐 CARIBE SHUTTLE (BOCAS/PTY)</a></li>
                    <li><a href="https://wa.me/50760038181" target="_blank" class="btn btn-whatsapp">🚙 HELLO PANAMA (PRIVATE SUV)</a></li>
                </ul>
            </div>
            <div class="card">
                <h2>The Floating Life</h2>
                <p style="font-size: 13px; color: var(--text-muted); margin-bottom: 10px;">Cash only. Watch the tides. Tip your captain.</p>
                <ul class="action-list">
                    <li><a href="https://wa.me/50763289249" target="_blank" class="btn btn-whatsapp">🌮 THE FLOATING BAR</a></li>
                    <li><a href="https://wa.me/50767622058" target="_blank" class="btn btn-whatsapp">🥥 THE BLUE COCONUT</a></li>
                </ul>
            </div>
        </div>

        <div id="tab-dream" class="tab-content">
            <div class="card" style="border-left: 4px solid var(--secondary); background: linear-gradient(145deg, #1e1e1e, #2a2a2a);">
                <h2 style="color: var(--secondary);">The Artisan's Itinerary</h2>
                <ul class="action-list" style="margin-top: 15px;">
                    <li style="background: #121212; padding: 10px; border-radius: 8px; border: 1px solid #333; display: flex; justify-content: space-between; align-items: center;">
                        <span style="font-family: -apple-system, BlinkMacSystemFont, sans-serif;">🦥 <strong>Sloth Island Run</strong><br><small style="color: #aaa;">Mangrove kayak tour</small></span>
                        <input type="checkbox" style="width: 20px; height: 20px;">
                    </li>
                    <li style="background: #121212; padding: 10px; border-radius: 8px; border: 1px solid #333; display: flex; justify-content: space-between; align-items: center;">
                        <span style="font-family: -apple-system, BlinkMacSystemFont, sans-serif;">🍫 <strong>Up in the Hill</strong><br><small style="color: #aaa;">Organic Cacao Farm Hike</small></span>
                        <input type="checkbox" style="width: 20px; height: 20px;">
                    </li>
                </ul>
            </div>
        </div>

    </div>

    <nav>
        <div class="nav-item active" onclick="switchTab('lens', this)"><span class="nav-icon">🌿</span>Lens</div>
        <div class="nav-item" onclick="switchTab('medical', this)"><span class="nav-icon">🛡️</span>Survival</div>
        <div class="nav-item" onclick="switchTab('logistics', this)"><span class="nav-icon">🗺️</span>Transit</div>
        <div class="nav-item" onclick="switchTab('dream', this)"><span class="nav-icon">✨</span>Dream</div>
    </nav>

    <script>
        // 1. SERVICE WORKER REGISTRATION
        if ('serviceWorker' in navigator) {
            window.addEventListener('load', () => {
                navigator.serviceWorker.register('./sw.js')
                    .then(() => console.log("Wild Finn: Offline Engine Armed."))
                    .catch((err) => console.error("Expert Warning: Service Worker Failed.", err));
            });
        }

        // 2. TAB SWITCHING (Battery Saver Fix)
        function switchTab(tabId, element) {
            document.querySelectorAll('.tab-content').forEach(tab => tab.classList.remove('active'));
            document.querySelectorAll('.nav-item').forEach(nav => nav.classList.remove('active'));
            
            document.getElementById('tab-' + tabId).classList.add('active');
            element.classList.add('active');

            const video = document.getElementById('camera-feed');
            if (tabId !== 'lens' && video.srcObject) {
                video.srcObject.getTracks().forEach(track => track.stop());
                video.srcObject = null;
                document.getElementById('lens-status').innerText = "CAMERA STANDBY";
                document.getElementById('lens-status').style.color = "var(--text-muted)";
            }
        }

        // 3. CAMERA ACTIVATION
        async function activateLens() {
            const video = document.getElementById('camera-feed');
            const status = document.getElementById('lens-status');
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: 'environment' } });
                video.srcObject = stream;
                status.innerText = "LENS ACTIVE: READY FOR SPECIMEN";
                status.style.color = "var(--primary)";
            } catch (err) {
                status.innerText = "ERROR: CAMERA PERMISSION DENIED";
                status.style.color = "var(--danger)";
            }
        }

        // 4A. LIVE AI IDENTIFICATION (PlantNet Ready)
        async function identifyLive() {
            const video = document.getElementById('camera-feed');
            const canvas = document.getElementById('capture-canvas');
            const status = document.getElementById('lens-status');
            const resultBox = document.getElementById('ai-result');
            const resultText = document.getElementById('result-text');

            if (!video.srcObject) return alert("Activate Lens First.");

            status.innerText = "UPLOADING TO NEURAL NET...";
            status.style.color = "var(--secondary)";
            canvas.width = video.videoWidth; canvas.height = video.videoHeight;
            canvas.getContext('2d').drawImage(video, 0, 0);
            
            video.style.opacity = 0; setTimeout(() => video.style.opacity = 1, 200);

            canvas.toBlob(async (blob) => {
                const formData = new FormData();
                formData.append('images', blob, 'specimen.jpg');
                formData.append('organs', 'auto'); 

                // *** PASTE YOUR PLANTNET API KEY HERE LATER ***
                const API_KEY = 'YOUR_ACTUAL_API_KEY_GOES_HERE'; 
                const API_URL = `https://my-api.plantnet.org/v2/identify/all?api-key=${API_KEY}`;

                try {
                    const response = await fetch(API_URL, { method: 'POST', body: formData });
                    const data = await response.json();

                    resultBox.style.display = 'block';
                    
                    if (data.results && data.results.length > 0) {
                        const bestMatch = data.results[0];
                        status.innerText = `MATCH: ${(bestMatch.score * 100).toFixed(1)}% CERTAINTY`;
                        status.style.color = "var(--primary)";
                        resultText.innerHTML = `<strong>Scientific:</strong> <em>${bestMatch.species.scientificNameWithoutAuthor}</em><br><strong>Common:</strong> ${bestMatch.species.commonNames.slice(0, 2).join(', ') || 'None'}`;
                    } else {
                        status.innerText = "NO MATCH FOUND / WAITING FOR API KEY";
                        status.style.color = "var(--danger)";
                        resultText.innerText = "Insert valid PlantNet API key in code to connect live.";
                    }
                } catch (error) {
                    status.innerText = "NETWORK FAILED: USE STASH";
                    status.style.color = "var(--danger)";
                    resultText.innerText = "API unreachable or key invalid. Switch to offline stashing.";
                    resultBox.style.display = 'block';
                }
            }, 'image/jpeg', 0.8);
        }

        // 4B. OFFLINE STASH (Memory Compressed Fix)
        function stashOffline() {
            const video = document.getElementById('camera-feed');
            const canvas = document.getElementById('capture-canvas');
            const status = document.getElementById('lens-status');

            if (!video.srcObject) return alert("Activate Lens First.");

            const scaleFactor = 0.4; 
            canvas.width = video.videoWidth * scaleFactor; canvas.height = video.videoHeight * scaleFactor;
            canvas.getContext('2d').drawImage(video, 0, 0, canvas.width, canvas.height);
            const imageData = canvas.toDataURL('image/jpeg', 0.5); 

            try {
                let vault = JSON.parse(localStorage.getItem('wildFinnVault') || '[]');
                vault.push({ id: Date.now(), image: imageData });
                localStorage.setItem('wildFinnVault', JSON.stringify(vault));
                status.innerText = "SECURED IN OFFLINE VAULT.";
                status.style.color = "var(--secondary)";
                document.getElementById('stash-count').innerText = `STASHED: ${vault.length}`;
            } catch (e) {
                status.innerText = "VAULT FULL. CLEAR CACHE.";
                status.style.color = "var(--danger)";
            }
            video.style.opacity = 0; setTimeout(() => video.style.opacity = 1, 200);
        }

        window.addEventListener('load', () => {
            let vault = JSON.parse(localStorage.getItem('wildFinnVault') || '[]');
            document.getElementById('stash-count').innerText = `STASHED: ${vault.length}`;
        });
    </script>
</body>
</html>

