# gflab.r-universe.dev

Registry for the [r-universe](https://r-universe.dev) builds of FengGao Lab R
packages. r-universe builds each package from source and checks it on Linux,
macOS, and Windows across R-release and R-devel, then serves binaries so users
install without a compiler.

Built packages are online at **<https://gflab.r-universe.dev>**.

## Packages

| Package | Source | Universe page | Status |
| --- | --- | --- | --- |
| `gfplot` | [gflab/gfplot](https://github.com/gflab/gfplot) | <https://gflab.r-universe.dev/gfplot> | [![checks](https://gflab.r-universe.dev/gfplot/badges/checks)](https://gflab.r-universe.dev/gfplot) |
| `clinstats` | [gflab/clinstats](https://github.com/gflab/clinstats) | <https://gflab.r-universe.dev/clinstats> | [![checks](https://gflab.r-universe.dev/clinstats/badges/checks)](https://gflab.r-universe.dev/clinstats) |

## Installing

```r
install.packages(
  c("gfplot", "clinstats"),
  repos = c(gflab = "https://gflab.r-universe.dev", CRAN = "https://cloud.r-project.org")
)
```

This downloads a prebuilt binary, so no compiler is needed.

The GitHub route keeps working and is unchanged:

```r
remotes::install_github("gflab/gfplot")
remotes::install_github("gflab/clinstats")
```

## Editing

`packages.json` lists the repositories to build. Add an entry and push; the
next build picks it up. Set `"branch"` for a repository whose default branch
is not `main`, as `gfplot` does. This repository holds no package source.

Builds run in [r-universe/gflab](https://github.com/r-universe/gflab), which
the R-universe GitHub App maintains.

## Why the checks matter

The R-universe matrix is wider than a single CI run: R-devel on Linux and
Windows, R-release on three platforms, R-oldrel binaries, and a WebAssembly
build. It caught a provenance test that asserted the R version string in its
release wording, which fails on R-devel and would otherwise have surfaced at
the next R release.
