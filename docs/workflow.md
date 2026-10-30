# Testing Workflow

1. Paste your pattern and sample text into [RegexTester.dev](https://regextester.dev/)
2. Read the per-engine result columns — a pattern that matches in Python but fails to compile in Go is visible instantly
3. Run the [compatibility checker](https://regextester.dev/compat) for a construct-by-construct difference report
4. Benchmark before optimizing — the same pattern can be 50x slower in one engine than another; P95/P99 timings across engines are built in
5. Share findings with a permalink — pattern, flags, and test text are encoded in the URL

## Checklist before shipping a pattern to another language

- [ ] Same escape semantics? (`\d` vs `\p{Nd}` under Unicode)
- [ ] Lookbehind width rules differ (variable/fixed/bounded/none)
- [ ] Named group syntax (`(?<n>)` vs `(?P<n>)`)
- [ ] Case-insensitive Unicode folding?
- [ ] Catastrophic backtracking risk on user input?
