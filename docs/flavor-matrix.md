# Regex Flavor Matrix

Which regex flavor supports lookbehind, atomic groups, possessive quantifiers, backreferences, recursion or `\K`?

| Feature | PCRE2 | RE2 | JavaScript | Python | Go | Java | .NET | Rust |
|---|---|---|---|---|---|---|---|---|
| Lookahead | yes | no | yes | yes | no | yes | yes | no |
| Lookbehind | variable | no | variable (ES2018) | fixed | no | bounded | variable | no |
| Backreferences | yes | no | yes | yes | no | yes | yes | no |
| Named groups | `(?<n>…)` | `(?P<n>…)` | `(?<n>…)` | `(?P<n>…)` | `(?P<n>…)` | `(?<n>…)` | `(?<n>…)` | `(?P<n>…)` |
| Atomic groups | yes | no | no | 3.11+ | no | yes | .NET 7+ | no |
| Possessive quantifiers | yes | no | no | 3.11+ | no | yes | no | no |
| Recursion `(?R)` | yes | no | no | no | no | no | no* | no |
| Unicode `\p{L}` | yes | yes | `u` flag | yes | yes | yes | yes | yes |
| Free-spacing `(?x)` | yes | yes | no | yes | yes | yes | yes | yes |
| `\K` | yes | no | no | no | no | no | no | no |
| Linear-time guarantee | no | yes | no | no | yes | no | partial | yes |

*.NET has balancing groups covering some recursion use cases.

Verify any cell yourself with the [8-engine tester](https://regextester.dev/) or the per-flavor testers: [PCRE2](https://regextester.dev/pcre2-regex-tester), [RE2](https://regextester.dev/re2-regex-tester), [JavaScript](https://regextester.dev/javascript-regex-tester), [Python](https://regextester.dev/python-regex-tester), [Go](https://regextester.dev/go-regex-tester), [Java](https://regextester.dev/java-regex-tester), [.NET](https://regextester.dev/dotnet-regex-tester), [Rust](https://regextester.dev/rust-regex-tester).
