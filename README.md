# SupportIQ

SupportIQ is an AI-powered customer-support knowledge workspace. This repository is a source-controlled React/Vite starter designed to be extended with Supabase and a server-side AI/RAG endpoint.

## Current starter features
- Responsive dark dashboard with KPI cards and recent activity
- Searchable knowledge article list and category filters
- Support chat prototype with source cards and explicit fallback for unsupported questions
- Feedback controls and unanswered-question queue
- Demo mode so the UI can be explored without credentials

> The included chat uses local demo retrieval and sample data. It is **not** a production RAG system yet. Do not present demo analytics as real usage metrics.

## Stack
- React + TypeScript + Vite
- Tailwind CSS
- Supabase JS client scaffold
- Supabase SQL schema in `supabase/migrations`

## Run locally
1. Install Node.js 20 or newer.
2. Copy `.env.example` to `.env.local`.
3. Install and run:
   ```bash
   npm install
   npm run dev
   ```
4. Open the local URL shown by Vite.

## GitHub
Create a repository named `supportiq`, then from this folder:
```bash
git init
git add .
git commit -m "Initial SupportIQ starter"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/supportiq.git
git push -u origin main
```

## Supabase
1. Create a Supabase project.
2. Open SQL Editor and run the migration at `supabase/migrations/0001_initial_schema.sql`.
3. Set `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` in `.env.local`.
4. Keep the Supabase `service_role` key server-side only; never add it to frontend variables.

## Vercel
Import the GitHub repository into Vercel and set the build command to `npm run build` and output directory to `dist`. Add the two Supabase frontend variables if you have configured Supabase. The UI can also run in demo mode without them.

## Next implementation milestones
1. Add Supabase Auth and role-aware access.
2. Persist articles, conversations, and feedback in Postgres.
3. Add a server-side `/api/chat` endpoint using embeddings + vector retrieval.
4. Require retrieved sources for factual answers; return a clear fallback when evidence is insufficient.
5. Add tests, audit logs, rate limits, and production security review.
