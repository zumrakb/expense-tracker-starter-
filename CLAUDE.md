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

Expense tracker application with component-based architecture:

- **`App.jsx`** - Root component, manages transactions state
- **`Summary.jsx`** - Displays income, expenses, and balance totals
- **`TransactionForm.jsx`** - Form for adding new transactions (manages own form state)
- **`TransactionList.jsx`** - Displays filtered transaction table (manages own filter state)

### Transaction Data Structure

```javascript
{
  id: number,           // Date.now()
  description: string,
  amount: number,
  type: "income" | "expense",
  category: string,     // food, housing, utilities, transport, entertainment, salary, other
  date: string          // ISO format (YYYY-MM-DD)
}
```

## Known Issues

- No delete/edit functionality for transactions
