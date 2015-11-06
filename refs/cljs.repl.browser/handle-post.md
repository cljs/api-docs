## cljs.repl.browser/handle-post



 <table border="1">
<tr>
<td>multimethod</td>
<td><a href="https://github.com/cljsinfo/cljs-api-docs/tree/0.0-927"><img valign="middle" alt="[+] 0.0-927" title="Added in 0.0-927" src="https://img.shields.io/badge/+-0.0--927-lightgrey.svg"></a> </td>
</tr>
</table>


 <samp>
(__handle-post__ _ m)<br>
</samp>

---







Source code @ [github](https://github.com/clojure/clojurescript/blob/r927/src/clj/cljs/repl/browser.clj#L192):

```clj
(defmulti handle-post (fn [_ m] (:type m)))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r927
└── src
    └── clj
        └── cljs
            └── repl
                └── <ins>[browser.clj:192](https://github.com/clojure/clojurescript/blob/r927/src/clj/cljs/repl/browser.clj#L192)</ins>
</pre>

-->

---

Dispatch method @ [github](https://github.com/clojure/clojurescript/blob/r927/src/clj/cljs/repl/browser.clj#L194-L201):

```clj
(defmethod handle-post :ready [conn _]
  (do (reset! loaded-libs #{})
      (send ordering (fn [_] {:expecting nil :fns {}}))
      (send-for-eval conn
                     (cljsc/-compile
                      '[(ns cljs.user)
                        (set! *print-fn* clojure.browser.repl/repl-print)] {})
                     identity)))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r927
└── src
    └── clj
        └── cljs
            └── repl
                └── <ins>[browser.clj:194-201](https://github.com/clojure/clojurescript/blob/r927/src/clj/cljs/repl/browser.clj#L194-L201)</ins>
</pre>
-->

---
Dispatch method @ [github](https://github.com/clojure/clojurescript/blob/r927/src/clj/cljs/repl/browser.clj#L221-L224):

```clj
(defmethod handle-post :print [conn {:keys [content order]}]
  (do (constrain-order order (fn [] (do (print (read-string content))
                                       (.flush *out*))))
      (send-and-close conn 200 "ignore__")))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r927
└── src
    └── clj
        └── cljs
            └── repl
                └── <ins>[browser.clj:221-224](https://github.com/clojure/clojurescript/blob/r927/src/clj/cljs/repl/browser.clj#L221-L224)</ins>
</pre>
-->

---
Dispatch method @ [github](https://github.com/clojure/clojurescript/blob/r927/src/clj/cljs/repl/browser.clj#L226-L228):

```clj
(defmethod handle-post :result [conn {:keys [content order]}]
  (constrain-order order (fn [] (do (return-value content)
                                   (set-connection conn)))))
```

<!--
Repo - tag - source tree - lines:

 <pre>
clojurescript @ r927
└── src
    └── clj
        └── cljs
            └── repl
                └── <ins>[browser.clj:226-228](https://github.com/clojure/clojurescript/blob/r927/src/clj/cljs/repl/browser.clj#L226-L228)</ins>
</pre>
-->

---


###### External doc links:

[`cljs.repl.browser/handle-post` @ crossclj](http://crossclj.info/fun/cljs.repl.browser/handle-post.html)<br>

---

 <table>
<tr><td>
<img valign="middle" align="right" width="48px" src="http://i.imgur.com/Hi20huC.png">
</td><td>
Created for the upcoming ClojureScript website.<br>
[edit here] | [learn how]
</td></tr></table>

[edit here]:https://github.com/cljsinfo/cljs-api-docs/blob/master/cljsdoc/cljs.repl.browser/handle-post.cljsdoc
[learn how]:https://github.com/cljsinfo/cljs-api-docs/wiki/cljsdoc-files

<!--

This information was too distracting to show to readers, but I'll leave it
commented here since it is helpful to:

- pretty-print the data used to generate this document
- and show how to retrieve that data



The API data for this symbol:

```clj
{:ns "cljs.repl.browser",
 :name "handle-post",
 :signature ["[_ m]"],
 :history [["+" "0.0-927"]],
 :type "multimethod",
 :full-name-encode "cljs.repl.browser/handle-post",
 :source {:code "(defmulti handle-post (fn [_ m] (:type m)))",
          :title "Source code",
          :repo "clojurescript",
          :tag "r927",
          :filename "src/clj/cljs/repl/browser.clj",
          :lines [192]},
 :extra-sources ({:code "(defmethod handle-post :ready [conn _]\n  (do (reset! loaded-libs #{})\n      (send ordering (fn [_] {:expecting nil :fns {}}))\n      (send-for-eval conn\n                     (cljsc/-compile\n                      '[(ns cljs.user)\n                        (set! *print-fn* clojure.browser.repl/repl-print)] {})\n                     identity)))",
                  :title "Dispatch method",
                  :repo "clojurescript",
                  :tag "r927",
                  :filename "src/clj/cljs/repl/browser.clj",
                  :lines [194 201]}
                 {:code "(defmethod handle-post :print [conn {:keys [content order]}]\n  (do (constrain-order order (fn [] (do (print (read-string content))\n                                       (.flush *out*))))\n      (send-and-close conn 200 \"ignore__\")))",
                  :title "Dispatch method",
                  :repo "clojurescript",
                  :tag "r927",
                  :filename "src/clj/cljs/repl/browser.clj",
                  :lines [221 224]}
                 {:code "(defmethod handle-post :result [conn {:keys [content order]}]\n  (constrain-order order (fn [] (do (return-value content)\n                                   (set-connection conn)))))",
                  :title "Dispatch method",
                  :repo "clojurescript",
                  :tag "r927",
                  :filename "src/clj/cljs/repl/browser.clj",
                  :lines [226 228]}),
 :full-name "cljs.repl.browser/handle-post"}

```

Retrieve the API data for this symbol:

```clj
;; from Clojure REPL
(require '[clojure.edn :as edn])
(-> (slurp "https://raw.githubusercontent.com/cljsinfo/cljs-api-docs/catalog/cljs-api.edn")
    (edn/read-string)
    (get-in [:symbols "cljs.repl.browser/handle-post"]))
```

-->