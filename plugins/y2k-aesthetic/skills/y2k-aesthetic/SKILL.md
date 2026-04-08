---
name: y2k-aesthetic
description: Build frontends with the Y2K skeuomorphic / AmpCore aesthetic — glossy metallic surfaces, Winamp-era media player skins, alien/cyber organic shapes, neon-on-black palettes, and early-2000s digital maximalism. Use this skill whenever the user asks for Y2K, AmpCore, retro-futuristic, Winamp skin, early 2000s, skeuomorphic, cyber, blobject, or media-player-inspired UI. Also trigger when the user references glossy/chrome/metallic interfaces, alien-organic shapes, NURBS-style curves, or that "2003 desktop customization" vibe. Works for dashboards, music players, widgets, landing pages, or any UI that should look like it belongs on a teenager's Windows XP desktop circa 2003.
---

# Y2K / AmpCore Skeuomorphic Aesthetic

Build interfaces that channel the golden era of desktop customization and physical product design: Winamp skins, concept vehicle dashboards, Sony Walkman pods, Nokia handsets, Skannerz toys, and blobject consumer electronics — all rendered in CSS.

## Core Design Philosophy

This aesthetic simulates **manufactured physical objects on screen**. Every UI must feel like a real product you could pick up and hold. The test: *"Could I imagine this as an injection-molded plastic object in my hand?"* If yes, you're on track.

### The Five Rules (from AmpCore study)

**1. It must feel "holdable."**
Imagine holding the UI in your hand. Even if the shape is wild, it must feel like an actual material with surface, shading, lighting, and implied thickness. Flat designs with abstract lighting that only implies direction (not form) fail this test.

**2. Surfaces first, accessories second.**
Design the main body/shell first — the primary radial surface. Then add buttons, screens, LEDs, and decorative elements on top of it. Never start with the controls.

**3. Shape language is Radials in Abstract.**
The design revolves around NURBS-like shapes — abstract curves and bends that follow an inner/outer radial flow. Shapes often attempt to converge into their opposite silhouette. Simple circles are fine, but the magic is in asymmetric organic curves that still feel resolved.

**4. Sharp angles are heavily discouraged.**
Almost everything should have rounded, organic edges. Rectangles and cubes must have rounded corners to fit the flow. The only exception is when sharp angles serve a specific functional purpose (like a screen bezel).

**5. Blobject is key, but not the rule.**
Most designs are abstracted blobject/NURBS shapes. But rounded rectangles and simpler forms are OK when the object has its own functional gimmick or abstractness. The blobject rules the *shell*; the internals can be more geometric.

### Radial Design Rules

The radial is the most important structural concept:

- **Every design needs at least one radial** — a dominant curved flow that defines the shell's silhouette
- **Accessories can go against the radial** (buttons, knobs, antenna) as long as the radial is clearly present underneath
- **Multiple radial sets are OK** as long as there's a decent separator between them (a groove, inset line, or material change)
- **Never break the radial and venture too far** — if elements (like a button row) stray from the main curve, they must still resolve their edges back to it cleanly
- **Implied radials work** — you can suggest the curve through early-termination of lines and using insets rather than outsets

### Two Design Modes

**Blobject-ruled:** The outer shell IS a blob — freeform organic NURBS shape. Think Sony bean-shaped Walkman, iMac G3, alien media players. The screen and controls are inset into the organic form.

**Non-blobject-ruled:** More rectangular/geometric overall, but with heavy rounding, subtle curves, and organic details. Think Nokia phones, Skannerz toys, rugged portable devices. The radial is present in edge treatment and surface contours rather than the silhouette.

## Visual Implementation

### Mandatory Elements

1. **Pure black background** (`#000000`) — the skin floats in void, like a product photo
2. **Glossy/metallic surfaces** — layered CSS gradients simulating chrome, brushed metal, or translucent plastic gel
3. **Neon accent palette** — toxic green, electric blue, hot purple, warning amber
4. **Deep shadows and glows** — colored `box-shadow` layers for depth; never flat
5. **Organic/alien shapes** — blobs, asymmetric curves via `border-radius` with mixed values, `clip-path`, SVG masks
6. **Pixel-precise details** — 1px bevels, inset grooves, tiny LED indicators, segmented displays
7. **Jewel-like accessories** — buttons and accents that feel hi-fashion, precious, like polished gems or chrome knobs on a luxury device

