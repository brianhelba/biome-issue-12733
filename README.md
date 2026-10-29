# Reproduction for biomejs/biome#12733

Configuring any lint rule disables dependency-based domain detection.

```sh
npm ci
npm run lint
```

Expected: `lint/suspicious/noFocusedTests` is reported on `a.test.ts`, because the `vitest` dependency enables the `test` domain.

Actual: nothing is reported.

Replace the contents of `biome.json` with `{}` and run `npm run lint` again: the diagnostic is reported.
