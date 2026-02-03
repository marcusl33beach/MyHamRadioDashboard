# 📻 MyHamDashboard: Your Personal Shack Command Center

**Keep your eyes on the hobby, not the code.** `MyHamDashboard` is a lightweight, single-file "cockpit" for Ham and GMRS operators. No servers, no complex dependencies, and zero overhead—just double-click and get back to the bands. 📡

---

### 🚀 The "Quick Start"
1.  **Download** the repository.
2.  **Double-click** `index.html` to open it in your favorite browser.
3.  **Explore** the different pages from the central console.
4.  **Stay Informed** with a persistent dashboard that lives entirely on your machine.

---

### 🛠 Recent Signal Reports (Changelog)
* **Central Console (`index.html`):** A new central hub to access all the different pages of the dashboard.
* **Unified Theme:** All pages now share a consistent, modern, and dark theme.
* **The Grid:** Editable `contentData` tiles in a 4x3 layout with cache-busted refreshing to keep data current.
* **"Cyclops" Camera Engine:** Rotate multiple camera URLs (weather cams, shack cams, or repeater sites) inside a single tile on a configurable timer.
* **Camera Grid Lightbox:** Click Tile 8 to instantly pop open a full-screen grid showing all your rotation cameras at once—perfect for spotting storms or traffic jams.
* **The Ticker:** A slower, "easy-on-the-eyes" scrolling ticker with live weather data and NWS alerts for the Cincinnati/NKY area appended automatically.
* **RSS Integration:** Add your favorite news feeds directly into the scrolling ticker via the settings menu.
* **On-the-Fly Settings:** A sleek lightbox editor for tiles, menu links, coordinates, and refresh intervals. Everything saves to `localStorage` (`mhd_settings`).
* **GMRS Contact Logger (`contacts.html`):** A visual, map-based logbook. Right-click on the map to drop a pin where you made contact, save their callsign, and keep notes on the QSO.
* **Net Check-In Log (`NetRadioLog.html`):** A dedicated tool for Net Control Stations. Start a net with a timestamped header and quickly log check-ins with locations and signal reports.

---

### 🛰 Why Local-First?
In the spirit of emergency preparedness, this dashboard doesn't need a cloud to rain on your parade. It runs directly from your filesystem.
* **Portable:** Throw it on a thumb drive and take it to Field Day.
* **Private:** Your logs and settings stay on your machine, not a third-party server.
* **Serverless:** If you can double-click a file, you're "on the air." No `npm install` required.

---

### 📦 The Manifest
* **`index.html`** – The central hub for the dashboard, providing access to all other pages.
* **`dashboard.html`** – The brains: 4x3 grid, scrolling ticker, settings engine, camera rotator, and camera grid lightbox.
* **`contacts.html`** – Your digital logbook for GMRS contacts (City/State) powered by Leaflet maps and local storage.
* **`NetRadioLog.html`** – A streamlined interface for logging Nets, grouped by date and Net Control callsign.
* **`frequencies.html`** – A personal and editable list of GMRS frequencies.

---

### ⚠️ Signal Report (Notes & Limitations)
* **QRM (Interference):** Some sites block embedding via `X-Frame-Options`. If a tile won't load, the dashboard will gracefully pop it into a new tab for you.
* **File Permissions:** Running via `file://` can occasionally block remote fetches (like NWS alerts) in hyper-secure browsers. Most features work out of the box.

---

### 🤝 Credits & Acknowledgments
* **Inspiration:** Huge thanks to **VA3HDL/hamdashboard** for the brilliant original concept. 
* **The Rewrite:** This version is a ground-up rework focusing on UI fluidity, camera rotations, map-integrated logging, and a "no-code" settings editor for easier customization.

---

### 📜 License
Tinker freely! This is open-source for the radio community. Just remember: **Keep it clean on the air and in the code.**

73s — See you on the waterfall! 🎙️✨