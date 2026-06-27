========================================================================
             NAS100 Market Replay Simulator - Web Edition
========================================================================
An interactive, responsive HTML5 web-based simulator designed for 
backtesting trading strategies on NAS100 (or MNQ) financial data.
------------------------------------------------------------------------
1. HOW TO LAUNCH AND RUN THE SIMULATOR
------------------------------------------------------------------------
To run the web simulator, you must open it using a web browser. 
* Note on Local API Features (CORS Restrictions):
  Because modern browsers enforce security boundaries (CORS) when loading 
  local files directly via the "file://" protocol, loading the config.txt 
  API key file automatically will be blocked in Google Chrome or Safari 
  if you simply double-click the HTML file.
To run the simulator with full functionality:
Option A: Start a Quick Local HTTP Server (Recommended)
  1. Open a terminal/command prompt in this folder.
  2. Start a Python web server:
     python -m http.server 8000
  3. Open your web browser and go to:
     http://localhost:8000/interactive_web_simulator.html
  4. (This method also allows you to access the simulator on your iPhone 
      by visiting http://<your-computer-ip>:8000/interactive_web_simulator.html)
Option B: Direct Double-Click (Fallback)
  1. Double-click "interactive_web_simulator.html" to open it.
  2. If the API key is not read automatically due to CORS, you can simply 
     paste your Gemini API Key directly into the input field on the startup page.
------------------------------------------------------------------------
2. KEY FEATURES
------------------------------------------------------------------------
* 16:9 Responsive Viewport:
  - Constrained to a crisp 16:9 aspect ratio.
  - Automatically sizes to fit desktops, iPads, or iPhones.
  - On mobile/iPhone layouts, elements intelligently compact and stack for a 
    native app feel.
* Multi-Format CSV Support:
  - Drag-and-drop or select any CSV file.
  - Auto-detects 3 different formats:
    1. Tab-separated NAS100 (with <DATE>, <TIME>, <OPEN>, etc.).
    2. Comma-separated MNQ v1 (with ts_event column).
    3. Comma-separated MNQ v2 (with Date and mixed-case columns).
* 250-Candle Pre-Start Window:
  - Automatically loads 250 bars of historical context before your selected date.
  - Historical bars are drawn dimmed so you can distinguish them from live trading.
  - Trading is blocked until you advance the pointer past the session start line.
* Interactive Click-to-Order System:
  - Click anywhere on the chart canvas to open the placement menu at that price.
  - Place "Limit Buy" (cyan line) or "Stop Loss" (orange line).
  - Unfilled pending orders can be canceled at any time using the floating 
    "Pending Orders" panel in the bottom-right corner.
  - Orders auto-trigger when price action crosses them.
* Close Markers:
  - Closing active positions places a white "X" marker directly on the chart.
* Gemini AI Copilot Integration:
  - Enter your API key on the start page (or pre-fill it via config.txt) to 
    enable real-time market reviews, strategy chats, and performance audit evaluations.
  - If no API key is entered, all AI panels and options are hidden automatically.
