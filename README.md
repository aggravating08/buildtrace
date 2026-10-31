# BuildTrace

**Keep the fix, not just the ticket.** BuildTrace is a private engineering memory for debugging sessions, technical decisions, and reusable lessons. It is a new, solo-built project for the Appwrite Databases Hackathon.

## What it does

- Capture each engineering trace with the symptom, fix, and lesson.
- Search title, project, problem, fix, lesson, and tags; filter by type or project.
- Star useful fixes, expand the full trace, and add an optional reference URL.
- Store each trace in Appwrite TablesDB with row-level security. Each anonymous session can read, update, and delete only its own records.
- Fall back to clearly labeled local preview mode if Appwrite is unavailable. Fictional sample traces are never presented as synced data.

## Live demo

[Watch the 2-minute demo](https://aggravating08.github.io/buildtrace/demo.mp4) or [open BuildTrace](https://aggravating08.github.io/buildtrace/). The demo connects to a free Appwrite TablesDB project by default. It creates an anonymous session in your browser; records you add are scoped to that session and are not visible to other visitors.

## Technology and privacy

- HTML, CSS, and JavaScript with Appwrite Web SDK 29.0.0.
- Appwrite TablesDB `listRows`, `createRow`, `updateRow`, and `deleteRow`.
- No server API key is embedded in the browser. The endpoint, project ID, database ID, and table ID are public identifiers.
- The database uses the serverless TablesDB option. The demo was set up in Appwrite's Free organization without a payment method or paid database tier.

## Run locally

Open `index.html` in a modern browser or serve this folder with any static web server. To connect your own Appwrite project, add your hostname as a Web platform, enable anonymous sign-in, create a TablesDB database and a `traces` table, then enter the project IDs in **Connect Appwrite**. The table needs text columns `title`, `project`, `kind`, `problem`, `fix`, `lesson`, `tags`, `url`, `ownerId`, a datetime column `loggedAt`, and a boolean column `starred`. Enable row-level security and allow authenticated users to create rows.

## Demo production

The demo video uses a synthetic narration voice and on-screen captions. The recording shows a fictional debugging trace created for demonstration; no personal or production data is included.
