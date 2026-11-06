# Technical Preferences

<!-- project.yaml at the repo root is the machine-readable source of truth for
     engine, specialists, naming, performance, platform, and testing.framework.
     This file is the human-readable LEGACY FALLBACK: agents and skills resolve
     each key from project.yaml first and fall back here only when the
     project.yaml key is absent. /setup-engine dual-writes both.
     Forbidden patterns and allowed libraries are NOT migrated — they live only
     in this file. Populated by /setup-engine; updated as decisions are made. -->

## Engine & Language

- **Engine**: Phaser 4.2.1
- **Language**: JavaScript (ES modules), bundled with Vite
- **Rendering**: WebGL (Phaser auto-selects; Canvas fallback). Pixel art: `pixelArt: true`
- **Physics**: Phaser Arcade Physics

## Input & Platform

<!-- Written by /setup-engine. Read by /ux-design, /ux-review, /test-setup, /team-ui, and /dev-story -->
<!-- to scope interaction specs, test helpers, and implementation to the correct input methods. -->

- **Target Platforms**: Web browser (desktop) first; a downloadable wrapper may come later
- **Input Methods**: Keyboard, Gamepad
- **Primary Input**: Keyboard + Gamepad (both first-class)
- **Gamepad Support**: Partial (browser Gamepad API)
- **Touch Support**: None for now
- **Platform Notes**: No hover-only interactions. Browsers block audio until the first click/keypress, so start audio after input. Keep load size small.

## Naming Conventions

- **Classes**: PascalCase (e.g., `PlayerController`)
- **Variables**: camelCase (e.g., `moveSpeed`)
- **Signals/Events**: kebab-case past tense event names (e.g., `'health-changed'`)
- **Files**: PascalCase for classes/scenes (e.g., `Player.js`, `BattleScene.js`), camelCase for modules (e.g., `upgrades.js`)
- **Scenes/Prefabs**: PascalCase Phaser Scene classes ending in `Scene`
- **Constants**: UPPER_SNAKE_CASE (e.g., `MAX_HEALTH`)

## Performance Budgets

- **Target Framerate**: 60 fps
- **Frame Budget**: 16.6 ms
- **Draw Calls**: ~500 (starting default for 2D; revisit once target hardware is known)
- **Memory Ceiling**: 512 MB (browser tab, starting default)

## Testing

- **Framework**: Vitest (logic tests); browser screenshots via Playwright for visual checks
- **Minimum Coverage**: [TO BE CONFIGURED]
- **Required Tests**: Balance formulas, gameplay systems, networking (if applicable)

## Forbidden Patterns

<!-- Add patterns that should never appear in this project's codebase -->
- [None configured yet — add as architectural decisions are made]

## Allowed Libraries / Addons

<!-- Add approved third-party dependencies here -->
- [None configured yet — add as dependencies are approved]

## Architecture Decisions Log

<!-- Quick reference linking to full ADRs in docs/architecture/ -->
- [No ADRs yet — use /architecture-decision to create one]

## Engine Specialists

<!-- Written by /setup-engine when engine is configured. -->
<!-- Read by /code-review, /architecture-decision, /architecture-review, and team skills -->
<!-- to know which specialist to spawn for engine-specific validation. -->

- **Primary**: gameplay-programmer (no Phaser-specific specialist exists)
- **Language/Code Specialist**: gameplay-programmer (all .js game code)
- **Shader Specialist**: technical-artist (WebGL effects, particles)
- **UI Specialist**: ui-programmer (HUD, menus, upgrade picker)
- **Additional Specialists**: ai-programmer (enemy and boss behavior)
- **Routing Notes**: Engine is Phaser, which has no dedicated specialist. Use gameplay-programmer for game code, ai-programmer for enemy/boss AI, ui-programmer for UI, technical-artist for visual effects. Check docs/engine-reference/phaser/ before using Phaser 4 APIs.

### File Extension Routing

<!-- Skills use this table to select the right specialist per file type. -->
<!-- If a row says [TO BE CONFIGURED], fall back to Primary for that file type. -->

| File Extension / Type | Specialist to Spawn |
|-----------------------|---------------------|
| Game code (.js files) | gameplay-programmer |
| Enemy / boss AI | ai-programmer |
| Visual effects / particles | technical-artist |
| UI / HUD / menus | ui-programmer |
| Scene classes (*Scene.js) | gameplay-programmer |
| General architecture review | lead-programmer |
