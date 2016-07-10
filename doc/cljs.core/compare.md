---
name: cljs.core/compare
related:
  - cljs.core/sort-by
  - cljs.core/sorted-set-by
  - cljs.core/sorted-map-by
---

## Signature
[x y]


## Details

Comparator.

Returns a negative number, zero, or a positive number when `x` is logically
"less than", "equal to", or "greater than" `y`.

Uses `IComparable` if available and `google.array.defaultCompare` for objects of
the same type. nil is treated as a special case and is always less than any
other object.


## Examples

```clj
(compare 10 12)
;;=> -1

(compare 12 10)
;;=> 1

(compare 10 10)
;;=> 0

(compare 10 nil)
;;=>  1

(compare 10 (list 1 2 3))
;; Error: compare on non-nil objects of different types
```