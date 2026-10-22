# Workspace Rules

## Privacy Principles
- No network request ever carries user data.
- Raw transactions live in memory only; never store them in localStorage.
- Never commit real statements; use generated fake data and add statement files to .gitignore.
- Plain-language privacy page.

## Coding Rules
- Pure functions in `/lib` (parse, categorize, stats), each with tests.
- Money as integer paise, never floats.
- Small files, one responsibility; no new dependency without asking first.
- After each step: run tests, lint, and build.
- Commit after every working step.

## Module Rules
- `parse`: input `File`, output `Transaction[]` or typed error (`WRONG_FILE`, `PASSWORD_REQUIRED`, `UNSUPPORTED_LAYOUT`).
- `categorize`: pure, keyword map in one data file, easy to extend.
- `stats`: pure, takes `Transaction[]`, returns plain objects that cards render.
- UI never parses; parsers never touch the DOM.
