# IClojure

An Interactive Clojure repl, inspired by IPython.

## License

Eclipse Public License (EPL), same as Clojure.

## Getting started

```
curl -O -L http://clk.tc/iclojure-latest.jar
java -jar iclojure-latest.jar
```

Alternatively, you can download the following script, mark it executable and put it somewhere in path

```
curl -O https://raw.github.com/cosmin/IClojure/master/bin/iclojure
chmod +x iclojure
sudo mv iclojure /usr/local/bin
```

Then you can simply launch `iclojure` at any time.

## Development

    git checkout https://github.com/cosmin/IClojure
    cd IClojure
    bin/run.sh

## Package

    mvn clean package

## Features

- Tab completion
- Shorthand for source and doc
- Shorthand for introspecting Java objects and classes via reflection
- Proper Control-C handling, although not very portable
- persist history across sessions to ~/.iclojure_history
- input and output caching of last 1000 elements

## Tab completion

- variable
- method invocations
- "(.method" completion for all java methods for any of the classes in the current namespace
- "(. object method" completion for all the methods of the object (or a form that evaluates to an object)
- namespaces
- java classes
- import statements for both symbols and import lists

## Input / output caching

In addition to the Clojure convention of caching the last 3 output in `*1`, `*2` and `*3` IClojure also caches the last 1000 input and output

```
(input 102) ; => returns the input from line 102
(output 102) ; => returns the output from line 102
```

## Other shorthands

```
    ?symbol          => (doc symbol)
    ??symbol         => (source symbol)
    %d symbol        => show constructors, methods and fields of the given object or Class
    %f class         => find all classes matching this name (supports globs)
    %f class package => like the above, but restrict search to the given package
```

## Roadmap

- tab completion for require and use forms
- abort long runing tasks with Ctrl+C
- better stack traces
- find class by name (to know what to import)
