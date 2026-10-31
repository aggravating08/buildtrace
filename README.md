# BuildTrace

**Keep the fix, not just the ticket.** BuildTrace is a private engineering memory for debugging sessions, technical decisions, and lessons that should be reusable. It is a new solo project built for the Appwrite Databases Hackathon.

## What it does

- Capture an engineering trace with the symptom, fix, and the lesson to keep.
- Search by title, project, problem, fix, lesson, and tags; filter by trace type or project.
- Star useful fixes, expand the full trace, and add an optional reference URL.
- Keep notes in this browser for a local preview, or connect Appwrite TablesDB for private, account-scoped persistence.
- The initial sample traces are fictional examples and are clearly labeled as sample data. They are not stored in Appwrite.

## Run

Open `index.html` in a modern browser or serve this folder with any static web server. There is no build step. The Appwrite Web SDK loads from the official jsDelivr CDN.

## Live demo

Try [BuildTrace on GitHub Pages](https://aggravating08.github.io/buildtrace/). The public demo opens in clearly labeled local-preview mode with fictional examples. It does not connect to a live Appwrite database until you configure your own project using the steps below.

## Connect Appwrite TablesDB

1. Create an Appwrite Cloud project and add your app's hostname as a Web platform.
2. Enable anonymous sign-in in the Appwrite project's Auth settings.
3. Create a TablesDB database and a `traces` table with row-level security enabled.
4. Add text columns named `title`, `project`, `kind`, `problem`, `fix`, `lesson`, `tags`, `url`, `ownerId`, a datetime column `loggedAt`, and a boolean column `starred`.
5. Allow authenticated users to create rows. BuildTrace creates an anonymous session and assigns each row read/update/delete permissions for that session's user ID.
6. In BuildTrace, choose **Connect a database** and enter the endpoint, project ID, database ID, and table ID. These are public project identifiers. No server API key is used or required in the browser.

The app uses Appwrite TablesDB `listRows`, `createRow`, `updateRow`, and `deleteRow`. When Appwrite is not configured, the app stays in local preview mode and labels that state; it never presents local data as synced database data.

## Stack

- HTML, CSS, and JavaScript
- Appwrite Web SDK 29.0.0
- Appwrite TablesDB

## Submission demo notes

Show the setup panel and explain that sample content is fictional. A live Appwrite demonstration requires a project/database configured as described above. Do not record private notes, API keys, or account data in the public demo.
