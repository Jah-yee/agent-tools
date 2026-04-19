# Contributing to Agent Tools

Thank you for your interest in contributing! This project is part of the [GitTensor](https://gittensor.io) ecosystem (Bittensor Subnet 74). Quality contributions can earn TAO rewards.

## Getting Started

1. **Fork** the repository
2. **Clone** your fork: `git clone https://github.com/<your-username>/agent-tools.git`
3. **Install** dependencies: `npm install`
4. **Build** all packages: `npm run build`
5. **Test** all packages: `npm run test`

## Finding Work

- Browse [open issues](../../issues) for bugs, features, and tool requests
- Issues labeled `good first issue` are great starting points
- Issues labeled `help wanted` need contributors
- Feel free to propose new tools by opening an issue first

## Pull Request Process

1. **One PR per issue.** Keep changes focused and reviewable.
2. **Branch from `main`.** Name your branch descriptively: `feat/tool-name`, `fix/issue-description`.
3. **Write tests.** Every new function needs tests. Every bug fix needs a regression test.
4. **Run checks locally** before submitting:
   ```bash
   npm run build
   npm run test
   npm run typecheck
   ```
5. **Write a clear PR description.** Explain what changed and why. Reference the issue number.
6. **Keep commits clean.** Squash WIP commits. Use clear commit messages.

### Immutable PR Policy

**PRs are reviewed exactly once, as submitted. This is non-negotiable.**

- When you open a PR, that snapshot is what gets reviewed — merge or close, no middle ground.
- **Any additional commits pushed after opening will auto-close your PR.**
- There is no back-and-forth iteration. No "can you fix this one thing." If the PR isn't ready, it gets closed.
- To iterate: close the old PR, fix your code, open a new one.

**Why?** This keeps reviews fast, fair, and honest. It forces you to test thoroughly before submitting. It prevents gaming through incremental fixes. Ship it right or ship it again.

**Before you open your PR, make sure:**
- All tests pass (`npm test`)
- Types check (`npm run typecheck`)
- Build succeeds (`npm run build`)
- You've manually verified your code works
- Your PR description is complete

## Code Style

- TypeScript with strict mode
- No `any` types unless absolutely necessary (and documented why)
- Functions should have explicit return types
- Prefer `const` over `let`
- Use descriptive variable names — no single-letter variables outside of loop counters
- No comments explaining *what* — only *why* when non-obvious

## Package Structure

Every package follows this structure:

```
packages/<tool-name>/
├── package.json
├── tsconfig.json
├── README.md
├── src/
│   ├── index.ts          # Public API exports
│   ├── <module>.ts       # Implementation
│   └── __tests__/
│       └── <module>.test.ts
```

### package.json Template

```json
{
  "name": "@agent-tools/<tool-name>",
  "version": "0.1.0",
  "description": "<one-line description>",
  "main": "dist/index.js",
  "types": "dist/index.d.ts",
  "files": ["dist"],
  "scripts": {
    "build": "tsc",
    "test": "node --test src/__tests__/*.test.ts",
    "typecheck": "tsc --noEmit"
  }
}
```

## Quality Standards

- **Tests must pass.** No exceptions.
- **Type-check must pass.** No `@ts-ignore` without explanation.
- **No unnecessary dependencies.** If you can implement it in 50 lines, don't add a dependency.
- **API must be agent-friendly.** Clear function signatures, predictable returns, no ambiguous options.

## Code of Conduct

Be respectful, constructive, and collaborative. We're building tools that help everyone. Harassment, trolling, or unconstructive criticism will not be tolerated.

## Questions?

Open an issue with the `question` label or start a discussion.
