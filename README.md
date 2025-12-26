# @strata/typescript-tutor

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🏢 Enterprise Context

**Strata** is the Games & Procedural division of the [jbcom enterprise](https://jbcom.github.io). This repository provides an interactive, mascot-driven educational experience for learning TypeScript by building games with [Strata 3D](https://strata.game).

## Features

- 🎓 **Interactive Lessons** - Learn TypeScript by building actual game systems
- 🤖 **Mascot-Driven** - Guided by Professor Pixel, your AI game development tutor
- 🎮 **Game-Based Learning** - Concepts applied immediately to real-time 3D environments
- 🧩 **Modular Structure** - Lessons covering everything from basic types to advanced game architecture

## Getting Started

### Prerequisites

- **Node.js**: >= 20.0.0
- **pnpm**: >= 10.0.0

### Installation

```bash
# Clone the repository
git clone https://github.com/strata-game-library/typescript-tutor.git
cd typescript-tutor

# Install dependencies
pnpm install
```

### Development

```bash
# Start the interactive tutor
pnpm dev
```

The tutor will be available at `http://localhost:5000`.

## Testing

```bash
# Run unit tests
pnpm test

# Run E2E tests (Playwright)
pnpm test:e2e
```

## Structure

- `client/` - React-based interactive lesson UI
- `server/` - Node.js backend for lesson state and asset serving
- `shared/` - Shared schemas and types
- `assets/` - 3D models, textures, and audio used in lessons

## License

MIT © [Jon Bogaty](https://github.com/jbcom)
