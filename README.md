<div align="center">
  <h4>Rajendra Bist — Backend-focused Full-Stack Developer</h4>
  <p>Node.js · TypeScript · PostgreSQL · AI-integrated products</p>
</div>

I design systems from the data layer up — validation schemas, API boundaries, and database
integrity before any client-facing flow gets written. Then I prove they hold with tests.

---

**How I work**

- **Make invalid states impossible.** Constraints and row-level security live in Postgres; Zod schemas guard every API boundary. Application code is the second line of defence, not the first.
- **Treat outside systems as untrusted.** LLM output, webhooks and queue events are validated, time-boxed, and fail through one uniform path.
- **Prove it, don't assume it.** Sovereign ships with 100+ automated checks, including cross-tenant read and write attempts that must fail.
- **Measure before optimizing.** A slow page turned out to be database round-trip latency, not code. I measured it, cut the after-idle query cost from ~2 s to ~0.6 s, and measured again.

---

**Live builds**

**[Sovereign](https://github.com/rajendrabist07/sovereign)** · [live →](https://sovereign-saas-platform.vercel.app/)

Multi-tenant workflow platform. Organisations define step-based workflows that run durably in the background, with Postgres row-level security, role-based access control, an append-only audit log, atomic monthly quotas, and a live run timeline. **Status:** the secure core is built and tested; AI-agent steps with schema-validated tool calls and human approval gates are next.

![Next.js](https://img.shields.io/badge/-Next.js_16-18181B?style=flat-square&logo=nextdotjs&logoColor=white) ![React](https://img.shields.io/badge/-React_19-18181B?style=flat-square&logo=react&logoColor=61DAFB) ![TypeScript](https://img.shields.io/badge/-TypeScript-18181B?style=flat-square&logo=typescript&logoColor=3178C6) ![tRPC](https://img.shields.io/badge/-tRPC-18181B?style=flat-square&logo=trpc&logoColor=398CCB) ![Prisma](https://img.shields.io/badge/-Prisma-18181B?style=flat-square&logo=prisma&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-18181B?style=flat-square&logo=postgresql&logoColor=4169E1) ![Clerk](https://img.shields.io/badge/-Clerk-18181B?style=flat-square&logo=clerk&logoColor=white) ![Inngest](https://img.shields.io/badge/-Inngest-18181B?style=flat-square) ![Tailwind CSS](https://img.shields.io/badge/-Tailwind_CSS-18181B?style=flat-square&logo=tailwindcss&logoColor=06B6D4)

**[Chronicle](https://github.com/rajendrabist07/chronicle)** · [live →](https://chronicle-platform.vercel.app/)

Publishing platform with email-verified accounts and Gemini writing tools whose structured output is Zod-validated before it reaches the editor. Server-rendered public pages with ISR, and every push gated by tests. Two services: Next.js on Vercel, Express/Prisma/PostgreSQL on Render.

![Next.js](https://img.shields.io/badge/-Next.js_15-18181B?style=flat-square&logo=nextdotjs&logoColor=white) ![TypeScript](https://img.shields.io/badge/-TypeScript-18181B?style=flat-square&logo=typescript&logoColor=3178C6) ![Express](https://img.shields.io/badge/-Express-18181B?style=flat-square&logo=express&logoColor=white) ![Prisma](https://img.shields.io/badge/-Prisma-18181B?style=flat-square&logo=prisma&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-18181B?style=flat-square&logo=postgresql&logoColor=4169E1) ![Gemini](https://img.shields.io/badge/-Gemini_API-18181B?style=flat-square&logo=googlegemini&logoColor=8E75B2) ![Vitest](https://img.shields.io/badge/-Vitest-18181B?style=flat-square&logo=vitest&logoColor=6E9F18) ![GitHub Actions](https://img.shields.io/badge/-GitHub_Actions-18181B?style=flat-square&logo=githubactions&logoColor=2088FF)

**[DevGuard AI](https://github.com/rajendrabist07/dev-guard-ai)** · [live →](https://dev-guard-ai.vercel.app/)

Autonomous GitHub review agent — AST-level static checks, CVE scanning, test-evidence verification, and multi-model fallback routing so review quality doesn't depend on one LLM being available.

![Next.js](https://img.shields.io/badge/-Next.js_15-18181B?style=flat-square&logo=nextdotjs&logoColor=white) ![TypeScript](https://img.shields.io/badge/-TypeScript-18181B?style=flat-square&logo=typescript&logoColor=3178C6) ![Supabase](https://img.shields.io/badge/-Supabase-18181B?style=flat-square&logo=supabase&logoColor=3FCF8E)

---

**Stack**

**Backend** ![Node.js](https://img.shields.io/badge/-Node.js-18181B?style=flat-square&logo=nodedotjs&logoColor=339933) ![Express](https://img.shields.io/badge/-Express-18181B?style=flat-square&logo=express&logoColor=white) ![TypeScript](https://img.shields.io/badge/-TypeScript-18181B?style=flat-square&logo=typescript&logoColor=3178C6) ![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-18181B?style=flat-square&logo=postgresql&logoColor=4169E1) ![Prisma](https://img.shields.io/badge/-Prisma-18181B?style=flat-square&logo=prisma&logoColor=white) ![tRPC](https://img.shields.io/badge/-tRPC-18181B?style=flat-square&logo=trpc&logoColor=398CCB) ![Zod](https://img.shields.io/badge/-Zod-18181B?style=flat-square&logo=zod&logoColor=3E67B1)

**Frontend** ![Next.js](https://img.shields.io/badge/-Next.js-18181B?style=flat-square&logo=nextdotjs&logoColor=white) ![React](https://img.shields.io/badge/-React-18181B?style=flat-square&logo=react&logoColor=61DAFB) ![Tailwind CSS](https://img.shields.io/badge/-Tailwind_CSS-18181B?style=flat-square&logo=tailwindcss&logoColor=06B6D4)

**Platform** ![Supabase](https://img.shields.io/badge/-Supabase-18181B?style=flat-square&logo=supabase&logoColor=3FCF8E) ![Clerk](https://img.shields.io/badge/-Clerk-18181B?style=flat-square&logo=clerk&logoColor=white) ![Vercel](https://img.shields.io/badge/-Vercel-18181B?style=flat-square&logo=vercel&logoColor=white) ![Render](https://img.shields.io/badge/-Render-18181B?style=flat-square&logo=render&logoColor=46E3B7) ![GitHub Actions](https://img.shields.io/badge/-GitHub_Actions-18181B?style=flat-square&logo=githubactions&logoColor=2088FF) ![Docker](https://img.shields.io/badge/-Docker-18181B?style=flat-square&logo=docker&logoColor=2496ED) ![MongoDB](https://img.shields.io/badge/-MongoDB-18181B?style=flat-square&logo=mongodb&logoColor=47A248)

**Currently learning** — RAG pipeline internals and vector-store tradeoffs, from first principles, not from wrapping an API call. Applying it next in Sovereign.

---

**Open to** backend and full-stack roles (Node.js, TypeScript, PostgreSQL) · full-time

📍 Based in India (IST, UTC+5:30) · Nepali national · onsite or hybrid in India, remote-friendly

🔗 [bistrajendra.com.np](https://www.bistrajendra.com.np/) · 📫 [rajendrabist396@gmail.com](mailto:rajendrabist396@gmail.com) · 💼 [linkedin.com/in/rajendra-bist](https://www.linkedin.com/in/rajendra-bist-169926370/)
