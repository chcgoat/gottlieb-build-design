# Gottlieb Build & Design

**Construction Operating System** — the flagship construction platform within the Gottlieb Operating System (GOS) ecosystem.

## Status

📄 **Specification phase.** No application code has been written yet. This repository contains the complete, frozen v1.0 documentation set that governs all future development.

## Start here

**[`/docs/00-Master-Development-Bible`](docs/00-Master-Development-Bible)** is the single source of truth. It consolidates Vision, Architecture, Engineering Standards, UI/UX Standards, Database Design, API Specifications, AI Architecture, 3D Standards, Development Workflow, Release Management, Security, Testing, and the Prompt Library into one document, with cross-references into the full-detail source documents below. Every future build prompt should cite this document's chapter numbers rather than restating requirements.

## Full documentation set

| Doc | Folder | Covers |
|---|---|---|
| — | `00-Master-Development-Bible` | **Start here.** Consolidated single source of truth + Prompt Library |
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
| — | `13-Architecture-Bible` | System Architecture Bible — the five core systems, module communication, event system, notification architecture, AI Gateway contract, Document Generator contract, permission inheritance, mobile backend strategy, plug-in checklist |

**All five documents are frozen as Version 1.0** (tag: `v1.0-docs-full`). Changes go through a controlled revision process — update both the Master Development Bible and its source document in the same PR, never let them drift apart.

## Current recommended build order

1. Design System (theme, typography, icons, layouts, navigation, component library)
2. Authentication, Users, Organizations, Permissions, Language, Notifications
3. Projects, Clients, Vendors, Subcontractors, Documents
4. Estimating, AI, Blueprints, 3D, Material Studio
5. Financial: Invoices, Payments, Reports, Analytics

## Planned repository structure

```text
/docs        — the full documentation set, organized by volume (populated)
/app         — the Next.js application (not yet started)
/packages    — shared UI component library, design tokens, typed API clients
/supabase    — database migrations, RLS policies, seed data, generated types
/scripts     — build, deployment, and data-maintenance scripts
/.github     — GitHub Actions workflows
```

## Core stack

Next.js · React · TypeScript · TailwindCSS · React Three Fiber / Three.js / Drei · Supabase (Postgres, Auth, Storage, Realtime) · Vercel · GitHub Actions

## Non-goals

- No Medical Administration functionality (HIPAA, patient data, clinical workflows) — architecturally isolated forever.
- No custom 3D rendering engine — the 3D Design Studio consumes pre-built Blender GLB assets only.
- No redesign of the existing GOS Document Generator — integrated via API only.
