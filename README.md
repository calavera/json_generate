# JSON Generate

JSON Generate is a tool to create go structs based on JSON examples.

## Installation

```
$ go get github.com/calavera/json_generate
```

## Usage

Add a JSON example as a constant in your go code. Something like:

```go
const JSONExample_User = `{
  "name": "calavera"
}`
```

The constant MUST have the prefix `JSONExample_` in its name.

Then run the `json_generate` script with something like:

```
$ json_generate filename.go
```

Or add the `generate` header to the source file:

```go
// go:genearate json_generate
```

This will generate a `filename_json.go` file with the go struct parsed. Something like:

```go
type User struct {
  Name string `json:"name,omitempty"`
}
```

## Options

- output: Flag to specify the output where the structs are written.
- example: Flag to limit the json examples you want to parse.
- alias: Flag to convert inner json maps into other structs.
- types: Flag to convert fields into specific go types.
- debug: Print the genearted structs in STDOUT rather than into the output file.

## FAQ

** Is this program any good? **

It avoided me the hassle of writing a bunch of json structs by hand. It won't probably work for 100% of your use cases, but it can save you some time.

** Did you spend more time working on this than it would have taken you to write those structs by hand? **

Definitely.

** Did you learn something new about go by doing this rather than writing a bunch of boilerplate code? **

Definitely.

## LICENSE

MIT