### Color System

```css
:root {
  --y2k-black: #000000;
  --y2k-dark: #0a0a0a;
  --y2k-panel: #1a1a2e;

  /* Chrome/metal gradient stops */
  --y2k-chrome-light: #e8e8e8;
  --y2k-chrome-mid: #888888;
  --y2k-chrome-dark: #333333;
  --y2k-chrome-shadow: #111111;

  /* Neon accents */
  --y2k-green: #39FF14;
  --y2k-green-dim: #1a8a0a;
  --y2k-blue: #00BFFF;
  --y2k-blue-dim: #005f7f;
  --y2k-purple: #BF00FF;
  --y2k-amber: #FFB300;
  --y2k-red: #FF1744;

  /* Translucent gel */
  --y2k-gel-green: rgba(57, 255, 20, 0.3);
  --y2k-gel-blue: rgba(0, 191, 255, 0.25);
}
```

### Surface Recipes

**Chrome/brushed metal panel:**
```css
background: linear-gradient(
  160deg,
  #ccc 0%, #999 15%, #666 30%, #888 50%,
  #555 70%, #777 85%, #aaa 100%
);
border: 1px solid #444;
box-shadow:
  inset 0 1px 0 rgba(255,255,255,0.3),
  inset 0 -1px 0 rgba(0,0,0,0.4),
  0 4px 20px rgba(0,0,0,0.8);
```

**Glossy gel button (jewel-like):**
```css
background: radial-gradient(
  ellipse at 35% 25%,
  rgba(150, 255, 150, 0.9) 0%,
  rgba(57, 255, 20, 0.7) 30%,
  rgba(20, 120, 10, 0.9) 70%,
  rgba(5, 40, 2, 1) 100%
);
border: 2px solid rgba(57, 255, 20, 0.5);
box-shadow:
  inset 0 2px 4px rgba(255,255,255,0.4),
  inset 0 -2px 4px rgba(0,0,0,0.6),
  0 0 15px rgba(57, 255, 20, 0.4);
border-radius: 50%;
```

**Translucent alien pod surface:**
```css
background: linear-gradient(
  135deg,
  rgba(0, 191, 255, 0.15) 0%,
  rgba(0, 100, 180, 0.25) 50%,
  rgba(0, 40, 80, 0.4) 100%
);
border: 1px solid rgba(0, 191, 255, 0.3);
box-shadow:
  0 0 20px rgba(0, 191, 255, 0.2),
  inset 0 0 30px rgba(0, 191, 255, 0.05);
border-radius: 40% 60% 55% 45% / 50% 40% 60% 50%;
backdrop-filter: blur(4px);
```

**LCD / segmented display (inset screen):**
```css
background: #0a1a0a;
border: 2px inset #333;
color: #39FF14;
font-family: 'Courier New', monospace;
text-shadow: 0 0 8px rgba(57, 255, 20, 0.8);
letter-spacing: 2px;
box-shadow: inset 0 0 10px rgba(0,0,0,0.8);
```

### Typography

- **Labels/controls**: `'Trebuchet MS'`, `'Tahoma'`, `'Verdana'` — actual Y2K system fonts. Uppercase, tight letter-spacing, 10-12px.
- **LCD readouts**: `'Courier New'`, monospace, green-on-black glow
- **Chrome embossed text**:
  ```css
  text-shadow:
    0 1px 0 #ccc, 0 2px 0 #bbb,
    0 3px 0 #999, 0 4px 0 #888,
    0 5px 5px rgba(0,0,0,0.4);
  ```

### Shape Construction

**Building the radial shell:**
1. Start with an asymmetric `border-radius`: `border-radius: 30% 70% 60% 40% / 50% 30% 70% 50%;`
2. Or use `clip-path: ellipse()` / SVG `<path>` for more complex NURBS-like silhouettes
3. Add implied thickness via gradient shading — lighter on top-left (light source), darker on bottom-right
4. Surface should feel like it has curvature in 3D, not just a 2D blob outline

