# VISTAR

![Next.js](https://img.shields.io/badge/Next.js-15-black?logo=next.js)
![Supabase](https://img.shields.io/badge/Supabase-Database%20%26%20Auth-3ECF8E?logo=supabase)
![Stripe](https://img.shields.io/badge/Stripe-Payments-635BFF?logo=stripe)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-Styling-38B2AC?logo=tailwind-css)
![TypeScript](https://img.shields.io/badge/TypeScript-Strict-3178C6?logo=typescript)

**VISTAR** is a premium, high-end B2B platform designed to connect ambitious startups with elite corporate service providers. It acts as a matchmaking marketplace where businesses can discover vetted professionals, purchase credits, and securely contact providers for specialized corporate services across various jurisdictions.

---

## ✨ Key Features

- **Role-Based Workflows**: Tailored experiences for Clients, Providers, and Administrators.
- **Provider Discovery & Filtering**: Clients can filter corporate service providers by jurisdiction, service type, and ratings.
- **Credit-Based Lead System**: Clients purchase platform credits via Stripe, which are spent to unlock secure communication channels with providers.
- **Provider Onboarding & Vetting**: Comprehensive provider application flow with document uploads. Admins carefully verify and approve all service providers.
- **Secure Authentication**: Passwordless capabilities, secure session management, and role-based access control powered by Supabase Auth.
- **Admin Dashboard**: Comprehensive platform metrics, provider approval queues, and transaction/refund management.
- **Reviews & Trust Engine**: Verified clients can leave reviews, powering the rating system and provider trust badges.
- **Transactional Emails**: Automated notifications via Resend for lead assignment, credit purchases, refunds, and account status updates.
- **GDPR Compliance**: Built-in mechanisms for account deletion, data anonymization, and privacy requests.

---

## 🏗️ Technology Stack

- **Frontend Framework**: [Next.js 15](https://nextjs.org/) (App Router, React Server Components)
- **Styling & Animation**: [Tailwind CSS](https://tailwindcss.com/), [Framer Motion](https://www.framer.com/motion/), [Radix UI](https://www.radix-ui.com/)
- **Database & Backend Services**: [Supabase](https://supabase.com/) (PostgreSQL, Row Level Security, RPCs)
- **Payment Processing**: [Stripe](https://stripe.com/)
- **Email Delivery**: [Resend](https://resend.com/)
- **Language**: [TypeScript](https://www.typescriptlang.org/) (Strict Mode)

---

## 📂 Project Structure

```text
VISTAR/
├── .github/                # GitHub Actions and Workflows
├── docs/                   # Architectural and project documentation
├── scripts/                # Utility scripts for database and git operations
├── supabase/               # Supabase migrations, seed data, and configs
└── web/                    # The Next.js frontend application
    ├── public/             # Static assets (images, fonts, SVGs)
    └── src/
        ├── app/            # Next.js App Router pages and API/Webhook routes
        ├── components/     # Reusable React components (UI, Layout, Domain-specific)
        ├── lib/            # Utilities, Supabase clients, Stripe helpers
        └── types/          # Global TypeScript interfaces and type definitions
```

---

## 🚀 Local Development Setup

### 1. Prerequisites
- Node.js (v18+)
- npm, pnpm, or yarn
- Supabase CLI (if running the database locally)
- Stripe CLI (for webhook testing)

### 2. Clone the Repository
```bash
git clone https://github.com/bhagyabanghadai/VISTRA.git vistar
cd vistar/web
```

### 3. Install Dependencies
```bash
npm install
```

### 4. Environment Variables
Copy the `.env.example` to `.env.local` or reference the deployment guide. Ensure you provide your local/development keys for Supabase, Stripe, and Resend.
```bash
NEXT_PUBLIC_SUPABASE_URL=...
NEXT_PUBLIC_SUPABASE_ANON_KEY=...
SUPABASE_SERVICE_ROLE_KEY=...
STRIPE_SECRET_KEY=...
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=...
STRIPE_WEBHOOK_SECRET=...
RESEND_API_KEY=...
RESEND_FROM_EMAIL=...
```

### 5. Start the Development Server
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

---

## 🚢 Deployment

VISTAR is optimized for deployment on Vercel. 

For detailed, step-by-step production deployment instructions encompassing Supabase provisioning, Stripe configuration, and Vercel setup, please refer to the [**Deployment Guide (`DEPLOYMENT.md`)**](./DEPLOYMENT.md).

---

## 🛡️ Security & Privacy

VISTAR handles sensitive B2B data. Great care has been taken to isolate data through PostgreSQL **Row Level Security (RLS)**.
- **Provider Data**: Publicly visible only when approved.
- **Lead Data**: Visible tightly among the initiating Client, the target Provider, and Admins.
- **Administrative Actions**: Protected server-side by checking the `user_metadata.role` claim directly via the Supabase Service Role client.

---

## 📜 License

Copyright © 2026 VISTAR. All Rights Reserved.
