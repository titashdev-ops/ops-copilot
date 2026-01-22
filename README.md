# Ops Copilot

Ops Copilot is a production-grade B2B SaaS platform designed to automate regulatory compliance for businesses.

## What Problem It Solves
Businesses struggle to track compliance obligations across jurisdictions, frequencies, and risk levels. Ops Copilot converts compliance rules into structured tasks, prioritizes high-risk deadlines, and provides AI-assisted guidance to reduce penalties and operational risk.

## Key Features
- Database-driven compliance rules engine
- Automated compliance task generation (12-month horizon)
- Risk-based task prioritization
- AI-generated task explanations and professional email drafts
- Stripe subscription billing (Free / Pro)
- Automated high-risk deadline email reminders
- Admin dashboard for rule and user management

## Architecture Overview
- Frontend: React.js + Tailwind CSS
- Backend: Node.js (Express)
- Database & Auth: Supabase (Postgres, Row Level Security)
- Payments: Stripe Subscriptions
- AI: OpenAI (server-side, cached)
- Email: Resend

- ## Key Design Decisions

- **Database-driven compliance rules**  
  Compliance logic is stored entirely in the database, allowing rules to be added, edited, or disabled without redeploying the application.

- **Idempotent task generation**  
  Compliance tasks are generated in a safe, repeatable manner to prevent duplicate obligations during retries or onboarding restarts.

- **AI cost control**  
  AI-generated insights are cached per task to avoid repeated OpenAI calls and keep usage predictable.

- **Risk-first UX**  
  Tasks are grouped and surfaced by risk level so that high-impact deadlines are never buried.

- **Multi-tenant security**  
  Row Level Security (RLS) enforces strict data isolation between users and organizations.

## Security & Scalability
- Row Level Security (RLS) for multi-tenant isolation
- Server-side authorization for admin and billing logic
- AI response caching to control API costs
- Idempotent background jobs to prevent duplicate tasks

## Status
This is an active, production-oriented SaaS system design and implementation project.
