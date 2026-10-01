# AGENTS.md

Instructions for AI coding agents working in this repo.

## Project
A todo list app with accounts. UI, styling and logic live in `index.html` (no build step). Auth and the database are Firebase (Auth + Firestore), loaded via CDN script tags and configured with the `firebaseConfig` object near the top of the script — fill that in with your own Firebase project's keys, see README.md.

## Features (source of truth)
- Add a task (button or Enter)
- Tick a task done / undone
- Delete a task
- Filter: all / active / done
- "Clear completed"
- Sign up / sign in with email+password or Google (Firebase Auth)
- Persist each signed-in user's tasks in Firestore, under `users/{uid}/tasks/{taskId}`

## How to work
1. Read this file and `index.html` before changing anything.
2. Pick one item from the Backlog below. Do one item per change.
3. Keep it a single file with no external scripts or network calls.
4. Serve `index.html` over http/https (not `file://`, Google sign-in needs a real origin) and check the feature by hand, including a reload and a sign-out/sign-in to confirm persistence.
5. Commit with a short imperative message ("Add due dates"). Move the item from Backlog to Done here in the same commit.

## Conventions
- Plain JavaScript, no frameworks.
- Colours come from the CSS variables in `:root`; support light and dark.
- Use `textContent`, never `innerHTML`, for user-entered text.
- Keep the UI usable at 360px wide.

## Backlog
- [ ] Per-task notes / subtasks

## Done
- [x] Core add / complete / delete
- [x] Filters and clear completed
- [x] Published to the web
- [x] Calendar dropdown for due dates
- [x] Edit a task by double-clicking it
- [x] Due dates and priorities
- [x] Drag to reorder
- [x] Backup / restore as JSON (copy and paste)
- [x] Login / signup with email+password and Google, tasks stored in Firestore per account
- [x] Forgot password (email reset link)
- [x] Google sign-in always shows the account picker instead of reusing the last session
- [x] Auth form fields clear on sign-out
- [x] Guest access via anonymous sign-in, no email required, still backed by Firestore
- [x] "Load sample data" button to seed example tasks

## Do not
- Add a build system or npm dependencies
- Commit real Firebase keys to a public repo's commit history if the project is sensitive (this app's keys are meant to be public-safe when Firestore rules are set correctly, but keep the rules strict)
- Rewrite the whole file to make a small change
