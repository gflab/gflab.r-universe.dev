# gflab.r-universe.dev

Registry for the [r-universe](https://r-universe.dev) builds of FengGao Lab R
packages. r-universe builds each package from source on Linux, macOS, and
Windows and serves the binaries, so users install without a compiler.

## Packages

| Package | Source | Universe page |
| --- | --- | --- |
| `gfplot` | [gflab/gfplot](https://github.com/gflab/gfplot) | https://gflab.r-universe.dev/gfplot |
| `clinstats` | [gflab/clinstats](https://github.com/gflab/clinstats) | https://gflab.r-universe.dev/clinstats |

## Installing

```r
install.packages(
  c("gfplot", "clinstats"),
  repos = c("https://gflab.r-universe.dev", "https://cloud.r-project.org")
)
```

The GitHub route keeps working and is unchanged:

```r
remotes::install_github("gflab/gfplot")
remotes::install_github("gflab/clinstats")
```

## Editing

`packages.json` lists the repositories to build. Add an entry and push; the
next build picks it up. Set `"branch"` for a repository whose default branch
is not `main`. This repository holds no package source.
