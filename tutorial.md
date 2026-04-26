# Complete Game Developer Portfolio Tutorial

## From Absolute Zero to Professional Portfolio

A comprehensive, university-level course teaching you how to build a premium Game Developer Portfolio using Next.js 15, TypeScript, Tailwind CSS, and Framer Motion.

---

# Chapter 1 — Introduction to Modern Portfolio Development

## What is a Portfolio?

A portfolio is your digital calling card as a developer. It's a website that showcases your skills, projects, and experience to potential employers, clients, and collaborators. Think of it as your 24/7 online resume that never sleeps and works even when you're not actively applying for jobs.

For game developers, a portfolio isn't just about listing skills—it's about demonstrating them. Game development is inherently creative and visual. A game developer's portfolio should feel like a game itself: interactive, engaging, and memorable.

## Why Portfolios Matter

Consider this: when a recruiter or hiring manager receives your application, they likely have dozens of other applications to review. Your resume might get 30 seconds of attention. But a well-crafted portfolio can:

1. **Instantly demonstrate competence** — Rather than saying "I can build games," your portfolio shows them
2. **Stand out from the crowd** — Most developers have similar resumes; few have memorable portfolios
3. **Continue working for you** — Once published, your portfolio works 24/7 even when you're sleeping
4. **Show personality** — Games are creative; your portfolio should reflect that creativity
5. **Prove your claims** — Anyone can claim to be a "game developer"; your portfolio proves it

## What Makes a Good Developer Portfolio

Before we dive into code, let's understand what separates a good portfolio from a forgettable one:

### The Good Portfolio Checklist

- [ ] **Clear value proposition** — Visitor knows what you do within 3 seconds
- [ ] **Project showcase** — At least 2-3 projects with working demos or videos
- [ ] **Skills demonstration** — Not just listed, but demonstrated through the site itself
- [ ] **Contact method** — Easy way to reach you
- [ ] **Responsive design** — Works on mobile, tablet, and desktop
- [ ] **Fast loading** — Loads in under 3 seconds
- [ ] **Memorable design** — Leaves a lasting impression
- [ ] **Easy navigation** — Anyone can find what they need in seconds

### The Great Portfolio (Going Above and Beyond)

- [ ] **Smooth animations** — Delightful interactions throughout
- [ ] **3D elements** — Show technical prowess with WebGL/Three.js
- [ ] **Dark theme by default** — Easier on eyes, popular in gaming
- [ ] **Glassmorphism effects** — Modern UI trend
- [ ] **Neon accents** — Gaming aesthetic
- [ ] **Custom cursor** — Attention to detail
- [ ] **Micro-interactions** — Small animations on every interaction

## React vs Next.js: Understanding the Difference

If you're new to web development, you might wonder: "Why Next.js? Why not just React?"

Here's the fundamental difference:

### React: The Library

React is a **JavaScript library** for building user interfaces. Think of it as a set of building blocks. You can build anything with React, but you have to figure out:

- How to structure your project
- How to handle routing (navigation between pages)
- How to optimize for search engines
- How to handle server-side rendering
- How to manage images
- How to export for production

React is like having raw materials—powerful, but you need to build everything yourself.

### Next.js: The Framework

Next.js is a **React framework** that provides everything you need out of the box:

- **File-based routing** — Just create files, and Next.js handles navigation
- **Server-side rendering** — Better SEO and performance
- **Image optimization** — Automatic optimization for any image
- **API routes** — Build backend functionality without a separate server
- **Static export** — Deploy anywhere
- **Preview mode** — Live preview before publishing
- **TypeScript support** — Built-in type safety

Next.js is like having a fully-equipped kitchen with ingredients, recipes, and a chef—it provides everything to build a complete application.

### Why We Use Next.js for Portfolios

1. **SEO matters** — Portfolios need to be discoverable; Next.js has excellent SEO support
2. **Performance** — Fast loading leads to more engagement
3. **Static generation** — Deploy to CDNs for global speed
4. **Developer experience** — Less time configuring, more time creating
5. **Industry standard** — Most modern portfolios use Next.js or similar

## Modern Frontend Architecture

Before we dive into code, let's understand the architecture we'll be building:

```
┌─────────────────────────────────────────────────────────────┐
│                     BROWSER                                 │
│  ┌─────────────────────────────────────────────────┐    │
│  │              User Interface                        │    │
│  │  (Navigation, Pages, Components, Animations)      │    │
│  └─────────────────────────────────────────────────┘    │
│                            ↑                              │
│                    React Components                       │
│                            ↑                              │
│                     Next.js App Router                    │
│                    (File-based routing)                   │
│                            ↑                              │
│              Server / Static Generation                   │
│                            ↑                              │
│                        CDN / Edge                         │
└─────────────────────────────────────────────────────────────┘
```

This architecture provides:
- **Fast initial load** via static generation
- **Fast navigation** via client-side rendering after initial load
- **SEO** via server-side rendering for initial load
- **Great UX** via React's interactive nature

---

# Chapter 2 — Installing Everything

Now let's set up our development environment. We'll install all the tools we need to build our portfolio.

## Prerequisites

### Node.js

Node.js is a JavaScript runtime that lets us run JavaScript outside of a browser. Next.js requires Node.js to run.

**Installation:**

1. Visit https://nodejs.org
2. Download the LTS (Long Term Support) version
3. Run the installer
4. Restart your terminal

**Verification:**

```bash
node -v
```

You should see something like `v20.x.x` or higher.

### npm

npm (Node Package Manager) comes with Node.js. It's the largest software registry in the world—millions of JavaScript packages.

**Verification:**

```bash
npm -v
```

You should see something like `10.x.x`.

### VS Code

Visual Studio Code is Microsoft's free code editor. It's the most popular editor for JavaScript development.

**Installation:**

1. Visit https://code.visualstudio.com
2. Download for your operating system
3. Run the installer

**Recommended Extensions:**

After installing VS Code, install these extensions:

- **ESLint** — Lints your code for errors
- **Prettier** — Formats your code automatically
- **Tailwind CSS IntelliSense** — Autocompletes Tailwind classes
- **TypeScript Vue Plugin** (or React Plugin)

### Git

Git is a version control system. It tracks changes to your code, so you can revert if something goes wrong and collaborate with others.

**Installation:**

- **Windows**: Download from https://git-scm.com
- **macOS**: `brew install git`
- **Linux**: `sudo apt install git`

**Verification:**

```bash
git --version
```

## Creating Our Project

Now let's create our Next.js project with all the options we need:

```bash
npx create-next-app@latest portfolio --typescript --tailwind --eslint --app --src-dir --import-alias "@/*" --use-npm --yes
```

Let's break down what each option does:

