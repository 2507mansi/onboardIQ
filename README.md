# OnboardIQ

A job simulator for onboarding and recruiting. Built for the Buildathon brief "The Job Simulator for AI-Native Freshers" (RFS 20).

Companies load their processes (SOPs, docs, KT recordings) into a knowledge base. New hires learn each workflow through a guided click-through of a mirrored app, then prove it once in a test run. Recruiters can use the same workflows as a scored assessment.

This is a frontend MVP with dummy data (a fictional company, "Northwind Labs", and a Product Manager role). Nothing here is a real company system.

## Run locally

Needs Python 3. On a Mac, double-click `start.command`, or run:

    python3 -m http.server 5173

Then open http://localhost:5173 in Chrome or Edge. Use localhost, not a file path, or the microphone is blocked.

## What is in the MVP
- Employee card with role, manager, org ID, and a full org chart
- Role map of workflows (BAU, ad-hoc, KPI) with progress
- Workflow page: end result, sign-offs, context, stakeholders, task timeline, watch-outs, flag-an-update
- Simulation: mirrored app window, avatar agent with pause/play, subtitles, guided walkthrough, first-run test with scoring
- Applicant mode (no hints, scored) and Admin mode (add knowledge, comments inbox, scores)

## Next steps (not built)
- Claude API to turn SOPs and transcripts into workflow records
- ElevenLabs for voiceover and agent voice
- Descope for admin, employee and applicant roles
- Postgres for workflows, comments and scores
- Apify and CrustData to populate a real company's public information

To connect an agent backend, set `CFG.agentUrl` in `index.html`. The page POSTs `{question, workflow, lang}` and expects `{text, audioUrl?}`. Keep API keys on the server.

## Structure
    index.html      the whole app (HTML, CSS, JS)
    start.command   one-click local server for macOS
