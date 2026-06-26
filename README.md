# semver

This repository is a small clone of the `semver` package from
[`golang.org/x/mod`](https://cs.opensource.google/go/x/mod/).

The only intended difference is that this package works with semantic version
strings without the leading `v` prefix used by the upstream package.

For example, use:

```text
1.2.3
```

instead of:

```text
v1.2.3
```