- **`npx`** — Runs a package without installing it globally
- **`create-next-app@latest`** — Creates a new Next.js app using the latest version
- **`portfolio`** — Our project name
- **`--typescript`** — Uses TypeScript instead of JavaScript
- **`--tailwind`** — Includes Tailwind CSS
- **`--eslint`** — Includes ESLint for code quality
- **`--app`** — Uses the App Router (new framework)
- **`--src-dir`** — Creates the app folder in `src/` instead of root
- **`--import-alias "@/*"`** — Lets us import from `@/components` instead of `../../components`
- **`--use-npm`** — Uses npm as the package manager
- **`--yes`** — Answers yes to all prompts

### Project Structure After Creation

After running the command, your project will look like this:

```
portfolio/
├── node_modules/      # All installed dependencies
├── public/           # Static files (images, etc.)
├── src/
│   └── app/          # Next.js App Router
│       ├── globals.css
│       ├── layout.tsx
│       ├── page.tsx
│       └── page.module.css
├── .gitignore       # Tells Git what to ignore
├── eslint.config.mjs  # ESLint configuration
├── next.config.ts    # Next.js configuration
├── package.json      # Project dependencies
├── package-lock.json
├── postcss.config.mjs
├── README.md
├── tsconfig.json    # TypeScript configuration
└── typescript.json
```

## Installing Additional Dependencies

We need several more packages for our portfolio. Let's install them:

```bash
npm install framer-motion lucide-react @react-three/fiber @react-three/drei three gsap lenis class-variance-authority clsx tailwind-merge @radix-ui/react-slot
```

Here's what each package does:

| Package | Purpose |
|---------|---------|
| `framer-motion` | Animation library for React |
| `lucide-react` | Icons library |
| `@react-three/fiber` | Three.js for React (3D) |
| `@react-three/drei` | Helper components for R3F |
| `three` | 3D graphics library |
| `gsap` | Professional animation library |
| `lenis` | Smooth scrolling |
| `class-variance-authority` | Variant props for components |
| `clsx` | Conditional class names |
| `tailwind-merge` | Merge Tailwind classes |
| `@radix-ui/react-slot` | Universal component wrapper |

## Understanding package.json

The `package.json` file is the heart of your project. It tracks dependencies and scripts:

```json
{
  "name": "portfolio",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  },
  "dependencies": {
    "next": "^15.1.0",
    "react": "^19.0.0",
    "react-dom": "^19.0.0"
  },
  "devDependencies": {
    "@types/node": "^20",
    "@types/react": "^19",
    "@types/react-dom": "^19",
    "typescript": "^5"
  }
}
```

### NPM Scripts

| Script | What it Does |
|--------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run start` | Start production server |
| `npm run lint` | Check code quality |

## Running Our Development Server

Now let's start our development server:

```bash
cd portfolio
npm run dev
```

Open http://localhost:3000 in your browser. You should see the Next.js welcome page!

Congratulations—you've just created your first Next.js app!

---

# Chapter 3 — Understanding Next.js Deeply

Now that we have a working project, let's understand how Next.js works under the hood.

## What is Next.js?

Next.js is a React framework that provides:

1. **File-based routing** — Navigation through file structure
2. **Server Components** — Components that render on the server
3. **Client Components** — Components that render in the browser
4. **Layouts** — Shared UI across pages
5. **Server-side Rendering** — Pre-rendering pages on the server
6. **Static Generation** — Pre-rendering pages at build time
7. **ISR (Incremental Static Regeneration)** — Updating static pages periodically

## App Router vs Pages Router

Next.js has two ways to build applications:

### Pages Router (Older)

```typescript
// pages/index.tsx
export default function Home() {
  return <h1>Hello</h1>
}
```

### App Router (Newer, What We Use)

```typescript
// app/page.tsx
export default function Home() {
  return <h1>Hello</h1>
}
```

We use the **App Router** because it's newer and has more features.

## How Routing Works in Next.js

In Next.js App Router, our file structure determines our routes:

```
src/app/
├── page.tsx           → /
├── about/
│   └── page.tsx       → /about
├── projects/
│   ├── page.tsx      → /projects
│   └── [slug]/
│       └── page.tsx   → /projects/any-slug
...
```

### Creating Routes

To create a new page, simply create a folder and add a `page.tsx` file:

**Create `/contact` page:**

```
src/app/contact/
└── page.tsx
```

```typescript
// src/app/contact/page.tsx
export default function ContactPage() {
  return (
    <main>
      <h1>Contact Me</h1>
      <p>Email: hello@example.com</p>
    </main>
  )
}
```

## Server Components vs Client Components

This is one of the most important concepts in Next.js App Router.

### Server Components (Default)

Server Components are components that render on the server. They're:

- **Fast** — No JavaScript sent to browser for rendering
- **Secure** — Can access databases directly
- **Default** — No "use client" directive needed

```typescript
// This is a Server Component (default)
export default function About() {
  return <h1>About Page</h1>
}
```

### Client Components

Client Components are components that render in the browser. They're needed when:

- Using React hooks (useState, useEffect)
- Using event handlers (onClick, onChange)
- Using animation libraries (framer-motion)

```typescript
'use client' // This directive makes it a Client Component

import { useState } from 'react'

export function Counter() {
  const [count, setCount] = useState(0)
  
  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  )
}
```

### When to Use Each

| Use Server Components | Use Client Components |
|---------------------|---------------------|
| Static content | Interactive elements |
| Data fetching | useState, useEffect |
| SEO-critical content | onClick, onChange events |
| Large components | framer-motion animations |
| Layout, Navigation | Buttons with interactions |

### The Rule

**Default to Server Components.** Only add "use client" when you need interactivity.

## Layouts in Next.js

Layouts wrap pages and provide consistent UI:

```typescript
// src/app/layout.tsx
import './globals.css'

export default function RootLayout({
  children,
}: {
  children: React.ReactNode
}) {
  return (
    <html lang="en">
      <body>
        <nav>My Navigation</nav>
        {children}
        <footer>My Footer</footer>
      </body>
    </html>
  )
}
```

This layout wraps every page in our app!

### Nested Layouts

We can also create layouts for specific sections:

```typescript
// src/app/dashboard/layout.tsx
export default function DashboardLayout({ children }) {
  return (
    <div className="flex">
      <aside>Sidebar</aside>
      <main>{children}</main>
    </div>
  )
}
```

## Rendering in Next.js

Next.js supports several rendering strategies:

### 1. Static Site Generation (SSG)

Pages are built once at build time. Fastest possible.

```typescript
// This page is statically generated at build time
export default function About() {
  return <h1>About</h1>
}
```

### 2. Server-Side Rendering (SSR)

Pages are generated on each request. For dynamic content.

```typescript
// This page is server-rendered on each request
export const dynamic = 'force-dynamic'

export default function Page() {
  const data = fetch('https://api.example.com/data')
  return <h1>{data.title}</h1>
}
```

### 3. Client-Side Rendering

All rendering happens in the browser.

```typescript
'use client'

export default function Interactive() {
  const [data, setData] = useState(null)
  
  useEffect(() => {
    fetchData().then(setData)
  }, [])
  
  return <h1>{data?.title}</h1>
}
```

For our portfolio, we primarily use **Static Site Generation** because our content doesn't change frequently.

## Dynamic Routes

Dynamic routes let us create pages programmatically:

```typescript
// src/app/projects/[slug]/page.tsx
'use client'

