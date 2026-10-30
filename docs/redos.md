# ReDoS Safety

Catastrophic backtracking: patterns like `(a+)+$` against a long non-matching string make backtracking engines (PCRE2, JavaScript, Python, Java, .NET) explore an exponential number of paths.

Linear-time engines (RE2, Go `regexp`, Rust `regex`) compile patterns to finite automata and guarantee O(n) — they cannot blow up, but they don't support backreferences or lookarounds at all.

## Rules of thumb

- User-supplied patterns on a server? Use a linear-time engine, or wrap backtracking engines with a timeout (.NET `MatchTimeout`, Java `InterruptedException` handling, RE2 wrapper for Python).
- Own patterns only? Any engine, but unroll nested quantifiers: `aab+` style expansions, atomic groups `(?>...)` where available.
- Test the pathological input yourself: the classic `(a+)+$` vs `aaaaaaaaaaaaaaaaaaaaaaaaaaab` — see it hang in one engine and return instantly in another at [RegexTester.dev](https://regextester.dev/).
