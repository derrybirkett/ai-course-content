# Building Apps from PRD Tasks Automatically

**Date:** September 27, 2025

## From PRD to First Commit: Letting Warp + MCP + Linear Build the App (One Ticket at a Time)

In the last video, we used Warp (with an MCP server) connected to Linear to generate a PRD and a full backlog for "Metaprod." Today we actually start building—directly from those Linear tasks—while keeping the agent on a tight leash: one ticket, one sub-task at a time.

## The Flow

1. Pick the first ticket: MSTUDIO-37 — Set up development environment & project structure (part of epic MSTUDIO-36).
2. In Warp, tell the agent to work from Linear: "Build the app following the tasks from Linear, one by one."
3. Enforce clarity: I rejected the first attempt because it wasn't explicit about which ticket it was acting on. New rule: when it picks up a task, it must name the ticket number and sub-task before doing anything.

## What It Actually Built

• Next.js scaffold (app initialized and committed).
• Tailwind CSS configuration (noting potential v3/v4 compatibility quirks).
• Supabase integration setup:
  ○ Created .env.local entries (left empty for safety; I'll paste keys from the Supabase dashboard).
  ○ Server/client config and middleware stubs.
• Playwright test harness (basic config + test folder—no more manual "does it still work?" clicks).
• ESLint + Prettier setup (clean code, consistent formatting).
• Git commits with good messages along the way.
• README draft documenting what was done and how to deploy (targeting Vercel).

## Guardrails That Helped

• Explicit ticketing: "Finish MSTUDIO-37 (all sub-tasks) before moving to any other number. Mark each sub-task as done. Don't proceed without approval."
• Secrets discipline: Supabase keys were created as empty env vars and never printed to the terminal or committed. .env.local stays out of the repo.
• Manual checks: I kept an eye on version mismatches (e.g., Tailwind), and corrected course when needed.

## Where MCP Still Falls Short

• It couldn't move the Linear issue to Done or tick built-in checkboxes via the MCP (at least in my setup). Workaround: I marked them manually in Linear. Good news: It can leave comments on issues, so I had it post a build summary as a proof-of-work trail.

## Takeaways

• Agentic build flows shine when you anchor them to your backlog and enforce "one-ticket focus."
• Give the agent a personality with rules (name the ticket, confirm the sub-task, ask approval between steps).
• Start with infra + testing first (Next.js, Tailwind, Supabase, ESLint/Prettier, Playwright). You'll move faster later.
• Keep humans in the loop for scope, nuance, and status transitions until MCP coverage improves.

Next up, we'll run the remaining tickets in the epic and ship the first deploy to Vercel. Onward.

**Tags:** AI