import { useParams } from 'next/navigation'

export default function ProjectPage() {
  const params = useParams()
  const slug = params.slug
  
  return <h1>Project: {slug}</h1>
}
```

If someone visits `/projects/nebula-wars`, `slug` will be `"nebula-wars"`.

---

# Chapter 4 — Folder Structure Explained

A well-organized project is easier to maintain and scale. Let's explore our folder structure.

## The Main Folders

```
src/
├── app/            # Next.js App Router
├── components/     # Reusable React components
├── data/          # Static data (projects, etc.)
├── hooks/         # Custom React hooks
└── lib/            # Utility functions
```

### `src/app/` — Next.js App Router

This is where our pages live. Every folder becomes a route.

```
src/app/
├── page.tsx           → /
├── about/
│   └── page.tsx      → /about
├── projects/
│   ├── page.tsx      → /projects
│   └── [slug]/
│       └── page.tsx   → /projects/:slug
├── skills.tsx
├── resume.tsx
├── contact.tsx
├── layout.tsx        → Root layout (wraps all pages)
└── globals.css      → Global styles
```

### `src/components/` — Reusable Components

Components are reusable pieces of UI. We organize them into folders:

```
src/components/
├── ui/              # Basic UI components (Button, Card, Input)
│   └── button.tsx
└── sections/        # Page sections (Navbar, Footer, Hero)
    ├── Navigation.tsx
    └── Footer.tsx
```

**Why separate UI and sections?**

- **UI components** are generic and reusable anywhere (Button works everywhere)
- **Sections** are specific to our portfolio (Navbar only goes at the top)

### `src/data/` — Static Data

Our portfolio data lives here:

```typescript
// src/data/projects.ts
export const projects = [
  {
    id: "1",
    slug: "nebula-wars",
    title: "Nebula Wars",
    description: "A fast-paced space shooter...",
    // ... more fields
  },
]
```

Having data separate from components makes it:

- **Easier to update** — Change project info without touching components
- **Type-safe** — Strong typing with TypeScript
- **Reusable** — Same data in multiple places

### `src/hooks/` — Custom Hooks

Hooks are reusable logic. Custom hooks let us extract logic:

```typescript
// src/hooks/useSmoothScroll.ts
'use client'

import { useEffect, useRef } from "react"
import Lenis from "lenis"

export function useSmoothScroll() {
  const lenisRef = useRef<Lenis | null>(null)

  useEffect(() => {
    const lenis = new Lenis({ duration: 1.2 })
    lenisRef.current = lenis
    
    function raf(time: number) {
      lenis.raf(time)
      requestAnimationFrame(raf)
    }
    
    requestAnimationFrame(raf)
    
    return () => lenis.destroy()
  }, [])

  return lenisRef
}
```

### `src/lib/` — Utilities

Helper functions live here:

```typescript
// src/lib/utils.ts
import { type ClassValue, clsx } from "clsx"
import { twMerge } from "tailwind-merge"

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs))
}
```

This `cn` function merges Tailwind classes intelligently.

## Folder Naming Conventions

| Folder | Purpose | Naming |
|--------|---------|--------|
| `app/` | Pages | kebab-case (`contact.tsx`) |
| `components/` | Components | PascalCase (`Navigation.tsx`) |
| `data/` | Data files | camelCase (`projects.ts`) |
| `hooks/` | Hooks | camelCase (`useSmoothScroll.ts`) |
| `lib/` | Utilities | camelCase (`utils.ts`) |

---

# Chapter 5 — Tailwind CSS Masterclass

Tailwind CSS is a utility-first CSS framework. Instead of writing custom CSS, you compose your design using utility classes.

## How Tailwind Works

Instead of this:

```css
/* Old way: Custom CSS */
.my-button {
  background-color: #8B5CF6;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 0.5rem;
  font-weight: 500;
}
.my-button:hover {
  background-color: #7C3AED;
}
```

You write this:

```jsx
<!-- Tailwind: Utility classes -->
<button className="bg-primary text-white px-4 py-2 rounded-lg font-medium hover:bg-primary/90">
  Click Me
</button>
```

## Why Tailwind?

1. **No context switching** — Stay in your JSX
2. **Small bundle size** — Only includes what you use
3. **Easy customization** — Theme is just config
4. **Consistent design** — Design tokens ensure consistency

## Core Utility Classes

### Colors

Our portfolio uses a custom color palette:

```css
/* In globals.css */
:root {
  --background: #0B0F19;    /* Dark background */
  --foreground: #ffffff;     /* White text */
  --primary: #8B5CF6;     /* Purple accent */
  --accent: #06B6D4;       /* Cyan accent */
  --secondary: #1E293B;    /* Darker gray */
  --muted: #64748B;        /* Muted text */
}
```

We can use these in Tailwind:

```jsx
<div className="bg-background text-foreground">...</div>
<div className="bg-primary text-white">...</div>
<div className="bg-secondary text-muted">...</div>
```

### Spacing

Tailwind's spacing scale: `0`, `1`, `2`, `4`, `6`, `8`, `10`, `12`, `16`, `20`, `24`, `32`...

```jsx
<div className="p-4">      /* padding: 1rem */
<div className="px-4">     /* padding-left/right: 1rem */
<div className="py-4">     /* padding-top/bottom: 1rem */
<div className="m-4">      /* margin: 1rem */
<div className="gap-4">    /* gap: 1rem (flexbox/grid) */
```

### Typography

```jsx
<h1 className="text-4xl font-bold">Title</h1>
<p className="text-lg text-muted-foreground">Description</p>
<span className="text-sm font-medium">Label</span>
```

### Layout

#### Flexbox

```jsx
<div className="flex">                              /* display: flex */
<div className="flex-row">                         /* flex-direction: row (default) */
<div className="flex-col">                         /* flex-direction: column */
<div className="justify-center">                      /* justify-content: center */
<div className="justify-between">                   /* justify-content: space-between */
<div className="items-center">                     /* align-items: center */
<div className="flex-wrap">                       /* flex-wrap: wrap */
```

#### Grid

```jsx
<div className="grid">                               /* display: grid */
<div className="grid-cols-2">                       /* grid-template-columns: repeat(2, 1fr) */
<div className="grid-cols-3">                       /* grid-template-columns: repeat(3, 1fr) */
<div className="grid-cols-4">                       /* grid-template-columns: repeat(4, 1fr) */
<div className="col-span-2">                      /* grid-column: span 2 */
```

### Responsive Design

Prefix any class with a breakpoint to apply at that size:

```jsx
<!-- Mobile first: defaults apply to all sizes -->
<div className="flex flex-col">

