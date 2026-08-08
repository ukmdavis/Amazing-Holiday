# Holiday Planner

A small site for tracking holidays: flights, accommodation, and a day-by-day
countdown of tasks and notes in the run-up to departure. Includes a
"surprise" mode that hides a trip's details behind a countdown until a
reveal date — built for the Germany birthday trip.

## Stack

- **Plain HTML/CSS/JS** — no build step, easy to read and extend
- **Supabase** — free hosted Postgres database + auto-generated API
- **GitHub Pages** — free static hosting straight from this repo

## 1. Create the database (Supabase)

1. Go to [supabase.com](https://supabase.com) and sign up free, create a new project.
2. Once it's ready, open **SQL Editor** → **New query**.
3. Paste in the entire contents of `schema.sql` from this repo and click **Run**.
   This creates the `holidays`, `flights`, `stays`, and `day_items` tables.
4. Go to **Project Settings → API**. Copy the **Project URL** and the
   **anon public** key.
5. Open `js/config.js` in this repo and paste them in:
   ```js
   const SUPABASE_URL = "https://xxxxx.supabase.co";
   const SUPABASE_ANON_KEY = "eyJ...";
   ```

## 2. Push to GitHub

1. Create a new repository on GitHub (e.g. `holiday-planner`).
2. Upload all the files in this folder, keeping the folder structure
   (`css/`, `js/`, `index.html`, `trip.html`, `schema.sql`).
3. Commit and push.

## 3. Turn on GitHub Pages

1. In your repo, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to "Deploy from a branch".
3. Choose the `main` branch and `/ (root)` folder. Save.
4. GitHub gives you a live URL, something like:
   `https://yourusername.github.io/holiday-planner/`
5. It usually takes a minute or two to go live.

## Using it

- **Home page** — add a holiday with name, destination, and dates. Tick
  "This is a surprise" to lock the trip page behind a countdown to a reveal
  date/time you choose — perfect for a birthday reveal.
- **Trip page** — add flights and accommodation, and use the day-by-day
  timeline (running from today up to departure) to add tasks (checkable)
  or notes for any day.

## Notes on security

The Supabase anon key is visible in your public code, and the database
policies currently allow anyone with the link to read and write. That's
fine for a private link you only share with family, but don't post the
GitHub Pages URL publicly. If you want a passcode gate later, that's a
quick addition — just ask.

## Extending it

This is intentionally simple so you can keep building on it. Ideas:
- A packing list per trip
- A budget/spend tracker
- Weather widget pulling from a free API
- A simple login so only your family can access it
