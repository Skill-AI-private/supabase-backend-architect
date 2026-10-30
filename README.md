<div align="center">

# Supabase Backend Architect (`supabase-backend-architect`)

**PostgreSQL Relational Schemas, Row Level Security (RLS) & Next.js SSR Cookie Authentication**  
*The Production-Grade Database & Backend Security Standard for AI Coding Agents.*

[![Version](https://img.shields.io/badge/version-1.0.0-18181B.svg?style=flat-square&labelColor=09090B)](https://github.com/Skill-AI-private/supabase-backend-architect)
[![Supabase](https://img.shields.io/badge/Supabase-Supported-18181B.svg?style=flat-square&labelColor=09090B)](https://supabase.com)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15%2B-18181B.svg?style=flat-square&labelColor=09090B)](https://postgresql.org)
[![Harnesses](https://img.shields.io/badge/compatibility-Antigravity%20|%20Claude%20Code%20|%20Cursor%20|%20Copilot-18181B.svg?style=flat-square&labelColor=09090B)](https://github.com/Skill-AI-private/supabase-backend-architect)
[![License](https://img.shields.io/badge/license-MIT-18181B.svg?style=flat-square&labelColor=09090B)](LICENSE)

<br/>

```text
==========================================================================================
                 SUPABASE BACKEND ARCHITECT ARCHITECTURE MATRIX
==========================================================================================

  [01] NORMALIZED POSTGRESQL SCHEMA MODELING
       +-- Relational integrity with UUID primary keys and cascading foreign keys
       +-- Targeted B-Tree indexing on frequently queried foreign key relationships
       +-- Automated timestamps, update triggers, and database-level check constraints

  [02] MANDATORY ROW LEVEL SECURITY (RLS)
       +-- Iron Rule: Zero unprotected tables in production (ALTER TABLE ... ENABLE RLS)
       +-- Granular CRUD policies using authenticated role and auth.uid() boundaries
       +-- Security Definer trigger functions for automated user profile instantiation

  [03] NEXT.JS SSR COOKIE-BASED SESSION ARCHITECTURE
       +-- Official `@supabase/ssr` package implementation (zero deprecated auth-helpers)
       +-- Separation of Server Component (read-only) and Server Action (read-write) clients
       +-- Automated session refresh via Next.js Edge Middleware
==========================================================================================
```

</div>

---

## Technical Specifications

`supabase-backend-architect` enforces strict relational schema design and database-level security policies. It guarantees that multi-tenant web applications never leak private records through missing authorization checks.

### Core Disciplines

* **Mandatory RLS Enforcement:** Prohibits table creation without accompanying Row Level Security activation and explicit authorization policies.
* **Modern SSR Cookie Client:** Exclusively utilizes `@supabase/ssr` with segregated client factories for Server Components, Server Actions, and Middleware.
* **Database Normalization:** Enforces data integrity at the database layer rather than relying solely on client-side application logic.

---

## Installation

### Windows (PowerShell)
```powershell
git clone https://github.com/Skill-AI-private/supabase-backend-architect.git "$HOME\.gemini\config\skills\supabase-backend-architect"
```

### macOS & Linux (Bash)
```bash
git clone https://github.com/Skill-AI-private/supabase-backend-architect.git ~/.gemini/config/skills/supabase-backend-architect
```

---

## Directory Structure

```text
supabase-backend-architect/
|-- SKILL.md                                           # Core Backend & Security Rules
|-- README.md                                          # Technical specification
`-- references/                                        # Progressive disclosure playbooks
    |-- 01-schema-design-and-rls-security.md          # PostgreSQL schemas & RLS policies
    |-- 02-auth-flows-and-ssr-cookies.md               # Next.js @supabase/ssr setup
    `-- 03-edge-functions-and-realtime.md              # Edge functions & live websockets
```

---

<div align="center">

*Engineered for autonomous software agents within the Skill-AI-private suite.*

</div>
