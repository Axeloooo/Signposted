# Free hosting: Vercel, Render and Neon

No card and no domain needed: the web app on Vercel Hobby, the API on Render Free, the database on Neon
Free and the model on a free Groq key. The repo side is done (`render.yaml`, `apps/web/vercel.json`,
Postgres URL handling); the account steps below are yours.

## What you do

1. **Groq.** Create a free key at console.groq.com (no card).
2. **Neon.** Create a project named `signposted`, then copy its connection string
   (`postgresql://...neon.tech/neondb?sslmode=require`). Paste it as is; the API switches it to the
   psycopg driver itself, and creates its tables at startup.
3. **Render.** Install the Render GitHub app on this repo, then _New > Blueprint_ and pick the repo. It reads
   `render.yaml` and creates the `signposted-api` service (Python, free plan, health check `/health`). When
   it asks for the secret values, paste:
   - `DATABASE_URL`: the Neon string from step 2
   - `GROQ_API_KEY`: the key from step 1
4. **Vercel.** Install the Vercel GitHub app on this repo, _Add New > Project_, pick the repo and set the
   _Root Directory_ to `apps/web`. The framework, build command and output directory come from `vercel.json`.
   Add no environment variables: `VITE_*` values are public.
5. **Check the API address.** Render names the service `https://signposted-api.onrender.com` unless that is
   taken. If yours differs, edit the `destination` of the `/api/:path*` rewrite in `apps/web/vercel.json`
   and push.
6. **Deploy from `main`.** Render and Vercel both track `main`, so a release is the deploy.

Open the Vercel URL and plan a trip. The first request after a quiet spell takes about a minute while Render
wakes up (and Neon resumes).

## How it fits together

- `vercel.json` rewrites `/api/*` to the Render service with the prefix stripped, so the browser only talks to
  one origin and needs no CORS setup. Planning does not hold a request open: `POST /trips` answers 202 at once
  and the UI polls progress. To call Render directly instead, build the web app with
  `VITE_API_URL=https://signposted-api.onrender.com` and set `CORS_ORIGINS=https://<your-app>.vercel.app`
  on Render.
- One trip makes several Groq calls (research, itinerary, budget, reviewer, up to two review rounds). The
  free key is rate limited (check console.groq.com/settings/limits); if it bites, set
  `GROQ_MODEL=llama-3.1-8b-instant` on Render.
- Trips still `planning` when the service restarts are marked failed at startup, which also happens each
  time Render wakes from sleep mid-plan.
- Render sets `PORT`; `render.yaml` and the Dockerfile both listen on it (Dockerfile falls back to 8000).
- Never add a card to Neon, Render or Groq: the free tiers cannot bill you.
- The API has no authentication or rate limiting yet. With a free key the worst abuse is using up the daily
  Groq quota.
