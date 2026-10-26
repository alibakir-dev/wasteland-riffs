# ROADMAP: Wasteland Riffs (v1.0.0)

High-performance, matte industrial audio studio and guitar companion application.
Built with **React 19, TypeScript, Tailwind CSS, Vite, Web Audio API, and Framer Motion**.

---

## 1. Scope Decisions & Tech Stack

| Topic                 | Decision                                                                                                         |
| --------------------- | ---------------------------------------------------------------------------------------------------------------- |
| **Frontend Stack**    | React 19 + TypeScript + Vite (Lightning-fast HMR, strict type safety)                                            |
| **Styling**           | Tailwind CSS + CSS Custom Properties (Matte tokens, 14px root size, dark/light themes)                           |
| **Motion & Audio UI** | Framer Motion (spring physics, layout morphs, mechanical rotary dials, 60fps tuner needle)                       |
| **Audio Processing**  | Web Audio API + AudioContext (Pitch detection via YIN/Autocorrelation, synthetic tones, audio interface routing) |
| **Database & Auth**   | Supabase (PostgreSQL) for user practice telemetry, gear locker, and custom song data                             |
| **Branding Policy**   | ZERO "AI" buzzwords. Strictly framed as a precision sound lab and telemetry workstation                          |
| **Hosting**           | Vercel (Production)                                                                                              |

---

## 2. Design System Tokens (from Figma Inspection)

- **Root Font Size:** `14px` (`1rem = 14px`)
- **Theme 1 (Dark - Matte Graphite):**
  - Canvas: `#111317`
  - Panel/Surface: `#181B20`
  - Elevated/Controls: `#21252D`
  - Border: `#2E333D`
  - Signal Orange Accent: `#FF5A1F`
  - In-Tune Green: `#10B981`
  - Tech Blue: `#38BDF8`
- **Theme 2 (Light - Matte Titanium):**
  - Canvas: `#F3F4F6`
  - Panel/Surface: `#FFFFFF`
  - Elevated/Controls: `#E5E7EB`
  - Border: `#D1D5DB`
  - Industrial Orange: `#EA580C`
  - Success Green: `#047857`
- **Typography:** `Inter` (UI/Headings), `JetBrains Mono` (Readouts, TAB, Badges, Tuner frequencies)
- **Max Container:** `1320px` with `24px` side gutters.

---

## 3. Milestones

### M0: Repository Bootstrap & Design Tokens Engine
- **Goal:** Set up clean Vite + React + TS project, configure Tailwind with the exact 14px root and Figma matte tokens, and set up Git hygiene.
- **Done when:**
  - Vite dev server runs without warnings.
  - Dark and Light theme CSS variables toggle cleanly via `data-theme` attribute.
  - JetBrains Mono and Inter load locally or via Google Fonts without layout shift.

### M1: Shell, Navigation & Theme System
- **Goal:** Build the top flush navigation bar (`68px`), search capsule with `Cmd+K` trigger, sliding tab indicators, theme switcher, and Profile avatar menu.
- **Done when:**
  - Header is responsive (desktop 1320px container, mobile drawer).
  - Search command palette modal opens with smooth spring animation on `Cmd+K`.
  - Theme toggle switches between Matte Graphite and Matte Titanium instantly.

### M2: Vibe Finder (Discovery Engine) & Master Repertoire
- **Goal:** Build Screen 1 (Vibe Finder matrix) and Screen 2 (Advanced sortable Repertoire table & card archive).
- **Done when:**
  - Filter matrix (Vibes, Rig Mode, Tuning, Skill) filters song recommendations in real time.
  - Repertoire table supports multi-sorting (A-Z, Artist, Duration, BPM, Mastery Level).
  - Song cards support 3D hover tilt and audio preview waveforms.

### M3: Web Audio Engine & Precision Studio Tuner
- **Goal:** Screen 4 (Dedicated analog/digital hybrid tuner with Web Audio API).
- **Done when:**
  - Mic and Audio Interface (Hi-Z USB) input streams can be selected.
  - Real-time pitch detection (Autocorrelation) tracks frequency (Hz) and note (e.g. E2).
  - Semicircular needle swings with 60fps spring damping and locks on Studio Green when in tune.
  - Reference tones play on string click for all alternate tunings (Drop D, DADGAD, Eb, Drop C).

### M4: Song Workbench (Tone Lab & Interactive TAB Runner)
- **Goal:** Screen 3 (Full practice station with Electric Amp/FX and Acoustic Strum/Capo modes).
- **Done when:**
  - Electric Mode: Rotary knobs for Amp EQ (Gain, Bass, Treble, Presence) and 3 stompboxes with clickable toggle switches.
  - Acoustic Mode: Strumming rhythm arrows and fingerpicking diagrams render accurately.
  - Interactive TAB runner auto-scrolls with adjustable speed (0.5x, 0.75x, 1x) and loop markers.
  - Interactive 6-string fretboard highlights notes and scale intervals in real time.

### M5: Practice Vault & Telemetry Analytics
- **Goal:** Screen 5 (Session logger and data visualization).
- **Done when:**
  - Top metric tiles display total practice hours, day streaks, and mastered riffs.
  - Practice history chart renders responsive SVG line graphs.
  - New Session form logs song, artist, duration, technique, and field notes.

### M6: Profile, Gear Locker & Hardware Settings
- **Goal:** Screen 6 (Profile & Virtual Guitar Rack) and Screen 7 (Settings & Calibration).
- **Done when:**
  - User can register guitars with custom default tunings and string gauges.
  - Amp & stompbox tone presets can be saved and loaded with one click.
  - Pitch calibration toggles seamlessly between 440 Hz and 432 Hz.

### M7: Backend Integration (Supabase & Auth)
- **Goal:** Screen 8 (Studio Access / Auth) and cloud sync for telemetry.
- **Done when:**
  - User can sign in, register, or proceed in offline LocalStorage mode.
  - Practice logs and gear locker persist to PostgreSQL via Supabase.

### M8: Performance, A11y & Deployment
- **Goal:** Production polish, keyboard navigation, Lighthouse audit, and deployment on Vercel.
- **Done when:**
  - Lighthouse scores: 95+ across Performance, Accessibility, Best Practices, and SEO.
  - `prefers-reduced-motion` completely disables heavy animations.
  - Live on custom domain via Vercel.