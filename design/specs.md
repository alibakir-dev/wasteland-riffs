# Wasteland Riffs Design Tokens

> This inventory reflects the effective values in the current matte industrial interface.  
> The actual root size is `14px`, so all `rem` conversions use `14px = 1rem`.

## Live design

https://gauge-fiber-37268146.figma.site/

# 1. COLORS (HEX & RGBA)

## Dark Theme — Matte Graphite

| Suggested token | Actual CSS variable | Value | Usage |
|---|---|---:|---|
| `--bg-canvas` | `--bg` | `#111317` | Page background |
| `--bg-surface` | `--panel` | `#181B20` | Cards, header, footer |
| `--bg-elevated` | `--raised` | `#21252D` | Dropdowns, controls, table headers |
| `--border-default` | `--line` | `#2E333D` | Dividers and component borders |
| `--text-primary` | `--text` | `#F3F4F6` | Primary text |
| `--text-muted` | `--muted` | `#9CA3AF` | Secondary text |
| `--accent-primary` | `--amber`, `--amber2` | `#FF5A1F` | Signal-orange actions and indicators |
| `--accent-success` | `--green` | `#10B981` | In-tune and success states |
| `--accent-technical` | `--blue` | `#38BDF8` | Technical badges |
| `--accent-danger` | `--red` | `#DC2626` | Danger state |
| `--surface-wood` | `--wood` | `#3A2419` | Guitar silhouette |

### Dark component colors

| Suggested token | Value | Usage |
|---|---:|---|
| `--amp-surface` | `#14171B` | Amp enclosure |
| `--amp-header` | `#0F1114` | Amp header |
| `--amp-border` | `#303640` | Amp divider |
| `--knob-border` | `#080A0D` | Knob outer border |
| `--knob-surface` | `#1B1F25` | Knob face |
| `--knob-ring` | `#3B424D` | Hard knob outline |
| `--tab-canvas` | `#0C0E11` | TAB runner background |
| `--tab-text` | `#E9E5D9` | TAB notation |
| `--fretboard-surface` | `#241C18` | Fretboard |
| `--fretboard-border` | `#3A3028` | Fretboard perimeter |
| `--fret-wire` | `#AAAAAA` | Vertical frets |
| `--string-color` | `#C9C5AD` | Guitar strings |
| `--meter-tick` | `#59616E` | Tuner gauge marks |
| `--meter-hub` | `#090A09` | Needle hub |
| `--meter-hub-ring` | `#4D5149` | Needle hub border |
| `--readout-surface` | `#10120F` | Tuner frequency readout |
| `--success-label-text` | `#071C14` | Text over green status |
| `--modal-scrim` | `rgba(10, 11, 14, 0.82)` | Command palette overlay |
| `--focus-ring` | `rgba(255, 90, 31, 0.22)` | Input focus outline |
| `--selected-chip` | `#3E2C2B` | 13% orange mixed with elevated surface |
| `--technical-border` | `#3486AD` | 60% technical blue mixed with border |

## Light Theme — Matte Titanium

| Suggested token | Actual CSS variable | Value | Usage |
|---|---|---:|---|
| `--bg-canvas` | `--bg` | `#F3F4F6` | Page background |
| `--bg-surface` | `--panel` | `#FFFFFF` | Cards, header, footer |
| `--bg-elevated` | `--raised` | `#E5E7EB` | Drawers and controls |
| `--border-default` | `--line` | `#D1D5DB` | Dividers and component borders |
| `--text-primary` | `--text` | `#111827` | Primary text |
| `--text-muted` | `--muted` | `#4B5563` | Secondary text |
| `--accent-primary` | `--amber`, `--amber2` | `#EA580C` | Industrial orange |
| `--accent-success` | `--green` | `#047857` | Success and calibration |
| `--accent-technical` | `--blue` | `#0369A1` | Technical badges |
| `--accent-danger` | `--red` | `#DC2626` | Danger state |
| `--surface-wood` | `--wood` | `#7B4A2F` | Guitar silhouette |

### Light computed colors

| Suggested token | Value | Usage |
|---|---:|---|
| `--focus-ring` | `rgba(234, 88, 12, 0.22)` | Input focus outline |
| `--selected-chip` | `#E6D4CE` | 13% orange mixed with elevated surface |
| `--technical-border` | `#5594B8` | 60% technical blue mixed with border |

# 2. TYPOGRAPHY

## Font Families

### Loaded fonts

```css
--font-sans: 'Inter', sans-serif;
--font-mono: 'JetBrains Mono', monospace;
```

- **Inter:** interface, headings, navigation, controls, and body copy.
- **JetBrains Mono:** logo, measurements, technical labels, badges, keyboard hints, tuner readouts, and TAB notation.

### Legacy fallback declarations

Some component declarations still reference:

```css
'Barlow Condensed', sans-serif
'IBM Plex Mono', monospace
Arial, sans-serif
```