<!-- Then override for larger screens -->
<div className="flex flex-col md:flex-row">
<div className="flex flex-col md:flex-row lg:flex-row">
```

| Prefix | Breakpoint |
|--------|-----------|
| `sm:` | 640px |
| `md:` | 768px |
| `lg:` | 1024px |
| `xl:` | 1280px |

### Hover and Focus States

```jsx
<button className="hover:bg-primary/90">...</button>
<input className="focus:outline-none focus:ring-2" />
```

### Custom Effects

#### Glassmorphism

```css
.glass {
  background: rgba(18, 24, 41, 0.7);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(139, 92, 246, 0.2);
}
```

Usage:

```jsx
<div className="glass">Glass card</div>
```

#### Neon Glow

```css
.neon-glow {
  box-shadow: 0 0 20px rgba(139, 92, 246, 0.3),
              0 0 40px rgba(139, 92, 246, 0.1);
}
```

Usage:

```jsx
<button className="neon-glow">Glowing button</button>
```

## Responsive Grid Example

```jsx
<div className="grid 
  grid-cols-1        /* 1 column on mobile */
  md:grid-cols-2     /* 2 columns on tablet */
  lg:grid-cols-3      /* 3 columns on desktop */
  gap-6             /* Gap between items */
>
  <ProjectCard />
  <ProjectCard />
  <ProjectCard />
  <ProjectCard />
  <ProjectCard />
  <ProjectCard />
</div>
```

---

# Chapter 6 — Component Architecture

Good architecture makes code maintainable. Let's learn how to structure components.

## What is a Component?

A component is a reusable piece of UI. Think of them like LEGO blocks—you build your app by combining components.

```jsx
// A simple component
function Button({ children }) {
  return <button>{children}</button>
}

// Using the component
<Button>Click me</Button>
```

## Props: Making Components Dynamic

Props pass data to components:

```jsx
// Component with props
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>
}

// Using with props
<Greeting name="John" />
// Renders: <h1>Hello, John!</h1>
```

### Multiple Props

```jsx
function ProjectCard({ title, description, tags }) {
  return (
    <div className="card">
      <h3>{title}</h3>
      <p>{description}</p>
      <div className="tags">
        {tags.map(tag => <span>{tag}</span>)}
      </div>
    </div>
  )
}

<ProjectCard 
  title="Nebula Wars"
  description="Space shooter game"
  tags={["Unity", "C#", "Multiplayer"]}
/>
```

## State: Making Components Interactive

State stores data that changes over time:

```jsx
'use client'

import { useState } from 'react'

function Counter() {
  const [count, setCount] = useState(0)
  
  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  )
}
```

## Component Composition

Components can contain other components:

```jsx
function Navigation() {
  return (
    <nav>
      <Logo />
      <Links />
      <SocialIcons />
    </nav>
  )
}

function Logo() { return <div>My Logo</div> }
function Links() { return <div>Links</div> }
function SocialIcons() { return <div>Icons</div> }
```

## Button Component Example

Let's build a proper Button component:

```typescript
// src/components/ui/button.tsx
import * as React from "react"
import { Slot } from "@radix-ui/react-slot"
import { cva, type VariantProps } from "class-variance-authority"
import { cn } from "@/lib/utils"

