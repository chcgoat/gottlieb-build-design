# Gottlieb Build & Design

**Construction Operating System** — the flagship construction platform within the Gottlieb Operating System (GOS) ecosystem.

## Status

📄 **Specification phase.** No application code has been written yet. This repository currently contains the complete Master Product Requirements Document (PRD) that will govern all future development.

## /docs — Master PRD

The PRD is organized into ten volumes, each in its own folder:

| Volume | Folder | Covers |
|---|---|---|
| I | `01-Executive` | Project charter, vision, scope boundaries |
| II | `02-Brand` | Visual identity, design philosophy, design system |
| III | `03-Architecture` | System architecture, technology stack, environments |
| IV | `04-Database` | PostgreSQL schema, ER diagrams, relationships, indexes |
| V | `05-Permissions` | Role-based access control and Row Level Security model |
| VI | `06-Modules` | Functional specification for every application module |
| VII | `07-AI` | AI Estimating, Blueprint Intelligence, AI Assistant strategy |
| VIII | `08-3D` | 3D Design Studio, GLB pipeline, material configurator |
| IX | `09-API` | REST API design, authentication, webhooks, integration layer |
| X | `10-Roadmap` | Technical, module, AI, UI, database, and release roadmaps |
| — | `11-Engineering-Standards` | Engineering Standards Manual — folder structure, naming, component/database/Supabase conventions, GitHub workflow, testing, performance, security, AI coding standards |
| — | `12-Design-Bible` | Complete UI/UX Design System — brand application, typography, iconography, grid, navigation, role dashboards, Design Studio, Material Studio, portal experiences, mobile, components, motion, accessibility, i18n/RTL |
| — | `13-Architecture-Bible` | System Architecture Bible — the five core systems (GOS Core, Build & Design, Document Generator, future Medical OS, AI Services), module communication, event system, notification architecture, AI Gateway contract, Document Generator contract, permission inheritance, mobile backend strategy, plug-in checklist for future modules |

Read **Volume I** first — it explains how to use the rest of the document set. Read **11-Engineering-Standards** before writing any code. Read **12-Design-Bible** before designing or building any screen. Read **13-Architecture-Bible** before wiring any module to another.

**PRD, Engineering Standards, Design Bible, and Architecture Bible are frozen as Version 1.0** — the four foundational documents. Changes go through a controlled revision process, not ad hoc rewrites.

**Current recommended build order** (per Architecture Bible Ch. 12, supersedes PRD Vol. X pending formal revision):
1. Design System (theme, typography, icons, layouts, navigation, component library)
2. Authentication, Users, Organizations, Permissions, Language, Notifications
3. Projects, Clients, Vendors, Subcontractors, Documents
4. Estimating, AI, Blueprints, 3D, Material Studio
5. Financial: Invoices, Payments, Reports, Analytics

## Planned repository structure

```text
/docs        — this PRD, organized by volume (populated)
/app         — the Next.js application (not yet started)
/packages    — shared UI component library, design tokens, typed API clients
/supabase    — database migrations, RLS policies, seed data, generated types
/scripts     — build, deployment, and data-maintenance scripts
/.github     — GitHub Actions workflows
```

## Core stack (see Volume III for full detail)

Next.js · React · TypeScript · TailwindCSS · React Three Fiber / Three.js / Drei · Supabase (Postgres, Auth, Storage, Realtime) · Vercel · GitHub Actions

## Non-goals

- No Medical Administration functionality (HIPAA, patient data, clinical workflows) — architecturally isolated, see Volume I §2.4.
- No custom 3D rendering engine — the 3D Design Studio consumes pre-built Blender GLB assets, see Volume VIII.
- No redesign of the existing GOS Document Generator — integrated via API only, see Volume IX.
