# go-envtags

[![Codacy Badge](https://app.codacy.com/project/badge/Grade/6904ddba8e6747559c7b4141b0f91e71)](https://www.codacy.com/gh/taciogt/go-envtags/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=taciogt/go-envtags&amp;utm_campaign=Badge_Grade)
[![Codacy Badge](https://app.codacy.com/project/badge/Coverage/6904ddba8e6747559c7b4141b0f91e71)](https://www.codacy.com/gh/taciogt/go-envtags/dashboard?utm_source=github.com&utm_medium=referral&utm_content=taciogt/go-envtags&utm_campaign=Badge_Coverage)

🚧 This project is under construction 🚧 

One more package to support env tags to load environment variables on structs. It is more about studying Go reflection approach than to create something that already exists.

## Usage

Define a struct with the `env` tag on **exported** fields to bind the fields with environment variables

```go
type Config struct {
	Foo int `env:"BAR"`
}
```

On an environment with the corresponding variables set, bind the struct to these variables using the method `Set()`

```shell
  export BAR="13" 
```

```go
var config Config
if err := envtags.Set(&config); err != nil {
	log.Fatal(err)
}
```

## Refs

Better test output with:
```shell
go install github.com/rakyll/gotest
```

Requirements:
*   Go >= 1.17

Inspired by 
* https://github.com/kelseyhightower/envconfig/blob/master/envconfig.go
* https://github.com/caarlos0/env

References
*   https://go.dev/ref/spec#Numeric_types