Only Inter and JetBrains Mono are imported. Unavailable legacy faces resolve to their generic fallback.

## Root Size

```css
html {
  font-size: 14px;
}
```

## Font Sizes

| Role | Size |
|---|---:|
| Command-palette micro label | `10px / 0.714rem` |
| Calibration micro data, fret note | `11px / 0.786rem` |
| Eyebrows, badges, navigation, buttons, metadata | `12px / 0.857rem` |
| Hero-search input, song secondary copy | `13px / 0.929rem` |
| Default body/UI text, logo | `14px / 1rem` |
| Command input | `15px / 1.071rem` |
| Descriptive body copy, TAB notation | `16px / 1.143rem` |
| Section heading `h2` | `22px / 1.571rem` |
| Song-card heading `h3` | `26px / 1.857rem` |
| Metric value, calibration option, auth logo | `28px / 2rem` |
| Tuner readout, rhythm display, card index | `32px / 2.286rem` |
| Authentication heading | `36px / 2.571rem` |
| Responsive hero minimum | `38px / 2.714rem` |
| Profile heading | `42px / 3rem` |
| Large signal readout | `48px / 3.429rem` |
| Mobile tuner note | `52px / 3.714rem` |
| Tuner note | `64px / 4.571rem` |
| Hero heading maximum | `68px / 4.857rem` |

### Responsive hero heading

```css
font-size: clamp(38px, 5vw, 68px);
```

## Font Weights

| Text style | Weight |
|---|---:|
| Body and normal UI text | `400` |
| Navigation and medium UI labels | `500` |
| Eyebrows, badges, technical labels, readouts | `600` |
| Headings, buttons, logo, active labels | `700` |
| Large tuner note and legacy signal figures | `800` |

## Line Heights

| Text style | Line height |
|---|---:|
| Hero `h1` | `1.02` |
| Descriptive body copy | `1.65` |
| TAB notation | `1.7` |
| Radio/input supporting content | `1.5` |
| Settings supporting copy | `1.5` |
| Other interface text | Browser `normal` |

# 3. SPACING & LAYOUT

## Spacing Scale

| Pixels | Rem | Pixels | Rem |
|---:|---:|---:|---:|
| `2px` | `0.143rem` | `18px` | `1.286rem` |
| `3px` | `0.214rem` | `20px` | `1.429rem` |
| `4px` | `0.286rem` | `22px` | `1.571rem` |
| `5px` | `0.357rem` | `24px` | `1.714rem` |
| `6px` | `0.429rem` | `25px` | `1.786rem` |
| `7px` | `0.5rem` | `26px` | `1.857rem` |
| `8px` | `0.571rem` | `28px` | `2rem` |
| `9px` | `0.643rem` | `30px` | `2.143rem` |
| `10px` | `0.714rem` | `32px` | `2.286rem` |
| `11px` | `0.786rem` | `38px` | `2.714rem` |
| `12px` | `0.857rem` | `40px` | `2.857rem` |
| `13px` | `0.929rem` | `42px` | `3rem` |
| `14px` | `1rem` | `45px` | `3.214rem` |
| `15px` | `1.071rem` | `48px` | `3.429rem` |
| `16px` | `1.143rem` | `50px` | `3.571rem` |
|  |  | `60px` | `4.286rem` |
|  |  | `68px` | `4.857rem` |
|  |  | `72px` | `5.143rem` |
|  |  | `126px` | `9rem` |

## Primary Layout

```css
--layout-max-width: 1320px; /* 94.286rem */
--layout-side-gutter: 24px; /* 1.714rem per side */
```

Desktop:

```css
main {
  width: min(1320px, calc(100% - 48px));
  margin: auto;
  padding: 126px 0 72px;
}
```

Mobile:

```css
main {
  width: min(calc(100% - 28px), 1320px);
  padding: 108px 0 50px;
}
```

## Navigation Layout

| Property | Value |
|---|---:|
| Header height | `68px / 4.857rem` |
| Header horizontal padding | `28px / 2rem` |
| Header gap | `18px / 1.286rem` |
| Search maximum width | `430px / 30.714rem` |
| Search height | `40px / 2.857rem` |
| Navigation tab gap | `18px / 1.286rem` |

## Main Component Padding

| Component | Padding |
|---|---|
| Standard panel/card | `26px / 1.857rem` |
| Song card | `22px / 1.571rem` |
| Filter row | `20px 24px` |
| Metric tile | `20px / 1.429rem` |
| Table row | `12px 18px` |
| Input field | `10px 12px` |
| Standard button | `8px 13px` |
| Toggle button | `9px 15px` |
| Amp control area | `30px 20px` |
| TAB runner | `20px / 1.429rem` |
| Tuner gauge panel | `45px / 3.214rem` |
| Authentication card | `38px / 2.714rem` |
| Mobile authentication card | `25px 18px` |
| Command modal | `10px / 0.714rem` |
| Command result | `13px / 0.929rem` |