**Adding accessories on top:**
- Circular jewel buttons with `radial-gradient` for gem-like depth
- Small LED indicators (6-8px circles with colored `box-shadow` glow)
- Grooves and ridges via 1px `inset` borders or `box-shadow` pairs (light + dark)
- Antenna, fins, or protruding bumps as `::before`/`::after` pseudo-elements
- Accessories should feel like separate attached pieces, not painted on

**Separation techniques:**
- Inset grooves (dark line + lighter line below) to mark zones
- Material changes (chrome section → matte section)
- Early line termination — a groove that doesn't go all the way across implies the radial continues underneath

### Animation Patterns

- **LED blink**: `animation: blink 1.5s step-start infinite;`
- **Subtle pulse glow**: oscillate `box-shadow` spread on accent elements
- **Scan-line sweep**: semi-transparent gradient that `translateX` across a display
- **Visualizer bars**: staggered `animation-delay` on vertical bars with random heights
- Keep animations functional — they indicate "alive/active" state

### Layout Principles

1. **Float in the void** — components on `#000` with generous space; no full-width sections
2. **Product-shot composition** — center or slightly off-center, like a product render
3. **Layered depth** — elements overlap slightly; `z-index` stacking
4. **Compact control clusters** — small, dense button groups like real hardware
5. **Decorative chrome trim** — non-functional ridges, vents, screws as visual detail
6. **Fixed-size skins** — not fluid/responsive; these are objects with defined proportions

### Component Patterns

**Skin-style container (blobject-ruled):**
- Organic outer shell shape (SVG path or complex border-radius)
- 1-2px bevel/ridge border following the radial
- Inset "screen" area (dark recessed rectangle with rounded corners)
- Jewel button cluster following the body's curve
- Status LEDs and decorative antenna/fins

**Player widget (non-blobject-ruled):**
- Rounded rectangle body with heavy border-radius
- Chrome bezel frame with gradient shading
- Transport buttons as glossy gems
- EQ visualizer bars
- Seek bar with metallic track + glowing knob
- Playlist as dark inset list

## What IS NOT This Aesthetic

These anti-patterns come directly from the AmpCore study. Memorize them:

1. **Listless or organic line detailing** — if a shape is translucent, simplicity and separation is key. Don't make it look "alive" or biological. Products tended to subdue inner mechanics with curfed sections.

2. **Not holdable** — if the shading only implies abstract lighting direction but not form/surface, it fails. It shouldn't read as "a bunch of disparate rounded rectangles mashed together." Each section must feel resolved into the whole.

3. **Strict simple trapezoids** — sharp geometric shapes (trapezoids, hexagons) that don't feel holdable or comfortable. Using sci-fi shapes with random analog switches feels listless, not AmpCore.

4. **Breaking the radial too far** — buttons or accessories that are haphazardly connected to the outer shape without resolving their edges cleanly back to the radial.

5. **Flat design, modern minimalism** — no flat cards on white backgrounds, no pastel palettes, no sans-serif minimalism.

6. **Generic component libraries** — no shadcn, no Material Design. Everything is bespoke.

## Implementation Notes

- Build as a **single HTML or React file** — inline all styles
- Use CSS custom properties for the color system
- Prefer CSS gradients and shadows over images — keep it self-contained
- Inline SVG for complex shell shapes or visualizer graphics
- For React: `useState` for interactive elements (play/pause, sliders)
- Black background fills entire viewport/container
- Don't use `<marquee>` — animate with CSS `translateX` keyframes
- When designing, sketch the radial flow first (mentally), then build the shell, then add accessories

### Inspirations Reference

**Stylistic**: Y2K, Blobject, Sci-fi anime, Metalheart
**Physical products**: Concept vehicles, stereos/music players, toy design, pre-iPhone cellphones/beepers, Luigi Colani designs, biomorphic shapes
**Digital**: Winamp/WMP/AIMP skins, custom Windows themes, NURBS-style CG, abstract techno/breaks/trance music video aesthetics, Japanese biomorphic design
