# Go interlanguage call examples

Calls between Go and C/C++ and calling Go from dynamic languages.

## Calls from Go to C (`go_to_c` folder)

These examples use [cgo](https://golang.org/cmd/cgo/) to enable calls to C.

- Calling a C snippet in the cgo comment: [c_in_comment](https://github.com/draffensperger/go-interlang/tree/master/go_to_c/c_in_comment/main.go)
- Calling a C statically-linked library (`.a` file): [static_c_lib](https://github.com/draffensperger/go-interlang/tree/master/go_to_c/static_c_lib)
- Calling a C dynamically-linked library (`.so` or `.dylib`): [dynamic_c_lib](https://github.com/draffensperger/go-interlang/tree/master/go_to_c/dynamic_c_lib)

## Calls from Go to C++ (`go_to_cxx` folder)

C++ has more complex calling conventions (e.g. function overloading, inheritance, templates) and so it uses [name mangling](https://en.wikipedia.org/wiki/Name_mangling#Name_mangling_in_C.2B.2B) which adds a step when calling it from Go. Below are ways to do it.

- Calling C++ via a C wrapper function: [c_wrapper](https://github.com/draffensperger/go-interlang/tree/master/go_to_cxx/c_wrapper)
- Calling C++ via an auto-generated SWIG wrapper:
  [swig](https://github.com/draffensperger/go-interlang/tree/master/go_to_cxx/swig)

## Calls from C/C++ to Go (`c_to_go` folder)

- Calling from Go to C and back again: [to_c_and_back](https://github.com/draffensperger/go-interlang/tree/master/go_from_c/to_c_and_back)
- Calling a Go static library with `buildmode=c-archive`: [static_go_lib](https://github.com/draffensperger/go-interlang/tree/master/c_to_go/static_go_lib)
- Calling Go from C using [gccgo](https://golang.org/doc/install/gccgo)
- You can also call from C/C++ to a Go dynamically-linked library (same concept as dynamic langs below)

## Calls from Python/Node.js/Ruby/Java to Go

Go now allows building a C-compatible dynamically-linked library with `buildmode=c-shared`. That allows any language that can call C dynamic libraries to call Go.

- Call from Python via [ctypes](https://docs.python.org/2/library/ctypes.html): 
- Call from Node.js via [ffi](https://github.com/node-ffi/node-ffi) npm module
- Call from Ruby via [ffi](https://github.com/ffi/ffi) gem
- Call from Java via [JNA](https://github.com/java-native-access/jna)

# Helpful links

Cgo documentation: [golang.og/cmd/cgo/](https://golang.org/cmd/cgo/)

`go` command documentation (especially `go build` and "Calling between Go and C"): 
[golang.org/cmd/go/](https://golang.org/cmd/go/)

SWIG Documentation: [swig.org](http://swig.org/)

SWIG Go examples: (github.com/swig/swig/tree/master/Examples/go)[https://github.com/swig/swig/tree/master/Examples/go]

Gccgo documentation: [golang.org/doc/install/gccgo](https://golang.org/doc/install/gccgo)

# License

[MIT Licensed](http://opensource.org/licenses/MIT).
