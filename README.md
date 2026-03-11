# ⚔️ PixelSkies — 8-Bit Weather App

> A retro pixel-art weather app for Milwaukee, WI. Built as a single HTML file with zero dependencies.

![PixelSkies Preview](https://img.shields.io/badge/style-8--bit-yellow?style=flat-square) ![HTML](https://img.shields.io/badge/built%20with-HTML%2FJS%2FCSS-blue?style=flat-square) ![No deps](https://img.shields.io/badge/dependencies-none-green?style=flat-square)

---

## 🎮 Features

- **Animated 8-bit weather scenes** drawn entirely on an HTML Canvas — thunderstorms with flickering lightning, falling rain, drifting snowflakes, a rotating sun with rays, and rain/snow mix
- **Animated pixel knight** in the bottom-left of each scene who reacts to the weather:
  - ⛈ Storm / 🌧 Rain — raises a red shield overhead to block the rain
  - ☀️ Sunny — armor off, pants only, sunglasses on, waving
  - ❄️ Snow — full armor, arms crossed, shivering with icicles on his helmet
  - ⛅ Cloudy — hand raised over visor, scanning the sky
  - 🌨 Rain/Snow — hunched with blue shield angled overhead
- **Real Milwaukee forecast data** (NWS) baked in — current conditions, 5-day outlook, and hourly timeline
- **Light & Dark mode** toggle in the status bar, with weather-appropriate sky gradients for both themes
- **4 screens**: Home, Radar Map, Weather Alerts, Settings
- **°F / °C toggle** with live conversion across all values
- **No dependencies** — pure HTML, CSS, and vanilla JavaScript. One file, runs anywhere.

---

## 🚀 Getting Started

No build step. No npm. Just open the file.

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/pixelskies.git

# Open in your browser
open pixelskies/pixelweather-app.html
```

Or host it instantly with **GitHub Pages**:

1. Go to your repo **Settings → Pages**
2. Set source to `main` branch, `/ (root)`
3. Your app will be live at `https://YOUR_USERNAME.github.io/pixelskies/pixelweather-app.html`

---

## 📱 Screens

| Screen | Description |
|--------|-------------|
| **Home** | Full-width animated canvas, current temp, hourly strip, 5-day cards, stat grid |
| **Map** | Pixel terrain radar map of the Milwaukee metro area with city pins |
| **Alerts** | Live NWS-sourced weather alerts with severity badges |
| **Settings** | Theme toggle, temp units, notification preferences, location info |

---

## 🎨 Tech Details

| Thing | How |
|-------|-----|
| Pixel art | HTML5 Canvas API, drawn pixel-by-pixel at 8px grid scale |
| Knight sprites | Separate 3px scale helper (`kp()`), anchored to canvas bottom-left |
| Animation | `requestAnimationFrame` loop with a `tick` counter driving rain, snow, lightning flicker, and knight animations |
| Theming | CSS custom properties (`--var`) toggled via a `.light` body class |
| Fonts | [Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P) + [VT323](https://fonts.google.com/specimen/VT323) via Google Fonts |

---

## 📍 Weather Data

Weather data reflects real Milwaukee, WI conditions sourced from the **National Weather Service (NWS)** for the week of March 11, 2026. To update the forecast, edit the `TODAY`, `DAYS`, and `HOURS` constants in the `<script>` section of `pixelweather-app.html`.

To connect live data, swap those constants with a fetch call to the [NWS API](https://www.weather.gov/documentation/services-web-api):

```js
const res = await fetch('https://api.weather.gov/gridpoints/MKX/90,65/forecast');
const data = await res.json();
```

---

## 📁 File Structure

```
pixelskies/
├── pixelweather-app.html   # The entire app — one self-contained file
└── README.md               # This file
```

---

## 🛠 Customization

**Change the city** — update the `▸ MILWAUKEE, WI` string and the `TODAY` / `DAYS` data constants.

**Add a new weather type** — add a `bgXxx()` background function, a `knightXxx()` sprite function, a case in `drawScene()`, and an entry in `emojiMap`.

**Change the knight's colors** — edit the color constants (`K`, `KD`, `KL`, `SKIN`, etc.) at the top of each knight function.

---

## 📜 License

MIT — do whatever you want with it.
