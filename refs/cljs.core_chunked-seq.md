## <img width="48px" valign="middle" src="http://i.imgur.com/Hi20huC.png"> cljs.core/chunked-seq

 <table border="1">
<tr>
<td>function</td>
<td><a href="https://github.com/cljsinfo/api-refs/tree/0.0-1424"><img valign="middle" alt="[+] 0.0-1424" src="https://img.shields.io/badge/+-0.0--1424-lightgrey.svg"></a> </td>
</tr>
</table>

 <samp>
(__chunked-seq__ vec i off)<br>
(__chunked-seq__ vec node i off)<br>
(__chunked-seq__ vec node i off meta)<br>
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
            └── <ins>[core.cljs:3286-3290](https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L3286-L3290)</ins>
</pre>

```clj
(defn chunked-seq
  ([vec i off] (ChunkedSeq. vec (array-for vec i) i off nil nil))
  ([vec node i off] (ChunkedSeq. vec node i off nil nil))
  ([vec node i off meta]
     (ChunkedSeq. vec node i off meta nil)))
```


---

```clj
{:full-name "cljs.core/chunked-seq",
 :ns "cljs.core",
 :name "chunked-seq",
 :type "function",
 :signature ["[vec i off]" "[vec node i off]" "[vec node i off meta]"],
 :source {:code "(defn chunked-seq\n  ([vec i off] (ChunkedSeq. vec (array-for vec i) i off nil nil))\n  ([vec node i off] (ChunkedSeq. vec node i off nil nil))\n  ([vec node i off meta]\n     (ChunkedSeq. vec node i off meta nil)))",
          :filename "clojurescript/src/cljs/cljs/core.cljs",
          :lines [3286 3290],
          :link "https://github.com/clojure/clojurescript/blob/r1803/src/cljs/cljs/core.cljs#L3286-L3290"},
 :full-name-encode "cljs.core_chunked-seq",
 :history [["+" "0.0-1424"]]}

```