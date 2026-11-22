# KEYFORGE 14 — Noir Gold 3D Musical Mechanical Keyboard Game

An interactive, single-file 3D mechanical keyboard & musical rhythm/typing game built in **Three.js**, **GSAP**, and the **Web Audio API**, modeled after the compact **HP Pavilion 14 series (84-key)** layout in a luxury **Obsidian Black & 24K Brushed Gold** dark-mode finish.

---

## Highlights & Gameplay Modes

- **`♪ Melody` (Rhythm Play):** Play 4 built-in musical sequences (*Noir Arpeggio*, *Golden Waltz*, *Crystal Marimba*, *Pavilion Groove*) guided by a **shrinking 3D Cyan → Molten Gold timing ring**, glowing trajectory arc, switch spotlight beam, and live bottom note ribbon with accuracy tracking (`ACC %`).
- **`⚡ Words` (Word Forge):** Type glowing target words (`GOLD`, `FORGE`, `MELODY`, `AURORA`, `SYMPHONY`, `PAVILION`, …) to launch keycaps out of their hinged crystal cases onto the keyboard deck with live **WPM** tracking and word-clear bonuses.
- **`✦ Zen` (Free Studio Play):** Click any crystal glass case or type freely on your physical keyboard with live score, combo, and Fever progression.
- **Progression & Visual Juice:** Live animated **Score & Best tracker**, **Rank progression (`C` → `B` → `A` → `S` → `S+`)**, bouncing **Combo & Multiplier (`×1` → `×8`)**, **Aurum Overdrive (`Fever`)** prismatic keyboard mode, 5-bar audio visualizer, one-click **`✦ Assemble`** symphony wave, and **`Esc` / `↺ Reset`** reverse-order recall.

---

## 3D Hardware & Visual Design

- **HP Pavilion 14 Series (84-Key) Layout:** Compact `16u` 14-inch form factor with numeric keys `1–0` directly beneath `F1–F10`, right-edge navigation column (`DEL`, `HOME`, `PGUP`, `PGDN`, `END`), and stacked half-height `▲`/`▼` arrows flanked by full-height `◀`/`▶`.
- **Black & 24K Gold Finishing:** 6° tilted CNC obsidian brushed-aluminum wedge chassis, 24K brushed gold inner chamfer frame, gold outer waistband, gold-collared rear USB-C port, gold Torx switch plate screws, rubber feet, and **84 metallic gold MX cross stems** with RGB underglow.
- **Unified Curved Crystal Showcase Outlet:** All 84 keycaps start stored inside individual hinged crystal glass cases with 24K gold micro-hinges, framed inside a matching curved-corner obsidian-and-gold showcase vault above the keyboard.
- **Sculpted Artisan Keycaps:** Rounded-corner concave-dish clearcoat keycaps with curved gold double-bezel inlays, self-illuminated champagne-gold legends, jewel-toned micro-accent bars, metallic 24K gold `ESC`/`ENTER` accents, and a golden diamond-soundwave `Spacebar`.

---

## 84-Key Musical Synthesizer Map

Every key layers a synthesized mechanical PBT **thock** with its own distinct musical pitch & instrument voice (harmonically tuned to **D Dorian / F Major** with procedural stereo convolver reverb):

| Key Group | Instrument Voice | Interactive Visual Element |
| :--- | :--- | :--- |
| **QWERTY (`Q–P`)** | Crystal Celesta-Harp (`D4–G5`) | Iridescent Aurora Ripple + rising orbs |
| **Home Row (`A–L`)** | Warm Rhodes Electric Piano (`A3–D5`) | Iridescent Aurora Ripple |
| **Bottom Row (`Z–M`)** | Analog Synth Bass Plucks (`D2–F3`) | Deep Aurora Bass Ripple |
| **Number Row (`1–0`)** | Sparkling Glass Marimba (`A4–E6`) | Dual Concentric Cyan & Gold Shockwave Rings |
| **Function Row (`F1–F12`)** | 12 Ambient Cinematic Synth Chords (`Dm9`, `Fmaj7`, …) | Royal Violet Crown Pulse + Vertical Light Pillar |
| **Arrow Keys (`▲ ▼ ◀ ▶`)** | Rising / Falling / Gliding Synth Arpeggios | Neon Emerald Directional Laser Stream |
| **Spacebar** | Deep `D2` 808 Sub Boom + Fifth Shimmer | Full-Row Golden Horizon Wave |
| **Enter** | Rolled `Dadd9` Harp Strum + Tactile Click | 24K Gold Solar Flare + Vertical Light Pillar |
| **Modifiers (`Ctrl`, `Shift`, `Alt`, `Tab`, `Caps`, `Bksp`)** | Studio Lo-Fi Percussion Kit (Kicks, Snares, Hats, Clave, Brush) | Rose-Magenta Surge Ripple |
| **Nav & Punctuation** | Crystal Chimes & Music Box Plucks | Crystal Teal Diamond Pulse & Gold Sparks |
| **Esc** | Recall Bell Chime | Crimson-Gold Reverse Recall Cascade |

