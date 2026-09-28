# AGENTS.md

Instructions for AI coding agents working in this repo.

## Project
A single-page todo list app. Everything lives in `todo.html` (HTML, CSS and JS inline, no build step, no dependencies).

## Features (source of truth)
- Add a task (button or Enter)
- Tick a task done / undone
- Delete a task
- Filter: all / active / done
- "Clear completed"
- Persist tasks in `localStorage` (wrapped in try/catch)

## How to work
1. Read this file and `todo.html` before changing anything.
2. Pick one item from the Backlog below. Do one item per change.
3. Keep it a single file with no external scripts or network calls.
4. Open `todo.html` in a browser and check the feature by hand, including a reload to confirm persistence.
5. Commit with a short imperative message ("Add due dates"). Move the item from Backlog to Done here in the same commit.

## Conventions
- Plain JavaScript, no frameworks.
- Colours come from the CSS variables in `:root`; support light and dark.
- Use `textContent`, never `innerHTML`, for user-entered text.
- Keep the UI usable at 360px wide.

## Backlog
- [x] Edit a task by double-clicking it
- [x] Due dates and priorities
- [x] Drag to reorder
- [x] Backup / restore as JSON (copy and paste)

## Done
- [x] Core add / complete / delete
- [x] Filters and clear completed
- [x] localStorage persistence
- [x] Published to the web
- [x] Calendar dropdown for due dates

## Do not
- Add a build system or npm dependencies
- Commit secrets or tokens
- Rewrite the whole file to make a small change
