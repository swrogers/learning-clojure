<!--
.. title: Clojure and Functions
.. slug: clojure-and-functions
.. date: 2021-02-19 16:03:12 UTC-06:00
.. tags: clojure 
.. category: 
.. link: 
.. description: 
.. type: text
-->

## Clojure and Functions

With basics covered, time to cover functions.

Use `defn` to define one's own functions. Function definitions have five parts:

* defn

* Function Name

* Optional - Docstring

* bracket of parameters

* function body

Example:

```clojure
(defn function-name
    "This is an interesting function that does something nifty."
    [parameter]
    (str "Let's build a string! Your parameter was " parameter))

(function-name "PARAMETER HERE!!")
```

### Arity and overloading

Functions have an _arity_, that is, how many parameters they take. Functions can be overloaded to run different forms depending on arity. Note that each function form is wrapped in its own paren set:

```clojure
(defn overloaded-function
    ;; 3 arity
    ([one two three]
    (str "one: " one "two: " two "three: " three))
    ;; 2 arity
    ([one two]
    (str "one: " one "two: " two))
    ;; 1 arity
    ([one]
    (str "one: " one))
    ;; 0 arity
    ([]
    (str "no args here!")))
```

You can use the above as a method to provide default arguments, by calling the function from itself:

```clojure
(defn i-have-default-second-arg
    "The second argument will have a default here..."
    ([arg1 arg2]
        (str "arg1: " arg1 "arg2: " arg2))
    ([arg1]
        (i-have-default-second-arg arg1 "default")))
```

### The `Rest` parameter

Another way to define multi-arity functions is with the _rest_ parameter: `&`.  When this method is used, it says to place all the rest of the included parameters into the named list.

```clojure
(defn named-shopping-list
    "The first parameter will be the name of the list: list-name.
     The remaining parameters will be added to the list: shopping-list"
    [list-name & shopping-list]
    (str "List name: " list-name
        "List items: " shopping-list))
```

### Destructuring

Another way to define parameters, binding names to items within the collection.

This is done by passing the parameter list inside a vector.
