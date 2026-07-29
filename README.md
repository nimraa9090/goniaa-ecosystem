<div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:0F172A,100:1E3A8A&height=140&section=header&text=Goniaa&fontSize=48&fontColor=ffffff&fontAlignY=55&desc=AI-Powered%20Fashion%20E-Commerce%20Ecosystem&descAlignY=80&descSize=16" width="100%"/>

<p>
  <img src="https://img.shields.io/badge/status-in%20production-2ea44f?style=flat-square" />
  <img src="https://img.shields.io/badge/role-founder%20%26%20solo%20developer-0F172A?style=flat-square" />
  <img src="https://img.shields.io/badge/next.js-15-000000?style=flat-square&logo=nextdotjs&logoColor=white" />
  <img src="https://img.shields.io/badge/typescript-strict-3178C6?style=flat-square&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/supabase-postgres-3ECF8E?style=flat-square&logo=supabase&logoColor=white" />
  <img src="https://img.shields.io/badge/expo-SDK%2054-000020?style=flat-square&logo=expo&logoColor=white" />
</p>

<p>
  <a href="https://goniaapk.vercel.app/"><img src="https://img.shields.io/badge/🌐_Live_Website-Visit-1E3A8A?style=for-the-badge" /></a>
  <a href="#"><img src="https://img.shields.io/badge/📱_Mobile_APK-Download-1E3A8A?style=for-the-badge" /></a>
  <a href="#"><img src="https://img.shields.io/badge/🎥_Video_Demo-Watch-1E3A8A?style=for-the-badge" /></a>
  <a href="https://github.com/nimraa9090"><img src="https://img.shields.io/badge/💻_GitHub-Profile-1E3A8A?style=for-the-badge" /></a>
</p>

</div>

---

## Overview

**Goniaa** is a fashion e-commerce ecosystem I designed, built, and operate as founder and solo developer — a public storefront, an AI-powered internal Brand Manager dashboard, and a native mobile app, all shipped to production.

This is not a tutorial project or a clone: it's a real, live business with real customers, real inventory, and real operational decisions running through software I built end to end — product, design, frontend, backend, mobile, and AI integration.

> **Note:** This is a public showcase repository documenting the architecture, engineering decisions, and outcomes of the Goniaa platform. Production source code remains in a private repository.

---

## System Overview

Goniaa is composed of three applications sharing a single Supabase backend:

| Component | Description | Stack |
|---|---|---|
| **Storefront** | Public-facing store where customers browse and purchase | Next.js 15, TypeScript, Vercel |
| **Brand Manager Dashboard** | Internal 11-tab operations console — analytics, inventory, content, and AI-assisted decisions | Next.js 15, TypeScript, Groq API |
| **Mobile App** | Companion mobile experience | React Native, Expo SDK 54 |
| **Backend** | Shared data layer: auth, database, storage | Supabase (Postgres) |
| **AI Layer** | LLM-powered insights and content assistance inside the dashboard | Groq API — Llama 3.3 70B Versatile |

```
                         ┌─────────────────────┐
                         │      Supabase        │
                         │  (Postgres · Auth ·   │
                         │      Storage)         │
                         └───────────┬───────────┘
                 ┌───────────────────┼───────────────────┐
                 │                   │                   │
        ┌────────▼────────┐ ┌────────▼────────┐ ┌────────▼────────┐
        │    Storefront     │ │  Brand Manager   │ │   Mobile App     │
        │   (Next.js 15)     │ │  Dashboard (11    │ │ (React Native +  │
        │                    │ │  tabs, Groq LLM)  │ │   Expo SDK 54)   │
        └────────────────────┘ └────────────────────┘ └────────────────┘
```

---

## Engineering Highlights

Real problems solved while building and operating Goniaa in production:

