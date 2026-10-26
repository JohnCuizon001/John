# Supabase setup

1. Create a Supabase project and open its SQL Editor.
2. Run [`schema.sql`](./schema.sql) to create the `tasks` table and its row-level security policies.
3. In **Authentication → Sign In / Providers**, enable **Anonymous Sign-Ins**. The app uses an anonymous user so each browser gets a private task list without a sign-up screen.
4. Copy `.env.example` to `.env` and set `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` from the project's API settings. Use the publishable key (or legacy anon key); never use a secret or service-role key in the browser.
5. Restart the Vite dev server. The app will load existing cloud tasks and import this browser's saved tasks if the new cloud account has none yet.

If the project is not configured or is temporarily unavailable, the app continues to use browser storage. The status in the top bar shows whether cloud sync is active.
