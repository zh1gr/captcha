> Package captcha provides a simple API for captcha generation

<div>

[![GoDoc](https://godoc.org/github.com/steambap/captcha?status.svg)](https://godoc.org/github.com/steambap/captcha)
[![Build Status](https://travis-ci.org/steambap/captcha.svg)](https://travis-ci.org/steambap/captcha)
[![codecov](https://codecov.io/gh/steambap/captcha/branch/master/graph/badge.svg)](https://codecov.io/gh/steambap/captcha)
[![Go Report Card](https://goreportcard.com/badge/github.com/steambap/captcha)](https://goreportcard.com/report/github.com/steambap/captcha)

</div>

## install
```
go get github.com/steambap/captcha
```

## usage
```Go
func handle(w http.ResponseWriter, r *http.Request) {
	// create a captcha of 150x50px
	data, _ := captcha.New(150, 50)

	// session come from other library such as gorilla/sessions
	session.Values["captcha"] = data.Text
	session.Save(r, w)
	// send image data to client
	data.WriteTo(w)
}

```

[documentation](https://godoc.org/github.com/steambap/captcha) |
[example](example/main.go)

## sample image
![image](example/captcha.png)

## Contributing
If your found a bug, please contribute!
see [contributing.md](contributing.md) for more detail

## License
[MIT](LICENSE.md)