const buttonVariants = cva(
  "inline-flex items-center justify-center gap-2 whitespace-nowrap rounded-lg text-sm font-medium transition-all duration-300 focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring disabled:pointer-events-none disabled:opacity-50",
  {
    variants: {
      variant: {
        default: "bg-primary text-primary-foreground hover:bg-primary/90",
        destructive: "bg-destructive text-destructive-foreground hover:bg-destructive/90",
        outline: "border border-border bg-transparent hover:bg-secondary",
        secondary: "bg-secondary text-secondary-foreground hover:bg-secondary/80",
        ghost: "hover:bg-secondary hover:text-secondary-foreground",
        link: "text-primary underline-offset-4 hover:underline",
      },
      size: {
        default: "h-10 px-4 py-2",
        sm: "h-9 rounded-md px-3",
        lg: "h-12 rounded-lg px-8",
        icon: "h-10 w-10",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
)

export interface ButtonProps
  extends React.ButtonHTMLAttributes<HTMLButtonElement>,
    VariantProps<typeof buttonVariants> {
  asChild?: boolean;
}

const Button = React.forwardRef<HTMLButtonElement, ButtonProps>(
  ({ className, variant, size, asChild = false, ...props }, ref) => {
    const Comp = asChild ? Slot : "button"
    return (
      <Comp
        className={cn(buttonVariants({ variant, size, className }))}
        ref={ref}
        {...props}
      />
    )
  }
)
Button.displayName = "Button"

export { Button, buttonVariants }
```

This component:

1. Supports multiple **variants** (default, destructive, outline, etc.)
2. Supports multiple **sizes** (sm, md, lg, icon)
3. Uses **cva** for type-safe variants
4. Uses **forwardRef** to pass refs properly
5. Has proper TypeScript typing

---

# Chapter 7 — Building Hero Section

The hero section is the first thing visitors see. It needs to make a strong impression.

## Hero Section Requirements

- Large typography
- Clear value proposition
- CTA buttons
- Visual interest (background)
- Responsive design

## Building It Step by Step

### Step 1: Basic Structure

```jsx
export default function HeroSection() {
  return (
    <section className="min-h-screen flex items-center justify-center">
      <div className="container px-4">
        <h1>Game Developer & Gameplay Programmer</h1>
        <p>Building Immersive Experiences</p>
        <div className="flex gap-4">
          <button>View Projects</button>
          <button>Contact Me</button>
        </div>
      </div>
    </section>
  )
}
```

### Step 2: Add Typography

```jsx
<h1 className="text-4xl md:text-6xl lg:text-7xl font-bold mb-6 leading-tight">
  Game Developer &{" "}
  <span className="gradient-text">Gameplay Programmer</span>
  <br />
  Building Immersive Experiences
</h1>
```

### Step 3: Add Animations

```jsx
import { motion } from 'framer-motion'

<motion.div
  initial={{ opacity: 0, y: 20 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ duration: 0.6 }}
>
```

### Step 4: Complete Implementation

```jsx
export default function HeroSection() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      {/* Background */}
      <div className="absolute inset-0 bg-[radial-gradient(ellipse_at_center,_var(--tw-gradient-stops))] from-primary/20 via-background to-background" />
      
      {/* Content */}
      <motion.div
        className="container relative z-20 px-4"
        initial={{ opacity: 0, y: 30 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.6 }}
      >
        {/* Badge */}
        <motion.div
          initial={{ opacity: 0, y: 20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.6 }}
          className="mb-6"
        >
          <span className="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-primary/10 border border-primary/20 text-primary text-sm font-medium">
            <Zap className="w-4 h-4" />
            Available for game development projects
          </span>
        </motion.div>

        {/* Main Title */}
        <h1 className="text-4xl md:text-6xl lg:text-7xl font-bold mb-6 leading-tight">
          Game Developer &{" "}
          <span className="gradient-text">Gameplay Programmer</span>
          <br />
          Building Immersive Experiences
        </h1>

        {/* Description */}
        <p className="text-lg md:text-xl text-muted-foreground max-w-2xl mx-auto mb-10">
          Creating interactive worlds with AAA-quality gameplay systems,
          cutting-edge mechanics, and player-centric experiences.
        </p>

        {/* CTA Buttons */}
        <div className="flex flex-col sm:flex-row gap-4 justify-center">
          <Link href="/projects">
            <Button size="xl" variant="glow">
              View Projects
              <ArrowRight className="w-5 h-5" />
            </Button>
          </Link>
          <Link href="/resume">
            <Button size="xl" variant="outline">
              <Download className="w-5 h-5" />
              Download Resume
            </Button>
          </Link>
          <Link href="/contact">
            <Button size="xl" variant="ghost">
              Contact Me
              <Mail className="w-5 h-5" />
            </Button>
          </Link>
        </div>
      </motion.div>

      {/* Scroll indicator */}
      <motion.div
        className="absolute bottom-8 left-1/2 -translate-x-1/2"
        animate={{ y: [0, 10, 0] }}
        transition={{ repeat: Infinity, duration: 1.5 }}
      >
        <span className="text-sm text-muted-foreground">Scroll to explore</span>
        <ChevronDown className="w-5 h-5 mx-auto" />
      </motion.div>
    </section>
  )
}
```

---

# Chapter 8 — Framer Motion Full Guide

Framer Motion is React's animation library. It makes animations declarative—you describe *what* you want, not *how* to do it.

## Basic Animations

### Fade In

```jsx
import { motion } from 'framer-motion'

<motion.div
  initial={{ opacity: 0 }}
  animate={{ opacity: 1 }}
  transition={{ duration: 0.6 }}
>
  Content
</motion.div>
```

### Slide In

```jsx
<motion.div
  initial={{ opacity: 0, y: 20 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ duration: 0.6 }}
>
  Content
</motion.div>
```

## Animation Variants

Variants let you coordinate multiple animations:

```jsx
const containerVariants = {
  hidden: { opacity: 0 },
  visible: { 
    opacity: 1,
    transition: {
      staggerChildren: 0.1
    }
  }
}

const itemVariants = {
  hidden: { opacity: 0, y: 20 },
  visible: { opacity: 1, y: 0 }
}

// Usage
<motion.div variants={containerVariants} initial="hidden" animate="visible">
  <motion.div variants={itemVariants}>Item 1</motion.div>
  <motion.div variants={itemVariants}>Item 2</motion.div>
  <motion.div variants={itemVariants}>Item 3</motion.div>
</motion.div>
```

This creates a staggered animation—each item animates 0.1s after the previous.

## Hover Animations

```jsx
<motion.button
  whileHover={{ scale: 1.05 }}
  whileTap={{ scale: 0.95 }}
>
  Click me
</motion.button>
```

## Scroll Animations

Framer Motion can animate based on scroll position:

```jsx
import { useScroll, useTransform } from 'framer-motion'

function MyComponent() {
  const { scrollY } = useScroll()
  const y = useTransform(scrollY, [0, 500], [0, 150])
  const opacity = useTransform(scrollY, [0, 300], [1, 0])
  
  return (
    <motion.div style={{ y, opacity }}>
      Content
    </motion.div>
  )
}
```

## Layout Animations

Layout animations automatically animate when layout changes:

```jsx
<motion.div layout>
  This will animate when moved
</motion.div>
```

## Common Patterns

### On-scroll reveal

```jsx
import { motion } from 'framer-motion'

<motion.div
  initial={{ opacity: 0, y: 50 }}
  whileInView={{ opacity: 1, y: 0 }}
  viewport={{ once: true }}
  transition={{ duration: 0.6 }}
>
  Content reveals when scrolled into view
</motion.div>
```

### Entrance animation

```jsx
<motion.div
  initial={{ opacity: 0, scale: 0.9 }}
  animate={{ opacity: 1, scale: 1 }}
  transition={{ 
    duration: 0.6,
    ease: "easeOut"
  }}
>
  Content
</motion.div>
```

---

# Chapter 9 — GSAP Animation Guide

GSAP (GreenSock Animation Platform) is a professional-grade animation library.

## Why GSAP?

1. **Timeline** — Sequence animations precisely
2. **ScrollTrigger** — Trigger animations on scroll
3. **Performance** — Industry-leading performance
4. **Control** — Pause, reverse, restart animations

## Basic GSAP

```javascript
import gsap from 'gsap'

// Simple animation
gsap.to(".element", {
  duration: 1,
  x: 100,
  opacity: 1
})
```

## Timeline

GSAP Timelines let you sequence animations:

```javascript
const tl = gsap.timeline()

tl.to(".box1", { x: 100, duration: 1 })
  .to(".box2", { x: 100, duration: 1 })
  .to(".box3", { x: 100, duration: 1 })
```

This plays all three animations one after another.

## ScrollTrigger

ScrollTrigger triggers animations based on scroll position:

```javascript
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

gsap.from(".project-card", {
  scrollTrigger: ".project-card",
  y: 100,
  opacity: 0,
  duration: 1
})
```

### Reveal on Scroll

```javascript
gsap.from(".reveal", {
  scrollTrigger: {
    trigger: ".reveal",
    start: "top 80%", // Start when top of element is 80% down the viewport
    toggleActions: "play none none reverse"
  },
  y: 50,
  opacity: 0,
  duration: 1
})
```

---

# Chapter 10 — React Three Fiber

React Three Fiber (R3F) brings 3D to React. It's a renderer for Three.js.

## Setting Up R3F

```jsx
import { Canvas } from '@react-three/fiber'

function Scene() {
  return (
    <Canvas>
      <mesh>
        <boxGeometry />
        <meshStandardMaterial color="purple" />
      </mesh>
      <ambientLight />
      <pointLight position={[10, 10, 10]} />
    </Canvas>
  )
}
```

## Basic 3D Concepts

### Mesh

A mesh is a 3D object with geometry and material:

```jsx
<mesh>
  <boxGeometry args={[1, 1, 1]} />  {/* Shape */}
  <meshStandardMaterial color="#8B5CF6" />  {/* Appearance */}
</mesh>
```

### Geometry Types

| Geometry | What It Creates |
|----------|----------------|
| `boxGeometry` | Cube/box |
| `sphereGeometry` | Sphere |
| `planeGeometry` | Flat plane |
| `torusGeometry` | Donut shape |

### Materials

| Material | Appearance |
|----------|------------|
| `meshBasicMaterial` | Flat, unlit |
| `meshStandardMaterial` | Reacts to light |
| `meshPhongMaterial` | Shiny surface |

### Lights

```jsx
<ambientLight intensity={0.5} />        {/* Overall illumination */}
<pointLight position={[10, 10, 10]} />     {/* Point light source */}
<directionalLight />                    {/* Sun-like light */}
```

### Camera

```jsx
<Canvas camera={{ position: [0, 0, 5], fov: 75 }}>
```

- `position: [x, y, z]` — Camera location
- `fov` — Field of view (lower = more zoomed in)

## Animated 3D

Use `useFrame` for animations:

```jsx
import { useRef } from 'react'
import { useFrame } from '@react-three/fiber'

function AnimatedBox() {
  const meshRef = useRef()
  
  useFrame((state) => {
    meshRef.current.rotation.x = state.clock.elapsedTime * 0.2
    meshRef.current.rotation.y = state.clock.elapsedTime * 0.3
  })
  
  return (
    <mesh ref={meshRef}>
      <boxGeometry />
      <meshStandardMaterial color="purple" />
    </mesh>
  )
}
```

---

# Chapter 11 — Building Portfolio Sections

Let's build each section of our portfolio.

## Navigation

Requirements:
- Sticky position
- Blur background on scroll
- Mobile hamburger menu
- Smooth navigation

```jsx
// src/components/sections/Navigation.tsx
'use client'

import { useState, useEffect } from 'react'
import Link from 'next/link'
import { usePathname } from 'next/navigation'
import { motion, AnimatePresence } from 'framer-motion'
import { Menu, X, Mail, Link2 } from 'lucide-react'
import { Button } from '@/components/ui/button'
import { cn } from '@/lib/utils'

const navLinks = [
  { href: "/", label: "Home" },
  { href: "/about", label: "About" },
  { href: "/projects", label: "Projects" },
  { href: "/skills", label: "Skills" },
  { href: "/resume", label: "Resume" },
  { href: "/contact", label: "Contact" },
]

export function Navigation() {
  const [isScrolled, setIsScrolled] = useState(false)
  const [isMobileMenuOpen, setIsMobileMenuOpen] = useState(false)
  const pathname = usePathname()

  useEffect(() => {
    const handleScroll = () => {
      setIsScrolled(window.scrollY > 50)
    }
    window.addEventListener('scroll', handleScroll)
    return () => window.removeEventListener('scroll', handleScroll)
  }, [])

  useEffect(() => {
    setIsMobileMenuOpen(false)
  }, [pathname])

  return (
    <motion.header
      className={cn(
        "fixed top-0 left-0 right-0 z-50 transition-all duration-300",
        isScrolled ? "glass py-3" : "bg-transparent py-5"
      )}
      initial={{ y: -100 }}
      animate={{ y: 0 }}
    >
      <div className="container mx-auto px-4 flex items-center justify-between">
        <Link href="/" className="flex items-center gap-2">
          <div className="w-10 h-10 rounded-lg bg-primary flex items-center justify-center neon-glow">
            <span className="text-white font-bold text-lg">G</span>
          </div>
          <span className="font-bold text-xl">GDEV</span>
        </Link>

        {/* Desktop Nav */}
        <nav className="hidden lg:flex items-center gap-8">
          {navLinks.map((link) => (
            <Link
              key={link.href}
              href={link.href}
              className={cn(
                "text-sm font-medium hover:text-primary",
                pathname === link.href ? "text-primary" : "text-foreground/70"
              )}
            >
              {link.label}
            </Link>
          ))}
        </nav>

        {/* Mobile Menu Button */}
        <Button
          variant="ghost"
          size="icon"
          className="lg:hidden"
          onClick={() => setIsMobileMenuOpen(true)}
        >
          <Menu className="w-6 h-6" />
        </Button>
      </div>

      {/* Mobile Menu */}
      <AnimatePresence>
        {isMobileMenuOpen && (
          <motion.div>
            <div className="absolute inset-0 bg-background/80" onClick={() => setIsMobileMenuOpen(false)} />
            <motion.div
              className="absolute right-0 top-0 bottom-0 w-80 bg-card"
              initial={{ x: '100%' }}
              animate={{ x: 0 }}
              exit={{ x: '100%' }}
            >
              <div className="p-4 flex justify-end">
                <Button variant="ghost" size="icon" onClick={() => setIsMobileMenuOpen(false)}>
                  <X className="w-6 h-6" />
                </Button>
              </div>
              <nav className="flex flex-col p-4 gap-2">
                {navLinks.map((link) => (
                  <Link
                    key={link.href}
                    href={link.href}
                    className={cn(
                      "block px-4 py-3 rounded-lg text-lg",
                      pathname === link.href ? "bg-primary/10 text-primary" : "hover:bg-secondary"
                    )}
                  >
                    {link.label}
                  </Link>
                ))}
              </nav>
            </motion.div>
          </motion.div>
        )}
      </AnimatePresence>
    </motion.header>
  )
}
```

## Skills Section

```jsx
// src/app/skills/page.tsx
'use client'

import { useState } from 'react'
import { motion, AnimatePresence } from 'framer-motion'
import { Code2, Palette, Database, GitBranch, Cpu, Layers, Zap, Box, Gamepad2, Workflow, Brain, Languages } from 'lucide-react'
import { Navigation } from '@/components/sections/Navigation'
import { Footer } from '@/components/sections/Footer'
import { cn } from '@/lib/utils'

const skillCategories = [
  {
    id: "engines",
    name: "Game Engines",
    icon: Gamepad2,
    skills: [
      { name: "Unity", level: 95 },
      { name: "Unreal Engine 5", level: 85 },
      { name: "Godot", level: 80 },
    ],
  },
  {
    id: "languages",
    name: "Programming Languages",
    icon: Code2,
    skills: [
      { name: "C#", level: 95 },
      { name: "C++", level: 85 },
      { name: "GDScript", level: 75 },
    ],
  },
  // More categories...
]

export default function SkillsPage() {
  const [activeCategory, setActiveCategory] = useState("engines")

  const activeSkills = skillCategories.find((c) => c.id === activeCategory)

  return (
    <div className="min-h-screen bg-background">
      <Navigation />
      <main className="pt-24 pb-12">
        <div className="container px-4">
          <h1 className="text-4xl md:text-6xl font-bold mb-6">
            Skills & <span className="gradient-text">Expertise</span>
          </h1>
          
          {/* Category Filter */}
          <div className="flex flex-wrap gap-3 mb-12">
            {skillCategories.map((category) => (
              <button
                key={category.id}
                onClick={() => setActiveCategory(category.id)}
                className={cn(
                  "flex items-center gap-2 px-4 py-2 rounded-lg",
                  activeCategory === category.id ? "bg-primary text-white" : "bg-secondary/50"
                )}
              >
                <category.icon className="w-4 h-4" />
                {category.name}
              </button>
            ))}
          </div>

          {/* Skills Display */}
          <AnimatePresence mode="wait">
            <motion.div
              key={activeCategory}
              initial={{ opacity: 0, y: 20 }}
              animate={{ opacity: 1, y: 0 }}
              exit={{ opacity: 0, y: -20 }}
              className="glass-card rounded-2xl p-8"
            >
              {activeSkills?.skills.map((skill, index) => (
                <div key={skill.name} className="mb-4">
                  <div className="flex justify-between mb-1">
                    <span className="font-medium">{skill.name}</span>
                    <span className="text-muted-foreground">{skill.level}%</span>
                  </div>
                  <div className="h-2 bg-secondary/50 rounded-full overflow-hidden">
                    <motion.div
                      className="h-full bg-primary rounded-full"
                      initial={{ width: 0 }}
                      animate={{ width: `${skill.level}%` }}
                      transition={{ duration: 0.8, delay: index * 0.1 }}
                    />
                  </div>
                </div>
              ))}
            </motion.div>
          </AnimatePresence>
        </div>
      </main>
      <Footer />
    </div>
  )
}
```

---

# Chapter 12 — Dynamic Project Pages

## Dynamic Routes

Dynamic routes let us create pages programmatically:

```
src/app/projects/[slug]/
└── page.tsx
```

The `[slug]` folder name makes it dynamic.

## Getting the Slug

```jsx
'use client'

import { useParams } from 'next/navigation'

export default function ProjectPage() {
  const params = useParams()
  const slug = params.slug
  
  return <h1>Project: {slug}</h1>
}
```

## Loading Project Data

```typescript
// src/data/projects.ts
export interface Project {
  id: string
  slug: string
  title: string
  description: string
  thumbnail: string
  tags: string[]
  engine: string
  // More fields...
}

export const projects: Project[] = [
  {
    id: "1",
    slug: "nebula-wars",
    title: "Nebula Wars",
    description: "A fast-paced space shooter...",
    // ...
  },
]

export function getProjectBySlug(slug: string): Project | undefined {
  return projects.find((p) => p.slug === slug)
}
```

## Complete Project Page

```jsx
// src/app/projects/[slug]/page.tsx
'use client'

import { useParams, notFound } from 'next/navigation'
import { motion } from 'framer-motion'
import Link from 'next/link'
import { ExternalLink, Calendar, Users, Gamepad2, Layers, Cpu, Zap, ChevronRight } from 'lucide-react'
import { Button } from '@/components/ui/button'
import { Navigation } from '@/components/sections/Navigation'
import { Footer } from '@/components/sections/Footer'
import { getProjectBySlug, projects } from '@/data/projects'

export default function ProjectDetailPage() {
  const params = useParams()
  const slug = params?.slug as string
  const project = getProjectBySlug(slug)

  if (!project) {
    notFound()
  }

  const currentIndex = projects.findIndex((p) => p.slug === slug)
  const nextProject = projects[(currentIndex + 1) % projects.length]
  const prevProject = projects[(currentIndex - 1 + projects.length) % projects.length]

  return (
    <div className="min-h-screen bg-background">
      <Navigation />
      <main className="pt-24">
        {/* Hero */}
        <section className="relative">
          <div className="h-[50vh] min-h-[400px] bg-secondary/50 flex items-center justify-center">
            <motion.div
              initial={{ opacity: 0, y: 30 }}
              animate={{ opacity: 1, y: 0 }}
              transition={{ duration: 0.6 }}
              className="text-center"
            >
              <h1 className="text-4xl md:text-6xl font-bold mb-4">
                {project.title}
              </h1>
              <p className="text-xl text-muted-foreground">
                {project.shortDescription}
              </p>
            </motion.div>
          </div>
        </section>

        {/* Project Info */}
        <section className="py-12">
          <div className="container px-4">
            <div className="grid md:grid-cols-4 gap-6">
              <div className="glass-card rounded-xl p-4 text-center">
                <Gamepad2 className="w-8 h-8 mx-auto mb-2 text-primary" />
                <p className="text-sm text-muted-foreground">Engine</p>
                <p className="font-semibold">{project.engine}</p>
              </div>
              <div className="glass-card rounded-xl p-4 text-center">
                <Layers className="w-8 h-8 mx-auto mb-2 text-primary" />
                <p className="text-sm text-muted-foreground">Genre</p>
                <p className="font-semibold">{project.genre}</p>
              </div>
              <div className="glass-card rounded-xl p-4 text-center">
                <Calendar className="w-8 h-8 mx-auto mb-2 text-primary" />
                <p className="text-sm text-muted-foreground">Duration</p>
                <p className="font-semibold">{project.duration}</p>
              </div>
              <div className="glass-card rounded-xl p-4 text-center">
                <Users className="w-8 h-8 mx-auto mb-2 text-primary" />
                <p className="text-sm text-muted-foreground">Team Size</p>
                <p className="font-semibold">{project.teamSize}</p>
              </div>
            </div>
          </div>
        </section>

        {/* Description */}
        <section className="py-12">
          <div className="container px-4">
            <h2 className="text-2xl md:text-3xl font-bold mb-6">Overview</h2>
            <div className="glass-card rounded-2xl p-8">
              <p className="text-lg text-muted-foreground leading-relaxed">
                {project.description}
              </p>
            </div>
          </div>
        </section>

        {/* Features */}
        <section className="py-12">
          <div className="container px-4">
            <h2 className="text-2xl md:text-3xl font-bold mb-6">Features</h2>
            <div className="grid md:grid-cols-2 gap-4">
              {project.features.map((feature, index) => (
                <motion.div
                  key={index}
                  initial={{ opacity: 0, x: -20 }}
                  animate={{ opacity: 1, x: 0 }}
                  transition={{ delay: index * 0.1 }}
                  className="glass-card rounded-xl p-4 flex items-start gap-3"
                >
                  <Zap className="w-5 h-5 text-primary shrink-0 mt-0.5" />
                  <span>{feature}</span>
                </motion.div>
              ))}
            </div>
          </div>
        </section>

        {/* Navigation */}
        <section className="py-12 border-t border-border">
          <div className="container px-4">
            <div className="flex justify-between">
              <Link href={`/projects/${prevProject.slug}`}>
                <Button variant="ghost">
                  <ChevronRight className="w-5 h-5 mr-2 rotate-180" />
                  Previous
                </Button>
              </Link>
              <Link href="/projects">
                <Button variant="ghost">All Projects</Button>
              </Link>
              <Link href={`/projects/${nextProject.slug}`}>
                <Button variant="ghost">
                  Next
                  <ChevronRight className="w-5 h-5 ml-2" />
                </Button>
              </Link>
            </div>
          </div>
        </section>
      </main>
      <Footer />
    </div>
  )
}
```

---

# Chapter 13 — SEO + Metadata

Next.js has built-in SEO support through the Metadata API.

## Basic Metadata

```typescript
// src/app/layout.tsx
import type { Metadata } from 'next'

export const metadata: Metadata = {
  title: 'Game Developer Portfolio',
  description: 'Professional game developer specializing in gameplay programming',
}
```

## Open Graph

```typescript
export const metadata: Metadata = {
  title: 'Game Developer Portfolio',
  description: 'Professional game developer specializing in gameplay programming',
  openGraph: {
    title: 'Game Developer Portfolio',
    description: 'Building immersive gaming experiences',
    type: 'website',
  },
}
```

## Dynamic Metadata for Projects

```typescript
// src/app/projects/[slug]/page.tsx
import { getProjectBySlug, projects } from '@/data/projects'
import type { Metadata } from 'next'

export function generateStaticParams() {
  return projects.map((project) => ({
    slug: project.slug,
  }))
}

export async function generateMetadata({ 
  params 
}: { 
  params: Promise<{ slug: string }> 
}): Promise<Metadata> {
  const { slug } = await params
  const project = getProjectBySlug(slug)
  
  if (!project) {
    return { title: 'Project Not Found' }
  }
  
  return {
    title: `${project.title} | Game Developer Portfolio`,
    description: project.shortDescription,
    openGraph: {
      title: project.title,
      description: project.shortDescription,
      type: 'website',
    },
  }
}
```

---

# Chapter 14 — Performance Optimization

## Lazy Loading

Dynamically import components to reduce initial bundle size:

```typescript
import dynamic from 'next/dynamic'

const DynamicHero3D = dynamic(() => import('./Hero3D'), { 
  ssr: false 
})
```

This loads the 3D scene only on the client.

## Images

Use Next.js Image for automatic optimization:

```typescript
import Image from 'next/image'

<Image 
  src="/project.jpg"
  alt="Project screenshot"
  width={800}
  height={600}
/>
```

## Code Splitting

Next.js automatically code-splits by route. Use dynamic imports for large components:

```typescript
// Only load heavy component when needed
const HeavyComponent = dynamic(() => import('./HeavyComponent'))
```

---

# Chapter 15 — Responsive Design

Use Tailwind's responsive prefixes:

```jsx
<div className="
  grid-cols-1    // Mobile
  md:grid-cols-2  // Tablet  
  lg:grid-cols-3    // Desktop
">
```

### Common Breakpoints

| Breakpoint | Width | Use |
|-----------|-------|-----|
| Default | < 640px | Mobile |
| sm: | 640px | Large phones |
| md: | 768px | Tablets |
| lg: | 1024px | Laptops |
| xl: | 1280px | Desktops |

---

# Chapter 16 — Smooth Scroll + UX

Lenis provides smooth, momentum-based scrolling:

```typescript
// src/hooks/useSmoothScroll.ts
'use client'

import { useEffect, useRef } from 'react'
import Lenis from 'lenis'

export function useSmoothScroll() {
  const lenisRef = useRef<Lenis | null>(null)

  useEffect(() => {
    const lenis = new Lenis({
      duration: 1.2,
      easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
      smoothWheel: true,
    })

    lenisRef.current = lenis

    function raf(time: number) {
      lenis.raf(time)
      requestAnimationFrame(raf)
    }

    requestAnimationFrame(raf)

    return () => {
      lenis.destroy()
    }
  }, [])

  return lenisRef
}
```

---

# Chapter 17 — Dark Theme Design System

Our color palette:

```css
:root {
  /* Background */
  --background: #0B0F19;
  --foreground: #ffffff;
  
  /* Cards */
  --card: #121829;
  --card-foreground: #ffffff;
  
  /* Primary accent (purple) */
  --primary: #8B5CF6;
  --primary-foreground: #ffffff;
  
  /* Secondary accent (cyan) */
  --accent: #06B6D4;
  --accent-foreground: #ffffff;
  
  /* Muted */
  --muted: #1E293B;
  --muted-foreground: #94A3B8;
  
  /* Borders */
  --border: #1E293B;
}
```

### Gaming Aesthetic Tips

1. **Dark background** — Reduces eye strain, popular in gaming
2. **Purple accent** — Associated with creativity and gaming
3. **Cyan accent** — Associated with technology and sci-fi
4. **Neon glow** — Creates depth and atmosphere
5. **Glassmorphism** — Modern, premium feel

---

# Chapter 18 — Data Driven Portfolio

Centralize your data:

```typescript
// src/data/projects.ts
export interface Project {
  id: string
  slug: string
  title: string
  description: string
  shortDescription: string
  thumbnail: string
  tags: string[]
  engine: string
  platform: string
  genre: string
}

export const projects: Project[] = [
  {
    id: "1",
    slug: "nebula-wars",
    title: "Nebula Wars",
    description: "A fast-paced space shooter...",
    shortDescription: "Fast-paced space shooter",
    tags: ["Action", "Multiplayer"],
    engine: "Unity",
    // ...
  },
]

export function getProjectBySlug(slug: string) {
  return projects.find((p) => p.slug === slug)
}
```

Then import it wherever needed:

```typescript
import { projects, getProjectBySlug } from '@/data/projects'
```

---

# Chapter 19 — Deployment Guide

## Deploying to Vercel

1. Push your code to GitHub
2. Go to https://vercel.com
3. Import your repository
4. Vercel auto-deploys on every push

## Environment Variables

Create a `.env.local` file:

```env
NEXT_PUBLIC_SITE_URL=https://your-domain.com
```

---

# Chapter 20 — Common Errors and Fixes

## Hydration Errors

**Error:** "Text content does not match server-rendered HTML"

**Cause:** Different content on server vs client

**Fix:** Use `suppressHydrationWarning` or ensure consistent data:

```tsx
<div suppressHydrationWarning>
  {new Date().toLocaleTimeString()}
</div>
```

## Import Errors

**Error:** "Module not found"

**Cause:** Wrong import path

**Fix:** Check your paths and aliases:

```typescript
// Instead of
import { Button } from '../components/ui/button'

// Use
import { Button } from '@/components/ui/button'
```

## Type Errors

**Error:** TypeScript errors

**Cause:** Type mismatches

**Fix:** Add proper types:

```typescript
// Instead of
const [count, setCount] = useState(0)

// Add type
const [count, setCount] = useState<number>(0)
```

---

# Chapter 21 — Exercises and Practice

## Beginner Exercises

1. Create a new Next.js project
2. Add a new page with navigation
3. Style a component with Tailwind
4. Add a button with hover effects
5. Create a simple layout

## Intermediate Tasks

1. Add Framer Motion animations
2. Create a project filter
3. Build a contact form
4. Add responsive design
5. Implement dark/light theme

## Advanced Challenges

1. Add 3D elements with R3F
2. Create a custom smooth scroll
3. Build dynamic project routes
4. Add SEO metadata
5. Deploy to production

---

# Chapter 22 — Final Roadmap

Here's your learning path:

```
Beginner
    ↓
HTML & CSS Fundamentals
    ↓
JavaScript Basics
    ↓
React Fundamentals
    ↓
Next.js App Router
    ↓
Tailwind CSS
    ↓
Framer Motion
    ↓
Portfolio Project
    ↓
Professional Game Dev Portfolio
```

---

# Conclusion

You now have all the knowledge to build a professional game developer portfolio. Start small, iterate, and keep learning. The best portfolio is one that exists—get building!

Remember:
- **Start simple** — Don't try to build everything at once
- **Iterate** — Add features one at a time
- **Learn by doing** — Build, break, fix, repeat
- **Ask questions** — If something doesn't make sense, search or ask

Your journey from beginner to professional game developer portfolio starts now. Good luck!