# 📻 MyHamDashboard: Your Personal Shack Command Center

**Keep your eyes on the hobby, not the code.** `MyHamDashboard` is a lightweight, single-file "cockpit" for Ham and GMRS operators. No servers, no complex dependencies, and zero overhead—just double-click and get back to the bands. 📡

---

### 🚀 The "Quick Start"
1.  **Download** the repository.
2.  **Double-click** `Dashboard.html` to open it in your favorite browser.
3.  **Configure** your shack via the **Menu → Settings** lightbox.
4.  **Stay Informed** with a persistent dashboard that lives entirely on your machine.

---

### 🛠 Recent Signal Reports (Changelog)
*   **The Grid:** Editable `contentData` tiles in a 4x3 layout with cache-busted refreshing to keep data current.
*   **"Cyclops" Camera Engine:** Rotate multiple camera URLs (weather cams, shack cams, or repeater sites) inside a single tile on a configurable timer.
*   **On-the-Fly Settings:** A sleek lightbox editor for tiles, menu links, coordinates, and refresh intervals. Everything saves to `localStorage` (`mhd_settings`).
*   **The Ticker:** A slower, "easy-on-the-eyes" scrolling ticker with live NWS alerts appended automatically.
*   **Contact Logging:** Added `contacts.html`—a snappy GMRS logger (City/State) powered by IndexedDB with a one-click SQLite export for your records.

---

### 🛰 Why Local-First?
In the spirit of emergency preparedness, this dashboard doesn't need a cloud to rain on your parade. It runs directly from your filesystem.
*   **Portable:** Throw it on a thumb drive and take it to Field Day.
*   **Private:** Your data stays on your machine, not a third-party server.
*   **Serverless:** If you can double-click a file, you're "on the air." No `npm install` required.

---

### 📦 The Manifest
*   **`Dashboard.html`** – The brains: 4x3 grid, scrolling ticker, settings engine, and camera rotator.
*   **`contacts.html`** – Your digital logbook for GMRS contacts (City/State) with local storage.

---

### ⚠️ Signal Report (Notes & Limitations)
*   **QRM (Interference):** Some sites block embedding via `X-Frame-Options`. If a tile won't load, the dashboard will gracefully pop it into a new tab for you.
*   **File Permissions:** Running via `file://` can occasionally block remote fetches (like NWS alerts) in hyper-secure browsers. Most features work out of the box.

---

### 🤝 Credits & Acknowledgments
*   **Inspiration:** Huge thanks to **VA3HDL/hamdashboard** for the brilliant original concept. 
*   **The Rewrite:** This version is a ground-up rework focusing on UI fluidity, camera rotations, and a "no-code" settings editor for easier customization.

---

### 📜 License
Tinker freely! This is open-source for the radio community. Just remember: **Keep it clean on the air and in the code.**

73s — See you on the waterfall! 🎙️✨