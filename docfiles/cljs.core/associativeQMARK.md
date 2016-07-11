---
name: cljs.core/associative?
see also:
---

## Summary

## Details

Returns true if `coll` implements the `IAssociative` protocol, false otherwise.

Maps and vectors are associative.

## Examples

```clj
(associative? [1 2 3])
;;=> true

(associative? {:a 1 :b 2})
;;=> true

(associative? #{1 2 3})
;;=> false

(associative? '(1 2 3))
;;=> false
```

## Signature
[coll]