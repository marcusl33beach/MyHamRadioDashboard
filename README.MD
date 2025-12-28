## 📻 MyHamRadioDashboard

### The "Shack-in-a-Browser" Display for the Modern Operator

Welcome, ragchewers and net controllers!\! Sometimes you want to check propagation conditions, local radar, and solar wind without firing up 15 different browser tabs or buying another Raspberry Pi that you'll definitely configure "someday."

This is a lightweight, single-file HTML dashboard designed to run locally on your machine. It puts the "control" in Mission Control, and ready to be forked for your own QTH.

----

### 📡 Features (The "Specs")

  * **The 4x3 Grid of Glory:** Displays 12 monitored frequencies... err, images, perfectly sized to your screen. No scrolling required (unless you want to).
  * **Forced Refresh:** All images and maps in the grid are automatically **refreshed every 10 minutes** using cache-busting techniques, ensuring you always see the latest radar loop or space weather conditions.
  * **Zero-Install Deployment:** No Docker containers, no npm install, no compiling kernels. Just download the HTML file and double-click it like it's 1999.
  * **The Stealth Menu:** A stealthy menu button integrated into the ticker bar with helpful ham links, including **HamStudy.org**.
  * **The Ticker of Truth:** A transparent, floating ticker at the bottom that pulls live local weather (temp, wind, chance of rain) based on your set latitude/longitude.

----

### 🔧 Customization cheat sheet (aka the knobs you’ll actually use)
- Change tiles: edit the `contentData` array near the top of `Dashboard.html` — it's a plain JS array of `{ url, title }` objects.
- Location for ticker: edit `LATITUDE` and `LONGITUDE` in `Dashboard.html` to point to your QTH.
- Refresh intervals: edit `IMAGE_REFRESH_RATE_MS` and `ALERTS_REFRESH_MS` (defaults are 600000 ms = 10 minutes).
- MeshMap / embedded pages: the dashboard tries to iframe sites like MeshMap but will fall back to opening a new tab if framing is blocked.

-----

### Troubleshooting quick hits
- If a tile shows "Image Unavailable": open DevTools → Network and inspect the request. Many map portals return HTML (not an image) or block hotlinking.
- If a page refuses to embed: you’ll see an empty iframe or browser console X-Frame-Options/CSP error — fallback opens the site in a new tab.
- Want automatic detection of failing tiles? Tell me and I’ll add a small JS logger to capture failing URLs.

-----

### Notes for the distro and other copilots
- The central edit points are `contentData`, `LATITUDE`/`LONGITUDE`, and `IMAGE_REFRESH_RATE_MS`/`ALERTS_REFRESH_MS` in `Dashboard.html`.

-----

### 🤝 Credit & Acknowledgments

My idea for this Dashboard came from VA3HDL/hamdashboard.

I just rewrote the code with the help of Copilot in VSCode to make this Dashboard the way I like it, local, and ready for the shack now!

-----

### 📜 License

Feel free to fork it, mod it, break it, and fix it. Just don't broadcast spurious emissions.

73s