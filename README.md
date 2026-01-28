<div align="center">

# 🚀 Trabaho — Modern SaaS Recruitment Platform

### Connect Companies with Top Talent Seamlessly

[![Next.js](https://img.shields.io/badge/Next.js-15.3-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Prisma](https://img.shields.io/badge/Prisma-6.6-2D3748?style=for-the-badge&logo=prisma)](https://www.prisma.io/)
[![TailwindCSS](https://img.shields.io/badge/Tailwind-4.x-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

**Trabaho** is a full-featured SaaS recruitment platform that bridges the gap between companies and job seekers. Built with cutting-edge technologies, it delivers a seamless, secure, and lightning-fast hiring experience for both employers and candidates.

[Features](#-features) • [Tech Stack](#-tech-stack) • [Getting Started](#-getting-started) • [Documentation](#-project-structure) • [Deployment](#-deployment)

</div>

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Configuration](#environment-configuration)
  - [Database Setup](#database-setup)
  - [Running the Application](#running-the-application)
- [Project Structure](#-project-structure)
- [Database Schema](#-database-schema)
- [Available Scripts](#-available-scripts)
- [Deployment](#-deployment)
- [Testing](#-testing)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Overview

Trabaho is designed to revolutionize the recruitment process by providing:

- 🏢 **For Companies**: Post jobs, manage applications, review candidates, and hire top talent
- 👔 **For Job Seekers**: Discover opportunities, submit applications, track progress, and land dream jobs
- 🔒 **Enterprise Security**: Powered by Arcjet for bot protection and runtime security
- ⚡ **Blazing Fast**: Built on Next.js 15 with App Router and React Server Components
- 🌐 **Production Ready**: Deployed on Vercel with edge performance globally

---

## ✨ Features

### 🔐 Authentication & Security
- 🔑 OAuth authentication via **Google** and **GitHub** (Auth.js v5-beta)
- 🛡️ Enterprise-grade security with **Arcjet** (bot protection, rate limiting)
- 👤 Role-based access control (Company vs Job Seeker)
- 🔒 Secure session management

### 🏢 Company Dashboard
- ✅ Guided onboarding flow for company setup
- 📝 Create, edit, and manage job postings (draft/active/expired states)
- 👥 Review and manage candidate applications
- ⭐ Mark favorite candidates
- 📊 Track job post performance and expiration
- 💼 Company profile with logo, website, and social links

### 👔 Job Seeker Dashboard
- 📄 Profile creation with resume uploads via **UploadThings**
- 🔍 Browse and search job listings
- 📤 Submit applications with cover letters
- 📊 Track application history and status
- ⭐ Save favorite job posts
- 🔔 Receive notifications

### ⚙️ Power Features
- 📬 **Background Jobs**: Automated job expiration workflows via **Inngest**
- 💳 **Payments**: Stripe integration for premium listings and subscriptions
- 📤 **File Uploads**: Seamless resume and logo uploads via **UploadThings**
- 🎨 **Modern UI**: Beautiful components from **shadcn/ui** with Tailwind CSS
- 🌙 **Dark Mode**: Full dark/light theme support with **next-themes**
- 💨 **Optimized UX**: Skeleton loaders and optimistic UI updates
- 📱 **Responsive Design**: Mobile-first, works flawlessly on all devices
- 📧 **Email Notifications**: Transactional emails via **Resend**

---

## 🛠 Tech Stack

### Frontend
| Technology | Purpose |
|-----------|---------|
| [Next.js 15](https://nextjs.org/) | React framework with App Router, RSC, and SSR |
| [React 19](https://react.dev/) | UI library with latest features |
| [TypeScript](https://www.typescriptlang.org/) | Type-safe development |
| [Tailwind CSS](https://tailwindcss.com/) | Utility-first CSS framework |
| [shadcn/ui](https://ui.shadcn.com/) | Beautiful, accessible component library |
| [next-themes](https://github.com/pacocoursey/next-themes) | Dark mode implementation |
| [Lucide React](https://lucide.dev/) | Beautiful icon library |

### Backend & Database
| Technology | Purpose |
|-----------|---------|
| [Prisma](https://www.prisma.io/) | Next-generation ORM |
| [Neon PostgreSQL](https://neon.tech/) | Serverless Postgres database |
| [Auth.js](https://authjs.dev/) | OAuth authentication |
| [Zod](https://zod.dev/) | TypeScript-first schema validation |

### Infrastructure & Services
| Technology | Purpose |
|-----------|---------|
| [Vercel](https://vercel.com/) | Deployment and hosting |
| [Arcjet](https://arcjet.com/) | Security (bot protection, rate limiting) |
| [Inngest](https://inngest.com/) | Background job processing |
| [UploadThings](https://uploadthing.com/) | File uploads and management |
| [Stripe](https://stripe.com/) | Payment processing |
| [Resend](https://resend.com/) | Transactional emails |

### Development Tools
| Technology | Purpose |
|-----------|---------|
| [pnpm](https://pnpm.io/) | Fast, disk space efficient package manager |
| [ESLint](https://eslint.org/) | Code linting and quality |
| [Turbopack](https://turbo.build/) | Next-gen bundler for faster dev |

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** 20.x or higher
- **pnpm** 9.x or higher
- **PostgreSQL** database (we recommend [Neon](https://neon.tech/) for serverless)
- **Git** for version control

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/slashd0t/trabaho-platform.git
cd trabaho-platform
```

2. **Install dependencies**

```bash
pnpm install
```

### Environment Configuration

3. **Create environment file**

Copy the example environment file:

```bash
cp .env.exemple .env.local
```

4. **Configure environment variables**

Open `.env.local` and fill in the following variables:

```bash
# =============================================================================
# Authentication (Auth.js)
# =============================================================================
# Generate a secret: npx auth secret
AUTH_SECRET=""

# Google OAuth
# Get credentials: https://console.cloud.google.com/apis/credentials
AUTH_GOOGLE_ID=""
AUTH_GOOGLE_SECRET=""

# GitHub OAuth
# Get credentials: https://github.com/settings/developers
AUTH_GITHUB_ID=""
AUTH_GITHUB_SECRET=""

# =============================================================================
# Database (Neon PostgreSQL)
# =============================================================================
# Get your connection string: https://console.neon.tech/
DATABASE_URL=""

# =============================================================================
# File Uploads (UploadThings)
# =============================================================================
# Get your token: https://uploadthing.com/dashboard
UPLOADTHING_TOKEN=""

# =============================================================================
# Security (Arcjet)
# =============================================================================
# Get your key: https://app.arcjet.com/
ARCJET_KEY=""

# =============================================================================
# Payments (Stripe)
# =============================================================================
# Get keys: https://dashboard.stripe.com/apikeys
SECRET_STRIPE_KEY=""
STRIPE_WEBHOOK_SECRET=""

# =============================================================================
# Email (Resend)
# =============================================================================
# Get key: https://resend.com/api-keys
RESEND_API_KEY=""

# =============================================================================
# Application
# =============================================================================
# Your app URL (use http://localhost:3000 for development)
NEXT_PUBLIC_BASE_URL="http://localhost:3000"
```

<details>
<summary><b>📝 How to Get Each API Key</b></summary>

#### Auth.js Secret
```bash
npx auth secret
```

#### Google OAuth
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing
3. Enable Google+ API
4. Create OAuth 2.0 credentials
5. Add authorized redirect URI: `http://localhost:3000/api/auth/callback/google`

#### GitHub OAuth
1. Go to [GitHub Developer Settings](https://github.com/settings/developers)
2. Create new OAuth App
3. Set callback URL: `http://localhost:3000/api/auth/callback/github`

#### Neon PostgreSQL
1. Sign up at [Neon](https://neon.tech/)
2. Create a new project
3. Copy the connection string from the dashboard

#### UploadThings
1. Sign up at [UploadThings](https://uploadthing.com/)
2. Create a new app
3. Copy the token from settings

#### Arcjet
1. Sign up at [Arcjet](https://arcjet.com/)
2. Create a new site
3. Copy the API key

#### Stripe
1. Sign up at [Stripe](https://stripe.com/)
2. Get your secret key from the [API keys page](https://dashboard.stripe.com/apikeys)
3. For webhooks, install [Stripe CLI](https://stripe.com/docs/stripe-cli) and run `stripe listen --forward-to localhost:3000/api/webhooks/stripe`

#### Resend
1. Sign up at [Resend](https://resend.com/)
2. Create an API key from the dashboard

</details>

### Database Setup

5. **Initialize the database**

Push the Prisma schema to your database:

```bash
pnpm dlx prisma db push
```

6. **(Optional) Open Prisma Studio**

Explore your database with a visual editor:

```bash
pnpm dlx prisma studio
```

### Running the Application

7. **Start the development server**

```bash
pnpm dev
```

The application will be available at [http://localhost:3000](http://localhost:3000) 🎉

---

## 📁 Project Structure

```
trabaho-platform/
├── src/
│   ├── app/                      # Next.js App Router pages
│   │   ├── (auth)/              # Authentication routes
│   │   ├── (dashboard)/         # Protected dashboard routes
│   │   ├── api/                 # API routes
│   │   └── layout.tsx           # Root layout
│   ├── components/              # React components
│   │   ├── ui/                  # shadcn/ui components
│   │   ├── forms/               # Form components
│   │   └── ...                  # Feature components
│   ├── lib/                     # Utility libraries
│   │   ├── auth.ts              # Auth.js configuration
│   │   ├── db.ts                # Prisma client
│   │   └── stripe.ts            # Stripe configuration
│   ├── utils/                   # Helper functions
│   ├── inngest/                 # Background job functions
│   ├── generated/               # Prisma generated client
│   └── constants/               # App constants
├── prisma/
│   └── schema.prisma            # Database schema
├── public/                      # Static assets
├── .env.local                   # Environment variables (create this)
├── .env.exemple                 # Environment template
├── next.config.ts               # Next.js configuration
├── tailwind.config.ts           # Tailwind configuration
├── tsconfig.json                # TypeScript configuration
└── package.json                 # Dependencies
```

---

## 🗄 Database Schema

The platform uses the following core models:

### Core Models

```prisma
model User {
  id                   String    @id @default(cuid())
  email                String    @unique
  name                 String?
  userType             UserType? (COMPANY | JOB_SEEKER)
  onboardingComplete   Boolean   @default(false)
  company              Company?
  jobSeeker            JobSeeker?
  savedJobs            SavedJob[]
}

model Company {
  id        String   @id @default(cuid())
  name      String
  location  String
  about     String
  website   String
  logo      String
  jobs      Job[]
}

model JobSeeker {
  id              String           @id @default(cuid())
  name            String
  about           String
  resume          String
  jobApplications JobApplication[]
}

model Job {
  id              String      @id @default(cuid())
  jobTitle        String
  jobDescription  String
  employmentType  String
  location        String
  salaryFrom      Int
  salaryTo        Int
  benefits        String[]
  status          JobStatus   (DRAFT | ACTIVE | EXPIRED)
  jobApplications JobApplication[]
}

model JobApplication {
  id            String    @id @default(cuid())
  jobId         String
  jobSeekerId   String
  resume        String
  coverLetter   String?
  prevPosition  String?
  prevCompany   String?
}
```

For the complete schema, see [`prisma/schema.prisma`](./prisma/schema.prisma).

---

## 📜 Available Scripts

| Command | Description |
|---------|-------------|
| `pnpm dev` | Start development server with Turbopack |
| `pnpm build` | Build production bundle |
| `pnpm start` | Start production server |
| `pnpm lint` | Run ESLint for code quality |
| `pnpm dlx prisma studio` | Open Prisma Studio (database GUI) |
| `pnpm dlx prisma db push` | Push schema changes to database |
| `pnpm dlx prisma generate` | Generate Prisma Client |

---

## 🌐 Deployment

### Deploy to Vercel (Recommended)

Trabaho is optimized for [Vercel](https://vercel.com/) deployment:

1. **Push your code to GitHub**

```bash
git add .
git commit -m "Initial commit"
git push origin main
```

2. **Import to Vercel**
   - Go to [Vercel](https://vercel.com/new)
   - Import your GitHub repository
   - Vercel will auto-detect Next.js

3. **Configure Environment Variables**
   - Add all environment variables from `.env.local`
   - Don't forget to update `NEXT_PUBLIC_BASE_URL` to your production domain

4. **Deploy**
   - Click "Deploy"
   - Your app will be live in ~2 minutes! 🚀

### Other Platforms

Trabaho can be deployed to any platform that supports Next.js:
- **Netlify**: Use the Next.js runtime
- **Railway**: Deploy with PostgreSQL add-on
- **AWS/DigitalOcean**: Deploy as a Node.js application
- **Docker**: Create a Dockerfile for containerized deployment

---

## 🧪 Testing

> **Coming Soon**: Comprehensive test suite

Planned testing tools:
- **Jest**: Unit and integration tests
- **Playwright**: End-to-end testing
- **React Testing Library**: Component testing
- **Vitest**: Fast unit tests

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m "Add amazing feature"
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Development Guidelines

- Follow the existing code style
- Write meaningful commit messages
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting PR

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

Built with amazing tools and services:

- [Next.js](https://nextjs.org/) – The React Framework for the Web
- [Prisma](https://www.prisma.io/) – Next-generation ORM
- [Neon](https://neon.tech/) – Serverless Postgres
- [Inngest](https://inngest.com/) – Background job orchestration
- [Arcjet](https://arcjet.com/) – Application security
- [UploadThings](https://uploadthing.com/) – File uploads
- [shadcn/ui](https://ui.shadcn.com/) – Beautiful components
- [Tailwind CSS](https://tailwindcss.com/) – Utility-first CSS
- [Vercel](https://vercel.com/) – Deployment platform

---

## 📧 Contact & Support

- **Author**: Ayoub Hayda
- **GitHub**: [@ayoubhayda](https://github.com/ayoubhayda)
- **Repository**: [hireek-platform](https://github.com/ayoubhayda/hireek-platform)

---

<div align="center">

</div>