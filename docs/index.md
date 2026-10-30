# RegexTester.dev Documentation

[RegexTester.dev](https://regextester.dev/) is a free online regex tester that runs **real regex engines in your browser via WebAssembly**: PCRE2, RE2, ECMAScript, Python, Go, Java, .NET, and Rust.

No sign-up, no cookies, no server round-trips for matching — every engine is the actual library compiled to WASM, so behavior matches the real thing, edge cases included.

## What's inside

- [Flavor Matrix](flavor-matrix.md) — which flavor supports lookbehind, atomic groups, recursion, `\K`
- [Testing Workflow](workflow.md) — how to test one pattern across all eight engines
- [ReDoS Safety](redos.md) — why linear-time engines (RE2/Go/Rust) can't blow up

## Quick links

- [Online tester](https://regextester.dev/) — all 8 engines side by side
- [Compatibility checker](https://regextester.dev/compat) — cross-flavor difference report for your pattern
- [AI regex generator](https://regextester.dev/ai-regex-generator)
- [Community pattern gallery](https://regextester.dev/gallery) — 14,000+ real-world patterns