---

## Tech Stack & Tools Used

### Core Web & 3D Graphics Stack
| Technology / API | Version / Details | Role in Project |
| :--- | :--- | :--- |
| **HTML5 / CSS3 / Vanilla ES6+ JavaScript** | Single self-contained `index.html` | Zero-build, zero-dependency standalone web application |
| **Three.js** | `r128` (via cdnjs) | Real-time WebGL 3D rendering, PBR materials, shadows, raycasting, `CatmullRomCurve3` trajectories |
| **GSAP (GreenSock Animation Platform)** | `3.12.2` (via cdnjs) | Staggered intro choreography, hinged lid animations, spring lift/snap physics, HUD tweening |
| **WebGL PBR & Procedural Textures** | `MeshPhysicalMaterial`, `MeshStandardMaterial`, `PMREMGenerator`, `CanvasTexture` | Brushed obsidian/gold textures, softbox studio reflection environment map, 2048×1280 84-key legend atlas |
| **GPU Instancing & Custom Shader Hook** | `THREE.InstancedMesh`, `InstancedBufferAttribute`, `onBeforeCompile` | Renders all 84 switches, keycap bases, atlas-mapped legends, and glass cases at 60 FPS, swapping to individual meshes only while animating |
| **Web Audio API** | Procedural Synthesizer + Stereo `ConvolverNode` + `DynamicsCompressorNode` | 100% synthesized mechanical thock, 84 unique musical key voices, harmonic fanfares, and stereo studio reverb (no external audio files) |
| **Custom Manual Orbit Controls** | Spherical damped camera controller | Left-drag orbit, right/Shift-drag pan, scroll & pinch zoom, smooth target nudges |
| **CSS3 Glassmorphism UI** | `backdrop-filter`, CSS custom properties, tabular numerals | Clean dark-mode Noir Gold HUD, 3-mode switcher, live note ribbon, equalizer bars, floating 3D-projected judgements |

### Development, Testing & Production Tools
| Tool | Role |
| :--- | :--- |
| **Python 3 + `http.server`** | Local static development server for live preview |
| **Playwright + Google Chrome (GPU Direct3D11 / ANGLE)** | Automated browser verification, 0-console-error checks, and deterministic frame-stepped 1080p 60 FPS capture |
| **FFmpeg 9 (`libx264` / `aac`)** | High-bitrate 1920×1080 @ 60 FPS cinematic showcase mastering, subtle optical motion blur, and filmic color grading |
| **NumPy** | Procedural 48 kHz stereo soundtrack & beat-synced foley generation for demo trailers |
| **Git & GitHub CLI (`gh`)** | Version control, repository creation, and publishing |

---

## Quick Start

1. **Zero-setup run:** Open `index.html` directly in any modern browser (Chrome, Edge, Safari, or Firefox) with internet access (for Three.js & GSAP cdnjs scripts).
2. **Or serve locally:**
   ```bash
   python -m http.server 8099
   ```
   Then open `http://localhost:8099`.

### Controls
- **Click any crystal case** or **type on your physical keyboard** to install and play keys.
- **Left-drag** to orbit · **Right-drag / `Shift` + drag** to pan · **Scroll / Pinch** to zoom.
- **`✦ Assemble`** installs all remaining keys in a musical wave · **`Esc` / `↺ Reset`** returns all installed keys in reverse order.

---

## License

MIT License — see [LICENSE](LICENSE) for details.
