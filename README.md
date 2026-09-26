# Connect — Real-Time Multi-User Community Chat

A deployable first production-style version using **Supabase Auth + Postgres + Realtime**.

## What is now real
- Email/password registration and sign-in
- Persistent user profiles in Postgres
- Persistent chat messages in Postgres
- Real-time room messages across browsers/devices
- Real-time online presence
- Public rooms: General, Gaming, Music, Creators, Friends
- Profile display-name updates
- Row Level Security (RLS) policies
- Responsive modern UI

## 1. Create the backend
1. Create a project at Supabase.
2. Open **SQL Editor**.
3. Paste and run `supabase.sql`.
4. In Supabase, go to **Project Settings → API** and copy the Project URL and anon/public key.

## 2. Connect the frontend
Open `app.js` and replace:
```js
const SUPABASE_URL = 'https://YOUR-PROJECT.supabase.co';
const SUPABASE_ANON_KEY = 'YOUR_PUBLIC_ANON_KEY';
```
with your values.

Do **not** put a Supabase service-role/secret key in the browser. Only the public anon key belongs in `app.js`.

## 3. Run locally
Because browsers can restrict modules/assets from `file://`, serve the folder with any static server. For example:
```bash
python3 -m http.server 8080
```
Then open `http://localhost:8080`.

## 4. Deploy
This is a static frontend, so it can be deployed to Netlify, Vercel, Cloudflare Pages, GitHub Pages (with the correct SPA/static setup), or any static host. Supabase supplies the database, authentication and realtime layer.

## 5. Email confirmation
Supabase Auth may require email confirmation depending on your project's Auth settings. Configure the Site URL / Redirect URLs in Supabase Auth settings for your deployed domain.

## Production next steps
- Add password reset and email verification UI
- Add private 1-to-1 conversations
- Add room creation and membership permissions
- Add moderation/report/block tools
- Add message pagination/infinite scroll
- Add rate limiting / abuse protection
- Add image/file uploads via Supabase Storage
- Add unread counts and push/browser notifications
