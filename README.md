# French Practice App

## Current health check

The repository now includes an initialized project layout (apps/packages/services/infra/tests/workflows) plus this README, but still no configured lint/build/test tooling yet.  
Because of that, there are no failing checks to fix at this time.

## Suggested SOTA layout for this app

For a modern French practice app, use a feature-first structure with clear domain boundaries:

```text
french-practice-app/
├─ apps/
│  └─ web/                    # Frontend app (Next.js + TypeScript)
├─ packages/
│  ├─ ui/                     # Reusable design-system components
│  ├─ features/
│  │  ├─ vocab/               # Vocabulary training flows
│  │  ├─ grammar/             # Grammar lessons/exercises
│  │  ├─ listening/           # Audio-based practice
│  │  └─ speaking/            # Pronunciation/speaking practice
│  ├─ core/                   # Shared business logic (spaced repetition, scoring)
│  ├─ api-client/             # Typed API layer
│  └─ config/                 # Shared eslint/tsconfig/prettier/jest/vitest config
├─ services/
│  └─ api/                    # Backend service (REST/GraphQL)
├─ infra/
│  ├─ docker/                 # Containers
│  └─ terraform/              # Cloud/IaC (optional)
├─ tests/
│  ├─ e2e/
│  └─ performance/
└─ .github/workflows/         # CI: lint, typecheck, test, build, security scan
```

### Why this is SOTA

- **Feature-first modules** keep product work fast and maintainable as the app grows.
- **Shared packages** prevent duplication and enforce consistency.
- **Typed boundaries** (TypeScript + typed API client) reduce runtime bugs.
- **Dedicated CI/security workflows** keep quality high from day one.
