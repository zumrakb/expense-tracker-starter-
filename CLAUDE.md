# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build & Development Commands

- `npm run dev` - Start Vite development server (http://localhost:5173)
- `npm run build` - Build for production (outputs to `dist/`)
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

## Technology Stack

- **React 19** with JSX (no TypeScript)
- **Vite 7** for build tooling
- **ESLint 9** with flat config format

## Architecture

This is a simple expense tracker application. Currently a single monolithic component (`src/App.jsx`) that handles:

- Transaction state management (array of transaction objects)
- Form for adding new transactions
- Summary cards (income, expenses, balance)
- Filtered transaction table

### Transaction Data Structure

```javascript
{
  id: number,           // Date.now()
  description: string,
  amount: string,       // Note: stored as string, causes calculation bugs
  type: "income" | "expense",
  category: string,     // food, housing, utilities, transport, entertainment, salary, other
  date: string          // ISO format (YYYY-MM-DD)
}
```

## Known Issues

This is a starter project intentionally containing bugs for learning purposes:

- Amount stored as string instead of number (causes string concatenation in calculations)
- No delete/edit functionality for transactions
- Single monolithic component needs decomposition
