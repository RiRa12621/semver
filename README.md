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

## Usage

Install the package:

```sh
go get github.com/RiRa12621/semver
```

Use it from Go:

```go
package main

import (
	"fmt"

	"github.com/RiRa12621/semver"
)

func main() {
	fmt.Println(semver.IsValid("1.2.3"))
	fmt.Println(semver.Compare("1.2.3", "1.3.0"))
	fmt.Println(semver.Canonical("1.2"))
}
```

## Releases

Pushes to `main` run the full Go test workflow and then publish a GitHub
release when the commits since the last release contain release-worthy
Conventional Commit messages:

- `fix:` or `perf:` creates a patch release.
- `feat:` creates a minor release.
- `type!:` or a `BREAKING CHANGE:` footer creates a major release.

Release tags use Go-compatible SemVer tags such as `v1.2.3`; this does not
change the package behavior described above.
