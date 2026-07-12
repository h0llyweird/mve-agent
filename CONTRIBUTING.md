# Contributing to MVE Agent

This guide exists to save both sides time.

## The One Rule

**You must understand your code.** If you cannot explain what your changes do and how they interact with the rest of the system, your PR will be closed.

Using AI to write code is fine. Submitting AI-generated slop without understanding it is not.

If you use an agent, run it from the `mve-agent` root directory so it picks up `AGENTS.md` automatically. Your agent must follow the rules and guidelines in that file.

## Before Submitting a PR

Before submitting a PR:

```bash
npm run check
./test.sh
```

Both must pass.

Do not edit `CHANGELOG.md`. Changelog entries are added by maintainers.

If you are adding a new provider to `packages/ai`, see `AGENTS.md` for required tests.

## Philosophy

MVE Agent's core is minimal. If your feature does not belong in the core, it should be an extension. PRs that bloat the core will likely be rejected.

## Questions?

Open an issue on GitHub.