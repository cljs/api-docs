---
name: syntax/unreadable
display as: "#<> unreadable"
clojure doc: https://github.com/clojure/clojure/blob/clojure-1.9.0-alpha10/src/jvm/clojure/lang/LispReader.java#L116
see also:
---

## Summary

A proper definition for something that cannot be read.

- `#<...>`

When certain values cannot be printed to a REPL using some literal syntax form,
it wraps a description of its value in a form defined as unreadable, `#<>`.  A
reader error will be thrown if this value is fed back into the REPL.

## Details

For example, `(atom 42)` will print `#<Atom: 42>` when evaluated in a REPL.
This communicates a human-readable form that is not intended to be reproduce
its value.

Oftentimes, evaluating JavaScript objects in a REPL will print the result
of its `.toString` method inside the unreadable form `#<>`.

## Examples

Unreadable forms will throw an exception when read:

```clj
#<foo>
;; clojure.lang.ExceptionInfo: Unreadable form
```

You can create an unreadable form for a custom type:

```clj
(deftype Foo [])
(Foo.)
;;=> #<[object Object]>

(deftype Foo [x]
  Object
  (toString [_]
    (str "Foo: " x)))
(Foo. 1)
;;=> #<Foo: 1>
```

Some examples of unreadable JavaScript values:

```clj
Math/sin
;;=> #<function sin() { [native code] }>

js/console
;;=> #<[object Object]>
```
