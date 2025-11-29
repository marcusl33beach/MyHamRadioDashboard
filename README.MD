## 📻 MyHamRadioDashboard

### The "Shack-in-a-Browser" Display for the Modern Operator

Welcome to MyHamRadioDashboard\! Because sometimes you want to check propagation conditions, local radar, and solar wind without firing up 15 different browser tabs or buying another Raspberry Pi that you'll definitely configure "someday."

This is a lightweight, single-file HTML dashboard designed to run locally on your machine. It puts the "control" in Mission Control, optimized for Boone County, KY, but ready to be forked for your own QTH.

-----

## 📡 Features (The "Specs")

  * **✨ Propagation Analyst (Powered by Gemini):** A button that calls the Gemini API (using Google Search grounding) to provide a **real-time, tactical summary** of current solar conditions (SFI, K-Index, X-ray flux) and immediate, actionable **band recommendations** for HF/VHF operators.
  * **The 4x3 Grid of Glory:** Displays 12 monitored frequencies... err, images, perfectly sized to your screen. No scrolling required (unless you want to).
  * **Forced Refresh:** All images and maps in the grid are automatically **refreshed every 2 minutes** using cache-busting techniques, ensuring you always see the latest radar loop or space weather conditions.
  * **Zero-Install Deployment:** No Docker containers, no npm install, no compiling kernels. Just download the HTML file and double-click it like it's 1999.
  * **The Stealth Menu:** A stealthy menu button integrated into the ticker bar with helpful ham links, including **HamStudy.org**.
  * **The Ticker of Truth:** A transparent, floating ticker at the bottom that pulls live local weather (temp, wind, chance of rain) based on your set latitude/longitude.
  * **CORS-Fu:** Uses clever workarounds (like direct image generators and public JSON proxies) to try and load external content without making your browser scream about security policies.

-----

## 🛠️ Installation & Usage

This project requires a **Gemini API Key** to enable the **Propagation Analyst** feature.

### 1\. Get Your Key

1.  Obtain a Gemini API key from Google AI Studio.
2.  Follow the instructions there to **enable the Google Search Grounding tool** for your API key/project to ensure real-time data is used for analysis.

### 2\. Prepare the Code

1.  **Clone the Repo:**
    ```bash
    git clone [https://github.com/yourusername/MyHamDashboard.git](https://github.com/yourusername/MyHamDashboard.git)
    ```
2.  **Insert Your Key:** Open the HTML file in a text editor (VS Code recommended). Find the line:
    ```javascript
    const API_KEY = ""; 
    ```
    And paste your Gemini API key inside the quotes.

### 3\. Run It

  * **Method A (The "I just want it to work" method):** Right-click `dashboard.html` -\> Open with Chrome/Edge/Firefox. (Note: Some browsers might restrict API calls when opening local files, Method B is more reliable.)
  * **Method B (The Recommended Method):** Open a terminal in the folder and run a simple HTTP server (e.g., using Python):
    ```bash
    python -m http.server
    ```
    Then, navigate your browser to `http://localhost:8000`.

Enjoy\! Watch the clouds move and the solar x-rays spike.

-----

## 🔧 Customization (Mod Your Rig)

### 1\. Change Location for Weather Ticker

To customize the local weather ticker for your QTH:

  * Open `dashboard.html` in a text editor.

  * Find the `WEATHER TICKER LOGIC` section (around line 620).

  * Update the `LATITUDE` and `LONGITUDE` variables for your precise location:

    ```javascript
    // Coordinates for Boone County, KY (Update this!)
    const LATITUDE = 38.98; 
    const LONGITUDE = -84.77; 
    ```

### 2\. Change Image Content and Titles

To change the content tiles in the 4x3 grid:

  * Find the `DEFINE CONTENT URLs AND TITLES` section (around line 360).

  * Modify the `contentData` array to include your preferred links.

    ```javascript
    const contentData = [
        { url: 'https://radar.weather.gov/ridge/standard/CONUS-LARGE_loop.gif', title: 'CONUS Radar (Large)' }, 
        // ... add or change your links here
    ];
    ```

### 3\. Change Refresh Rate

To change how often the images reload (default is 2 minutes):

  * Find the `IMAGE_REFRESH_RATE_MS` variable and set your desired interval in milliseconds.

    ```javascript
    const IMAGE_REFRESH_RATE_MS = 120000; // 2 minutes
    ```

-----

## 🤝 Credit & Acknowledgments

My idea for this Dashboard came from VA3HDL/hamdashboard.

I just rewrote the code with the help of Gemini in VSCode to make this Dashboard the way I like it—streamlined, local, and ready for the shack—now featuring its own **Gemini Propagation Analyst**\!

-----

## 📜 License

Feel free to fork it, mod it, break it, and fix it. Just don't broadcast spurious emissions.

73