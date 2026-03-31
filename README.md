# HemenHesap.com

Public architecture showcase for `hemenhesap.com`, a cloud-native calculation platform built for speed, SEO, and scalable feature growth.

## Impact

- Used by 500+ users through organic traffic
- Reduced infrastructure costs by around 70 percent after moving deployment from Vercel to an AWS-centered setup
- Expanded into a platform with 80+ calculator pages and 20+ supporting content pieces
- Designed for fast page delivery, modular feature growth, and low operational overhead
- Built with a production mindset around CI/CD, infrastructure automation, and security controls

## What This Repository Contains

This repository is a public case study, not the full private production codebase.

It includes:

- a high-level architecture overview
- representative folder structure for the application
- infrastructure references such as [infra/cloudformation.yaml](./infra/cloudformation.yaml)
- project metadata that reflects the production application shape

It does not include:

- the private production source code
- secrets, credentials, or internal business logic

## What The Product Covers

In production, HemenHesap is more than a single calculator site.

It includes:

- a growing library of calculator pages across finance, tax, daily life, and work-related use cases
- supporting blog and explainer content for SEO and search intent coverage
- search and discovery flows that help users reach the right tool faster
- internal admin capabilities used to manage and expand content more efficiently
- analytics and operational tooling used to monitor platform behavior

## System Overview

HemenHesap is built as a modular monolith with a strong separation between application routing, feature-level business logic, shared building blocks, and infrastructure adapters.

Key design goals:

- keep feature development fast as the number of calculators grows
- avoid circular dependencies and tightly coupled feature modules
- support programmatic SEO and high page coverage without manual page creation
- keep runtime costs low while maintaining production-grade deployment practices

More architectural detail is available in [ARCHITECTURE.md](./ARCHITECTURE.md).

## Architecture Highlights

### Modular monolith with Feature-Sliced Design

The application follows a layered structure built around feature ownership. New tools and pages can be added with minimal cross-module impact, which keeps the codebase maintainable as the platform expands.

### Search and discovery

The platform supports intent-aware discovery for calculation tools through embeddings and vector-based retrieval, with fallback paths for text search and static mappings.

### Programmatic SEO

Thousands of dynamic, SEO-focused pages can be served through build-time generation and ISR-style delivery patterns. Structured data and FAQ schemas are generated automatically for relevant tools.

### Build and content workflow

The platform is designed so that adding new tools does not require manual updates across many files.

In practice, the build workflow helps keep:

- calculator listings
- search data
- navigation structures
- supporting content files
- metadata used for discoverability

in sync as the platform grows.

## Cloud and Delivery

The application layer uses modern web tooling and managed services, while deployment and infrastructure control were optimized around AWS.

- application: Next.js 16, React 19, TypeScript
- data layer: Supabase PostgreSQL
- caching and rate limiting: Upstash Redis
- deployment: AWS Amplify
- infrastructure as code: AWS CloudFormation
- delivery workflow: GitHub-based CI/CD and automated production deployment

This setup keeps the app operationally lightweight while still giving strong control over deployment, domain management, and production configuration.

## Security and Reliability

- IAM least-privilege access for infrastructure and service integration
- HTTPS enforcement and managed custom domain setup
- Redis-based rate limiting for abuse protection
- environment-driven configuration for safer secret handling
- architecture designed to reduce coupling and operational risk
- test and lint workflows used to catch issues before deployment

## Performance

- Lighthouse performance score: 98-100
- TTFB: under 100 ms
- CLS: 0

The platform was designed with performance as a product requirement, not an afterthought.

## Tech Stack

- Frontend: Next.js, React, Tailwind CSS, Recharts, React Leaflet
- Backend and platform: TypeScript, NextAuth, Supabase, Upstash Redis
- AI and data workflows: OpenAI embeddings, vector search, Python-based data tooling
- DevOps and cloud: AWS Amplify, CloudFormation, GitHub Actions, Docker

## Live Project

- Production: https://hemenhesap.com
