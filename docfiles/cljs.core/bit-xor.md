---
name: cljs.core/bit-xor
see also:
  - cljs.core/bit-and
  - cljs.core/bit-or
---

## Summary

## Details

Bitwise "exclusive or". Same as `x ^ y` in JavaScript.

## Examples

Bits can be entered using radix notation:

```clj
(bit-xor 2r1100 2r1010)
;;=> 6
;; 6 = 2r0110
```

Same numbers in decimal:

```clj
(bit-xor 12 10)
;;=> 6
```
