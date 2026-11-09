# ship

tests, checks, and deploys.

### [vitest](https://vitest.dev)
unit and integration tests.
- **shipped in**: parc, tetraslamworld, decision-twins

### [convex-test](https://www.npmjs.com/package/convex-test)
runs convex functions in tests. test permissions through the real rls wrapper and real auth sessions, not mocked policy outcomes.
- **shipped in**: parc, tetraslamworld

### [react doctor](https://www.react.doctor)
catches the bad react agents tend to write. treat its findings as leads to check, not a score to max out, and write down the exceptions you've reviewed.
- **shipped in**: parc

### [vercel](https://vercel.com) + [vercel analytics](https://vercel.com/analytics)
hosting for next apps, with preview deploys, plus privacy-friendly analytics.
- **watch out**: deploy convex separately (`pnpm exec convex deploy`), and make sure each vercel environment points at the matching convex deployment.
- **shipped in**: parc, tetraslamworld, softmax, damnbruh-website

## the check list

ci and agents both run this before calling something done:

```sh
pnpm lint        # biome check
pnpm typecheck   # tsc --noEmit (next typegen first on next apps)
pnpm test
pnpm build
pnpm audit --prod --audit-level high
```
