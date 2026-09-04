# Kannum Kannum

A browser-based webcam gaze game. Face and iris processing stays local in the browser; webcam footage is never uploaded.

## Multiplayer setup

The app supports Supabase Auth and a shared leaderboard. It falls back to local browser storage until Supabase is configured.

1. Create a Supabase project.
2. Run `supabase-schema.sql` in the Supabase SQL editor. Re-run it after updates; it safely creates the shared leaderboard function used by every signed-in player.
3. Enable the Email provider in Supabase Auth. For a classroom demo, email confirmation may be disabled.
4. Copy the project URL and anon key into `supabase-config.js`.
5. Serve the folder from a local server, for example `npx serve .`.

Open the provided `http://localhost:3000` URL. Do not open the HTML directly when testing Auth.

Never put a Supabase service-role key in the frontend. Row Level Security in `supabase-schema.sql` limits score submissions to signed-in users.

The webcam remains local even when multiplayer accounts and leaderboard sync are enabled.
