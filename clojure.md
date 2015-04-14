The #' reader macro for var makes it possible to bind a key to a the name of a function instead of to the actual function in maps etc.

'slurp' can take a web URL and read from it (!)

'fnil' transforms a function that crashes on nil input to something that will use a default value when given nil

'sort-by' can reach into each element of the thing being sorted by using a function and sort on some arbitrary property

%& can be used in #() functions for a variable length parameter list

ex-info & ex-data kan användas för att rapportera fel i form av data (?)

(case color
  :red (do-a)
  :green (do-b)
  :blue (do-c))
är bättre än
(condp color =
  ...)


assoc kan ta flera par av key/value
(assoc entity :x 30 :y 20 :hp 100)




Neat snippets
(->> (slurp "http://www.eriksvedang.com") (re-seq #"clairvoyance") count)	; räkna antalet gånger Clairvoyance nämns på min hemsida

Initializer function maker
(defmacro make-init [fn-name & keywords]
  (let [s (interleave (map keyword keywords) keywords)]
    `(defn ~fn-name [~@keywords]
       (array-map ~@s))))

Vec math function maker
(defmacro def-vec-fn [op]
  `(defn ~(symbol (str "vec" op)) [v1# v2#]
     (vec (map ~op v1# v2#))))
(def-vec-fn +)
(def-vec-fn -)
(def-vec-fn *)
(vec+ [1 2 3] [1 1 1])
(vec- [1 2 3] [1 1 1])
(vec* [1 2 3] [1 1 1])



(defn call-with-fn-at [obj path & args]
  (let [f (get-in obj path)]
    (apply f (concat [obj] args))))
