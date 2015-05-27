## <img width="48px" valign="middle" src="http://i.imgur.com/Hi20huC.png"> special/letfn\*

 <table border="1">
<tr>
<td>special form</td>
<td><a href="https://github.com/cljsinfo/api-refs/tree/0.0-1236"><img valign="middle" alt="[+] 0.0-1236" src="https://img.shields.io/badge/+-0.0--1236-lightgrey.svg"></a> </td>
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
    └── clj
        └── cljs
            └── <ins>[analyzer.clj:444-468](https://github.com/clojure/clojurescript/blob/r1803/src/clj/cljs/analyzer.clj#L444-L468)</ins>
</pre>

```clj
(defmethod parse 'letfn*
  [op env [_ bindings & exprs :as form] name]
  (assert (and (vector? bindings) (even? (count bindings))) "bindings must be vector of even number of elements")
  (let [n->fexpr (into {} (map (juxt first second) (partition 2 bindings)))
        names    (keys n->fexpr)
        context  (:context env)
        [meth-env bes]
        (reduce (fn [[{:keys [locals] :as env} bes] n]
                  (let [be {:name   n
                            :line (get-line n env)
                            :column (get-col n env)
                            :tag    (-> n meta :tag)
                            :local  true
                            :shadow (locals n)}]
                    [(assoc-in env [:locals n] be)
                     (conj bes be)]))
                [env []] names)
        meth-env (assoc meth-env :context :expr)
        bes (vec (map (fn [{:keys [name shadow] :as be}]
                        (let [env (assoc-in meth-env [:locals name] shadow)]
                          (assoc be :init (analyze env (n->fexpr name)))))
                      bes))
        expr (analyze (assoc meth-env :context (if (= :expr context) :return context)) `(do ~@exprs))]
    {:env env :op :letfn :bindings bes :expr expr :form form
     :children (conj (vec (map :init bes)) expr)}))
```


---

```clj
{:full-name "special/letfn*",
 :ns "special",
 :name "letfn*",
 :type "special form",
 :source {:code "(defmethod parse 'letfn*\n  [op env [_ bindings & exprs :as form] name]\n  (assert (and (vector? bindings) (even? (count bindings))) \"bindings must be vector of even number of elements\")\n  (let [n->fexpr (into {} (map (juxt first second) (partition 2 bindings)))\n        names    (keys n->fexpr)\n        context  (:context env)\n        [meth-env bes]\n        (reduce (fn [[{:keys [locals] :as env} bes] n]\n                  (let [be {:name   n\n                            :line (get-line n env)\n                            :column (get-col n env)\n                            :tag    (-> n meta :tag)\n                            :local  true\n                            :shadow (locals n)}]\n                    [(assoc-in env [:locals n] be)\n                     (conj bes be)]))\n                [env []] names)\n        meth-env (assoc meth-env :context :expr)\n        bes (vec (map (fn [{:keys [name shadow] :as be}]\n                        (let [env (assoc-in meth-env [:locals name] shadow)]\n                          (assoc be :init (analyze env (n->fexpr name)))))\n                      bes))\n        expr (analyze (assoc meth-env :context (if (= :expr context) :return context)) `(do ~@exprs))]\n    {:env env :op :letfn :bindings bes :expr expr :form form\n     :children (conj (vec (map :init bes)) expr)}))",
          :filename "clojurescript/src/clj/cljs/analyzer.clj",
          :lines [444 468],
          :link "https://github.com/clojure/clojurescript/blob/r1803/src/clj/cljs/analyzer.clj#L444-L468"},
 :full-name-encode "special_letfn_STAR_",
 :history [["+" "0.0-1236"]]}

```