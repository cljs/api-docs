---
name: syntax/deref
display: "@ deref"
see also:
  - cljs.core/deref
  - cljs.core/atom
  - cljs.core/delay
---

## Summary

## Details

`@foo` is sugar for [`(deref foo)`][doc:cljs.core/deref].

Retrieve the underlying value of a reference.  References can be created by
[doc:cljs.core/atom] or [doc:cljs.core/delay].

## Examples

```clj
(def a (atom 1))
@a
;;=> 1

(deref a)
;;=> 1
```

## Usage
@foo