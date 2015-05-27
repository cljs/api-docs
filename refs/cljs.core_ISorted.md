## <img width="48px" valign="middle" src="http://i.imgur.com/Hi20huC.png"> cljs.core/ISorted

 <table border="1">
<tr>
<td>protocol</td>
<td><a href="https://github.com/cljsinfo/api-refs/tree/0.0-1211"><img valign="middle" alt="[+] 0.0-1211" src="https://img.shields.io/badge/+-0.0--1211-lightgrey.svg"></a> </td>
</tr>
</table>

 <samp>
</samp>

```
(no docstring)
```

---

 <pre>
clojurescript @ r1803
└── src
    └── cljs
        └── cljs
            └── <ins>[core.cljs:271-275](https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L271-L275)</ins>
</pre>

```clj
(defprotocol ISorted
  (-sorted-seq [coll ascending?])
  (-sorted-seq-from [coll k ascending?])
  (-entry-key [coll entry])
  (-comparator [coll]))
```


---

```clj
{:ns "cljs.core",
 :name "ISorted",
 :type "protocol",
 :full-name-encode "cljs.core_ISorted",
 :source {:code "(defprotocol ISorted\n  (-sorted-seq [coll ascending?])\n  (-sorted-seq-from [coll k ascending?])\n  (-entry-key [coll entry])\n  (-comparator [coll]))",
          :filename "clojurescript/src/cljs/cljs/core.cljs",
          :lines [271 275],
          :link "https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L271-L275"},
 :methods [{:name "-sorted-seq",
            :signature ["[coll ascending?]"],
            :docstring nil}
           {:name "-sorted-seq-from",
            :signature ["[coll k ascending?]"],
            :docstring nil}
           {:name "-entry-key",
            :signature ["[coll entry]"],
            :docstring nil}
           {:name "-comparator",
            :signature ["[coll]"],
            :docstring nil}],
 :full-name "cljs.core/ISorted",
 :history [["+" "0.0-1211"]]}

```