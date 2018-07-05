# An asynchronous MongoDB Hook for [Logrus](https://github.com/sirupsen/logrus)

[![ReportCard][reportcard-image]][reportcard-url] [![GoDoc][godoc-image]][godoc-url] [![License][license-image]][license-url]

## Quick Start

### Download and install

```bash
$ go get -u -v github.com/LyricTian/logrus-mongo-hook
```

### Usage

```go
package main

import (
    "github.com/LyricTian/logrus-mongo-hook"
    "github.com/globalsign/mgo"
)

func main() {
    session, err := mgo.Dial(url)
    if err != nil {
        // ...
    }

    hook := mongohook.Default(session,"test","t_log")
    defer hook.Flush()

    log := logrus.New()
    log.AddHook(hook)
}
```

## MIT License

    Copyright (c) 2018 Lyric

[reportcard-url]: https://goreportcard.com/report/github.com/LyricTian/logrus-mysql-hook
[reportcard-image]: https://goreportcard.com/badge/github.com/LyricTian/logrus-mysql-hook
[godoc-url]: https://godoc.org/github.com/LyricTian/logrus-mysql-hook
[godoc-image]: https://godoc.org/github.com/LyricTian/logrus-mysql-hook?status.svg
[license-url]: http://opensource.org/licenses/MIT
[license-image]: https://img.shields.io/npm/l/express.svg