- **Built an 11-tab AI dashboard from scratch** — analytics, inventory, content, and operations tooling, integrated with the Groq API for AI-assisted brand decisions.
- **Diagnosed and eliminated a production-blocking React error (`recharts` #130)** by replacing the third-party charting library with custom, dependency-free CSS charts — removing an entire class of runtime crashes.
- **Root-caused a recurring `CSSStyleDeclaration` crash** traced to JSX spread operators inside style props, and resolved it by refactoring to reusable, strongly-typed styled components across the dashboard.
- **Fixed a Supabase auth misconfiguration** and replaced deprecated dependencies that were silently breaking builds.
- **Debugged NativeWind styling inconsistencies** across iOS/Android in the React Native mobile app.
- **Ran a brand-consistency audit** on the live storefront, catching a luxury-vs-affordable positioning contradiction and inconsistent brand naming before they reached more customers.

---

## Tech Stack

**Frontend:** Next.js 15 · TypeScript · React · TailwindCSS
**Mobile:** React Native · Expo SDK 54 · NativeWind
**Backend:** Supabase (Postgres, Auth, Storage)
**AI:** Groq API (Llama 3.3 70B Versatile)
**Infra:** Vercel · GitHub Actions

---

## Folder Structure

```
goniaa-ecosystem/
├── apps/
│   ├── storefront/            # Next.js 15 public storefront
│   │   ├── app/                # App Router routes
│   │   ├── components/         # UI components
│   │   ├── lib/                 # Supabase client, utils
│   │   └── public/
│   ├── dashboard/              # Brand Manager (11-tab admin console)
│   │   ├── app/
│   │   │   ├── (tabs)/          # analytics, inventory, content, etc.
│   │   │   └── api/             # Route handlers, Groq integration
│   │   ├── components/
│   │   ├── lib/
│   │   │   ├── ai/               # Groq client + prompt logic
│   │   │   └── supabase/
│   │   └── types/
│   └── mobile/                  # React Native + Expo app
│       ├── app/                  # Expo Router
│       ├── components/
│       └── lib/
├── packages/
│   ├── ui/                       # Shared design system components
│   ├── config/                   # Shared TS/ESLint/Tailwind config
│   └── types/                    # Shared TypeScript types
├── supabase/
│   ├── migrations/
│   └── seed/
├── docs/
│   ├── architecture.md
│   └── decisions/                # Lightweight ADRs
└── README.md
```

---

## Screenshots

### 🛠️ Admin Screenshots
<p align="center">
  <img src="https://github.com/user-attachments/assets/0cc764c6-da68-44ce-ada4-ae9f65d2a977" width="100%" />
  <img src="https://github.com/user-attachments/assets/8a2b82b1-6db7-4506-a4d3-63ca66b41311" width="100%" />
  <img src="https://github.com/user-attachments/assets/8eeda243-5d52-4a0e-9331-9b957498943b" width="100%" />
  <img src="https://github.com/user-attachments/assets/d18356db-ae19-4fb2-8705-f04d2edf7cfc" width="100%" />
  <img src="https://github.com/user-attachments/assets/591d1ba5-5341-4c62-a561-9072e695fa4a" width="100%" />
  <img src="https://github.com/user-attachments/assets/6214a599-9b69-4bf6-bbf5-26c7a4741d8c" width="100%" />
</p>

### 🤖 Brand Manager Screenshots
<p align="center">
  <img src="https://github.com/user-attachments/assets/22dabf19-9f00-46f4-bac2-1d2bcb172166" width="100%" />
  <img src="https://github.com/user-attachments/assets/3758537c-6331-4980-a245-015a12d13f22" width="100%" />
  <img src="https://github.com/user-attachments/assets/88fd89ce-6ae2-4a1b-be12-9c410a774c0e" width="100%" />
  <img src="https://github.com/user-attachments/assets/2bd6c9d2-5de9-49f5-8649-6b3ad8505ac4" width="100%" />
  <img src="https://github.com/user-attachments/assets/8a6945e8-41d6-4bd4-ad08-bc81e0c00fa3" width="100%" />
  <img src="https://github.com/user-attachments/assets/0d02f274-1a12-4ba6-8fc3-3912f7ffa721" width="100%" />
  <img src="https://github.com/user-attachments/assets/a3880585-b758-4200-86f6-28893a6b0030" width="100%" />
  <img src="https://github.com/user-attachments/assets/d690de1f-964b-4380-b043-d987a4fce398" width="100%" />
  <img src="https://github.com/user-attachments/assets/715f3351-3d77-4f96-acfa-6745cbbd4824" width="100%" />
  <img src="https://github.com/user-attachments/assets/564fce12-b93f-4d0d-b167-ab33f2f9594c" width="100%" />
  <img src="https://github.com/user-attachments/assets/18e0a66b-8f8c-471e-8167-32ac306e9ccd" width="100%" />
</p>

### 🛒 Storefront Preview
<p align="center">
  <img src="https://github.com/user-attachments/assets/54c007a6-6169-4783-b30b-6bb37884104c" width="100%" />
  <img src="https://github.com/user-attachments/assets/cfb8e46b-3198-46b2-bb25-477e64e0f8b4" width="100%" />
  <img src="https://github.com/user-attachments/assets/aa296579-9a77-44c2-99b1-f5a7d70026f2" width="100%" />
  <img src="https://github.com/user-attachments/assets/959982f1-6964-4584-8597-7f3f5d388de8" width="100%" />
  <img src="https://github.com/user-attachments/assets/b4c05fcd-4287-4918-b2c5-a4b14f0736bc" width="100%" />
  <img src="https://github.com/user-attachments/assets/f35f7bfc-d789-472d-954f-96471bf7d3bf" width="100%" />
  <img src="https://github.com/user-attachments/assets/e35119e8-9553-4c2a-9c82-2468ca9d9f3a" width="100%" />
</p>
---

## Roadmap

- [ ] Public mobile app release (App Store / Play Store)
- [ ] Expand AI Brand Manager with automated inventory forecasting
- [ ] Add role-based access for a small internal team
- [ ] Performance pass on storefront Core Web Vitals

---

## Author

**Nimra** — Founder & Solo Developer, Goniaa
BS Artificial Intelligence, Hazara University (Expected 2027)

[Portfolio](#) · [GitHub](https://github.com/nimraa9090) · [LinkedIn](#)
