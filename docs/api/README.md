# API Reference

This directory contains the auto-generated API documentation.

## Generating Documentation

Run TypeDoc to generate the API documentation:

```bash
pnpm docs
```

This will:
1. Parse all TypeScript source files
2. Extract JSDoc comments and type information
3. Generate HTML documentation in this directory

## Manual Reference

### Core Components

#### `client/src/components/`

- **wizard-dialogue-engine.tsx** - Manages dialogue flow and state
- **wizard-option-handler.tsx** - Handles user choices
- **pixel-presence.tsx** - Mascot display and animation
- **asset-browser-wizard.tsx** - Asset selection UI

#### `client/src/hooks/`

- **use-toast.ts** - Toast notifications
- **use-mobile.tsx** - Mobile detection

#### `client/src/lib/`

- **persistence.ts** - State persistence to localStorage
- **utils.ts** - Utility functions

### Shared Types

See `shared/schema.ts` for core type definitions:

```typescript
// User types
interface User {
  id: string;
  username: string;
}

// Lesson types
interface Lesson {
  id: string;
  title: string;
  description: string;
  order: number;
  content: {
    introduction: string;
    steps: Step[];
  };
}

interface Step {
  id: string;
  title: string;
  description: string;
  initialCode: string;
  solution: string;
  hints: string[];
  tests?: any[];
}

// Progress tracking
interface UserProgress {
  id: string;
  userId: string;
  lessonId: string;
  currentStep: number;
  completed: boolean;
}
```

### Server API

#### Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/api/lessons` | List all lessons |
| GET | `/api/lessons/:id` | Get lesson by ID |
| GET | `/api/progress/:userId` | Get user progress |
| POST | `/api/progress` | Update progress |

## Contributing

When adding new components or utilities:

1. Add JSDoc comments to all exports
2. Include `@param` and `@returns` tags
3. Add `@example` blocks for usage
4. Run `pnpm docs` to verify output

Example:

```typescript
/**
 * Formats a number as a score display string.
 * 
 * @param score - The numeric score value
 * @param digits - Minimum digits to display (default: 6)
 * @returns Formatted score string with leading zeros
 * 
 * @example
 * ```typescript
 * formatScore(42);     // "000042"
 * formatScore(1234);   // "001234"
 * formatScore(42, 4);  // "0042"
 * ```
 */
export function formatScore(score: number, digits = 6): string {
  return score.toString().padStart(digits, '0');
}
```
