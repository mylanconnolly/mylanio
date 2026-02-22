---
title: 'PolyGrub'
date: 2026-02-22
summary: 'Scan ingredient labels to identify allergens and dietary restrictions using AI-powered photo analysis with confidence scores and custom category grouping.'
tags:
  - Full-Stack
  - Frontend
---

PolyGrub lets you upload a photo of an ingredient list and uses AI to flag noteworthy ingredients  - dairy, meat, common allergens, or anything else you configure  - with confidence scores and category grouping.

## Key Features

- **Photo scanning**  - upload or capture an ingredient label photo, resized client-side before upload
- **AI ingredient analysis**  - a Supabase Edge Function analyzes photos and returns flagged ingredients with confidence percentages
- **Custom categories**  - create ingredient categories (e.g. "Dairy", "Allergens") with color coding
- **Custom ingredients**  - define specific ingredients to watch for within each category
- **Real-time updates**  - analysis status and results stream in live via Supabase Realtime
- **Re-analyze**  - trigger a new analysis run on any previously uploaded photo

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 16 (App Router) |
| Language | TypeScript 5 (strict mode) |
| UI | React 19, Tailwind CSS 4, Heroicons 2 |
| Auth & Database | Supabase (Auth, Postgres, Storage, Realtime) |
| AI Analysis | Supabase Edge Function (triggered by DB insert) |

## How It Works

Photos are resized client-side, uploaded to Supabase Storage, and a database trigger kicks off an Edge Function for AI analysis. Results stream back to the client in real-time via Supabase Postgres Changes, so you see ingredient matches appear as they're identified.
