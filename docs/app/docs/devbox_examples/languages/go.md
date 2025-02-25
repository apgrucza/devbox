---
title: Go
---

Go projects can be run in Devbox by adding the Go SDK to your project. If your project uses cgo or compiles against C libraries, you should also include them in your packages to ensure Go can compile successfully

[**Example Repo**](https://github.com/jetpack-io/devbox/tree/main/examples/development/go/hello-world)

[![Open In Devbox.sh](https://jetpack.io/img/devbox/open-in-devbox.svg)](https://devbox.sh/new?template=go)

## Adding Go to your Project

`devbox add go`, or add the following to your `devbox.json`

```json
  "packages": [
    "go@latest"
  ]
```

This will install the latest version of the Go SDK. You can find other installable versions of Go by running `devbox search go`.

If you need additional C libraries, you can add them along with `gcc` to your package list. For example, if libcap is required for yoru project:

```json
"packages": [
    "go",
    "gcc",
    "libcap"
]