## Common Grid Gaps

`4px`, `5px`, `6px`, `8px`, `10px`, `12px`, `14px`, `15px`, `18px`, `20px`, `24px`, `30px`, `50px`

# 4. RADII & BORDERS

## Corner Radii

| Component | Radius |
|---|---:|
| Main cards and panels | `8px / 0.571rem` |
| Authentication card | `8px / 0.571rem` |
| Command modal | `8px / 0.571rem` |
| Dropdown | `8px / 0.571rem` |
| Standard buttons | `6px / 0.429rem` |
| Search and inputs | `6px / 0.429rem` |
| Icon/profile controls | `6px / 0.429rem` |
| Toggle container | `6px / 0.429rem` |
| Toggle options | `4px / 0.286rem` |
| Stamped badge | `4px / 0.286rem` |
| Success status | `4px / 0.286rem` |
| TAB runner | `4px / 0.286rem` |
| Fretboard | `4px / 0.286rem` |
| Keyboard hint | `3px / 0.214rem` |
| Logo emblem | `3px / 0.214rem` |
| Cassette/card header | `7px 7px 0 0` |
| Circular controls and knobs | `50%` |
| Meter and progress tracks | `999px` |
| Semicircular tuner | `320px 320px 0 0` |
| Guitar silhouette | `60% 30%` |

## Borders

Core dark border:

```css
border: 1px solid #2E333D;
```

Core light border:

```css
border: 1px solid #D1D5DB;
```

Accent borders:

```css
/* Dark */
border: 1px solid #FF5A1F;

/* Light */
border: 1px solid #EA580C;
```

### Additional border specifications

| Component | Border |
|---|---|
| Navigation active underline | `2px solid` signal orange |
| Tuner gauge | `2px solid var(--line)`, bottom removed |
| Tuner note badge | `2px solid #10B981` |
| Knob outer border | `3px solid #080A0D` |
| Knob hard ring | `2px #3B424D` via box-shadow |
| Fretboard frets | `3px solid #AAAAAA` |
| Guitar strings | `1px solid #C9C5AD` |
| Fretboard | `1px solid #3A3028` |
| Profile avatar ring | `1px solid` theme accent |
| Technical badge | `1px solid #3486AD` dark / `#5594B8` light |

# 5. SHADOWS & MOTION

## Effective Shadows

The current matte system explicitly removes almost all earlier shadows:

```css
box-shadow: none;
backdrop-filter: none;
```

### Remaining hard-edged rings

| Component | Value |
|---|---|
| Knob milled outline | `0 0 0 2px #3B424D` |
| Dark input focus ring | `0 0 0 2px rgba(255, 90, 31, 0.22)` |
| Light input focus ring | `0 0 0 2px rgba(234, 88, 12, 0.22)` |

There are no active blurry card, button, header, dropdown, or modal drop shadows in the final matte override.

## Transition Durations

| Interaction | Duration | Easing |
|---|---:|---|
| App theme/background transition | `200ms` | Default `ease` |
| Navigation underline | `200ms` | `cubic-bezier(.2, .8, .2, 1)` |
| Navigation color/background/transform | `250ms` | Default `ease` |
| Chips and buttons | `200ms` | Default `ease` |
| Toggle state | `250ms` | Default `ease` |
| Song-card movement | `240ms` | `cubic-bezier(.2, .9, .2, 1)` |
| Song-card border | `180ms` | Default `ease` |
| Knob response | `160ms` | `cubic-bezier(.2, .9, .3, 1)` |
| Command overlay fade | `200ms` | Default `ease` |
| Command modal entrance | `350ms` | `cubic-bezier(.2, .8, .2, 1)` |

## Mechanical Motion Values

| Interaction | Value |
|---|---|
| Card hover | `translateY(-2px)` |
| Button hover | `translateY(-2px)` |
| Button active | `scale(.98)` |
| Knob hover | `scale(1.04)` |
| Knob active | `scale(.96)` |
| Note snap | `scale(1.08)` |
| Logo tick | `translateY(-1px)` |
| Hardware-orb travel | `translateY(-5px)` |

## Animation Timings

| Animation | Timing |
|---|---|
| Logo hardware tick | `2.4s steps(2, end) infinite` |
| Hardware orb | `3s cubic-bezier(.2, .8, .2, 1) infinite` |
| Orbit | `9s linear infinite` |
| Frequency bars | `1.1s steps(6, end) infinite` |
| Fret note snap | `2s steps(2, end) infinite` |
| Tuner needle damping | `3.4s cubic-bezier(.2, .8, .2, 1) infinite` |
| Song-card stagger entrance | `600ms`, delays `80ms` and `160ms` |
| Reduced-motion override | `0.01ms`, one iteration |

## Reduced Motion

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    scroll-behavior: auto !important;
  }
}
```
