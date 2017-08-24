# geen

a high performance, lightweight and composable package for building HTTP services.

`geen` is a high performance, lightweight and composable package for building HTTP services. It's
especially good at helping you write large REST API services that are kept maintainable as your
project grows and changes.

## Install

`go get -u github.com/geego/geen`

## Examples

See [examples](https://github.com/geego/example) for a variety of examples.

```go
package main

import (
  "net/http"

  "github.com/geego/geen"
  "github.com/geego/middleware"
)

func main() {
  r := geen.NewRouter()
  r.Use(middleware.Logger)
  r.Get("/", func(w http.ResponseWriter, r *http.Request) {
    w.Write([]byte("welcome"))
  })
  http.ListenAndServe(":3000", r)
}
```

## License

Inspired by `chi` and under [MIT License](./LICENSE)
