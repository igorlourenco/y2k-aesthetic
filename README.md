# y2k-aesthetic

A Claude Code plugin for building frontends with the **Y2K skeuomorphic / AmpCore aesthetic**: glossy metallic surfaces, Winamp-era media player skins, blobject organic shapes, and neon-on-black palettes.

It codifies the design language of early-2000s consumer electronics, media player skins, and concept vehicle dashboards into actionable CSS patterns.

## What it does

- **Design system**: full color tokens, surface recipes (chrome, gel, translucent pod, LCD), and typography for the Y2K era
- **Shape language**: radial-first design rules from the AmpCore study (holdable forms, NURBS-like curves, blobject vs non-blobject modes)
- **Anti-patterns**: knows what ISN'T Y2K (flat design, strict trapezoids, broken radials, listless organic detailing)
- **Component patterns**: Winamp-style players, skin containers, dashboard widgets, jewel-like accessories
- **CSS-only**: all surfaces built with gradients, box-shadows, and clip-paths, with no image dependencies

## Install

### Claude Code

```bash
# Marketplace
/plugin marketplace add igorlourenco/y2k-aesthetic
/plugin install y2k-aesthetic@igorlourenco-y2k-aesthetic
```

Or manually:

```bash
# Personal (all projects)
git clone https://github.com/igorlourenco/y2k-aesthetic.git ~/.claude/skills/y2k-aesthetic

# Per-project (shared via git)
git clone https://github.com/igorlourenco/y2k-aesthetic.git .claude/skills/y2k-aesthetic
```

### OpenAI Codex CLI

```bash
git clone https://github.com/igorlourenco/y2k-aesthetic.git ~/.codex/skills/y2k-aesthetic
```

### Claude.ai

Download the `y2k-aesthetic.skill` file from [Releases](https://github.com/igorlourenco/y2k-aesthetic/releases) and drag it into a Claude.ai conversation.

## Usage

The skill triggers automatically. Just describe what you want:

```
> Build me a Winamp-style music player
```

```
> Create a Y2K dashboard widget for system monitoring
```

```
> Make a landing page with that early 2000s alien media player vibe
```

```
> Build a blobject-shaped podcast player with chrome trim and neon LEDs
```

## Design Principles (from AmpCore study)

1. **It must feel "holdable"**: every UI should feel like a real injection-molded product
2. **Surfaces first, accessories second**: design the shell, then add controls
3. **Radials in abstract**: NURBS-like curves define the shape language
4. **Sharp angles are discouraged**: organic, rounded edges everywhere
5. **Blobject is key, but not the rule**: freeform shells or rounded rectangles, both work

## Credits

Design principles derived from the [AmpCore design study](https://x.com/ApplefatGov/status/2041326711892050052) by [@ApplefatGov](https://x.com/ApplefatGov).

## License

MIT
