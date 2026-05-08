# ⚡ Track D — App Builder / SaaS Founder

> Goal: ship a **paid AI SaaS** in 8–12 weeks. Skip credentialism. Optimize for shipping speed, unit economics, and durable moats.

## Profile

You're an indie hacker, founder, or full-stack engineer who wants AI to be your edge — not a hobby. You'd rather have $1k MRR than a wall of certs.

## 8-week ship sprint

### Week 1 · Pick one wedge
- 📓 List 5 painful, recurring tasks your target user does
- 📓 Score each on (a) frequency, (b) data privacy risk, (c) "is an LLM good at this in 2026?"
- 🎯 Pick the highest-scoring one. Resist scope creep.

### Week 2 · MVP build
- 🛠️ Stack: Next.js + Vercel **or** FastAPI + Fly.io
- 🤖 Models: start with **OpenAI GPT-5 mini** or **Claude Haiku 4.5** (cheap + fast); upgrade only when needed
- 🧩 Agent runtime: **OpenAI Agents SDK** for simple, **LangGraph** for stateful, **CrewAI** for role-based
- 📚 RAG: **Pinecone** or **pgvector** (don't roll your own vector DB)
- 🔍 Observability: **Langfuse** (OSS) — instrument from day 1

### Week 3 · MCP + tool integrations
- 🧠 Add 1–3 **MCP servers** that connect to your users' real systems (GitHub, Slack, Linear, Postgres)
- 🔐 Use OAuth from day 1 (no API key copy-paste UX)
- 🏗️ Don't over-engineer multi-agent orchestration until you've shipped single-agent

### Week 4 · Auth, billing, launch page
- 🔐 **Clerk** or **Supabase Auth**
- 💳 **Stripe** with **usage-based billing** if your costs are model-driven
- 🌐 Launch page on **Vercel** with waitlist
- 📨 Plain Markdown changelog → "What we shipped this week"

### Week 5–6 · Closed beta
- 👥 10–20 design partners (don't pay for ads yet)
- 📊 Track: activation, weekly active, model cost per user, churn drivers
- 🧪 Run **evals** (Promptfoo, Langfuse, or hand-rolled) before every prompt change
- 🛡️ Add **content safety** (Azure Content Safety, OpenAI Moderation, or open-source Llama Guard)

### Week 7 · Pricing + polish
- 💰 **Pricing:** start at $20–$49/mo; charge usage-based on top of base
- 📉 Cost-to-serve: aim for < 30% gross margin on inference. Use **Llama 4 on NIM** or **DeepSeek** for non-frontier paths.
- ✨ Polish onboarding: empty states, sample data, "wow moment" within 60 seconds

### Week 8 · Public launch
- 📢 **Product Hunt** + **Hacker News Show HN** + **Reddit** in your niche
- 📨 Email your waitlist
- 🐦 Post a 90-second screen recording on X / LinkedIn
- 🎯 Goal: **$1k MRR** within 30 days of launch

## Tech-decision shortcuts

| Decision | Default | Use the alternative when |
|---|---|---|
| Closed-source LLM | OpenAI GPT-5 mini | You need EU data residency → Mistral or Azure OpenAI EU Data Boundary |
| Open-source LLM | Llama 4 Scout via NIM | You need on-prem → run on your own GPUs |
| Agent framework | OpenAI Agents SDK | Need stateful + durable → LangGraph |
| Vector DB | pgvector (you already have Postgres) | Need scale (>10M vectors) → Qdrant / Pinecone |
| Frontend | Next.js + shadcn/ui | Streaming chat is critical → Vercel AI SDK |
| Hosting | Vercel + Supabase | You need GPUs → Modal, RunPod, fly.io GPU |
| Eval / observability | Langfuse (OSS) | Enterprise compliance → LangSmith / Helicone |
| Auth | Clerk | Open-source preference → Supabase Auth |
| Billing | Stripe + Polar.sh for one-time | B2B SaaS → Stripe usage-based |

## Defensibility checklist

✅ Build moats, not features:
- **Workflow lock-in** — your tool becomes the system of record for X
- **Proprietary data** — opt-in user data becomes training signal
- **Fine-tuned models** — LoRA-tune on your domain, host on Modal
- **MCP integrations** — depth beats breadth
- **Brand + trust** — newsletter, weekly demo, public roadmap

🚫 What's *not* a moat in 2026:
- "Better prompts" — anyone can copy them
- "GPT wrapper UI" — table stakes
- "We use Claude not ChatGPT" — irrelevant to users

## When to certify (later)

Certs aren't priority for builders. Get them after PMF, not before:
- **AI-103 / AIF-C01:** if you're selling enterprise → adds credibility
- **AZ-305 / SAP-C02:** if you target regulated buyers → table stakes
- Skip exec-ed programs entirely; read their reading lists for free

## Reading list

- [Building LLMs in Production](https://www.deeplearning.ai/short-courses/) (DeepLearning.AI series)
- [The Pragmatic Engineer — AI tooling deep-dives](https://newsletter.pragmaticengineer.com/)
- [Latent Space podcast](https://www.latent.space/) — frontier-AI builders
- [a16z AI Canon](https://a16z.com/ai-canon/) — curated foundational reading
- [Eugene Yan's blog](https://eugeneyan.com/) — applied LLM patterns

← [Back to README](../../README.md)
