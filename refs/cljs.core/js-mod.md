## cljs.core/js-mod



 <table border="1">
<tr>
<td>function/macro</td>
<td><a href="https://github.com/cljsinfo/cljs-api-docs/tree/0.0-1552"><img valign="middle" alt="[+] 0.0-1552" title="Added in 0.0-1552" src="https://img.shields.io/badge/+-0.0--1552-lightgrey.svg"></a> </td>
</tr>
</table>


 <samp>
(__js-mod__ n d)<br>
</samp>

---

Returns the modulus of dividing numerator `n` by denominator `d`, with JavaScript's
original behavior for negative numbers.

Returns `NaN` when `d` is 0 (divide by 0 error).

Equivalent to `x % y` in JavaScript.



---

###### Examples:

```clj
(js-mod -5 3)
;;=> -2

(js-mod 5 3)
;;=> 2

(js-mod 5 0)
;;=> NaN
```



---

###### See Also:

[`cljs.core/mod`](../cljs.core/mod.md)<br>

---


Source docstring:

```
Modulus of num and div with original javascript behavior. i.e. bug for negative numbers
```


Function code @ [github](https://github.com/clojure/clojurescript/blob/r1913/src/cljs/cljs/core.cljs#L1617-L1620):

```clj
(defn js-mod
  [n d]
  (cljs.core/js-mod n d))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r1913
└── src
    └── cljs
        └── cljs
            └── <ins>[core.cljs:1617-1620](https://github.com/clojure/clojurescript/blob/r1913/src/cljs/cljs/core.cljs#L1617-L1620)</ins>
</pre>

-->

---

Macro code @ [github](https://github.com/clojure/clojurescript/blob/r1913/src/clj/cljs/core.clj#L414-L415):

```clj
(defmacro js-mod [num div]
  (list 'js* "(~{} % ~{})" num div))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r1913
└── src
    └── clj
        └── cljs
            └── <ins>[core.clj:414-415](https://github.com/clojure/clojurescript/blob/r1913/src/clj/cljs/core.clj#L414-L415)</ins>
</pre>
-->

---


###### External doc links:

[`cljs.core/js-mod` @ crossclj](http://crossclj.info/fun/cljs.core.cljs/js-mod.html)<br>

---

 <table>
<tr><td>
<img valign="middle" align="right" width="48px" src="http://i.imgur.com/Hi20huC.png">
</td><td>
Created for the upcoming ClojureScript website.<br>
[edit here] | [learn how]
</td></tr></table>

[edit here]:https://github.com/cljsinfo/cljs-api-docs/blob/master/cljsdoc/cljs.core/js-mod.cljsdoc
[learn how]:https://github.com/cljsinfo/cljs-api-docs/wiki/cljsdoc-files

<!--

This information was too distracting to show to readers, but I'll leave it
commented here since it is helpful to:

- pretty-print the data used to generate this document
- and show how to retrieve that data



The API data for this symbol:

```clj
{:description "Returns the modulus of dividing numerator `n` by denominator `d`, with JavaScript's\noriginal behavior for negative numbers.\n\nReturns `NaN` when `d` is 0 (divide by 0 error).\n\nEquivalent to `x % y` in JavaScript.",
 :ns "cljs.core",
 :name "js-mod",
 :signature ["[n d]"],
 :history [["+" "0.0-1552"]],
 :type "function/macro",
 :related ["cljs.core/mod"],
 :full-name-encode "cljs.core/js-mod",
 :source {:code "(defn js-mod\n  [n d]\n  (cljs.core/js-mod n d))",
          :title "Function code",
          :repo "clojurescript",
          :tag "r1913",
          :filename "src/cljs/cljs/core.cljs",
          :lines [1617 1620]},
 :extra-sources [{:code "(defmacro js-mod [num div]\n  (list 'js* \"(~{} % ~{})\" num div))",
                  :title "Macro code",
                  :repo "clojurescript",
                  :tag "r1913",
                  :filename "src/clj/cljs/core.clj",
                  :lines [414 415]}],
 :examples [{:id "75fa6d",
             :content "```clj\n(js-mod -5 3)\n;;=> -2\n\n(js-mod 5 3)\n;;=> 2\n\n(js-mod 5 0)\n;;=> NaN\n```"}],
 :full-name "cljs.core/js-mod",
 :docstring "Modulus of num and div with original javascript behavior. i.e. bug for negative numbers"}

```

Retrieve the API data for this symbol:

```clj
;; from Clojure REPL
(require '[clojure.edn :as edn])
(-> (slurp "https://raw.githubusercontent.com/cljsinfo/cljs-api-docs/catalog/cljs-api.edn")
    (edn/read-string)
    (get-in [:symbols "cljs.core/js-mod"]))
```

-->