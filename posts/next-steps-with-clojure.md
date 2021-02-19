<!--
.. title: Next Steps With Clojure
.. slug: next-steps-with-clojure
.. date: 2021-02-19 15:14:51 UTC-06:00
.. tags: 
.. category: 
.. link: 
.. description: 
.. type: text
-->



# Continuing the Clojure Journey

## Forms

LISP, and clojure, code is basically data. Valid code is referred to as a `form`.

The following are all valid forms:

```clojure
42
"forty two"
["this" "is" "a" "vector" "that" "contains" "strings"]
```

Since the above is generally not very useful, you build up programs with operators:

```clojure
(operator operand1 operand2 operand3 ... operandn)
```

Note the wrapping parenthesis. Note the distinct lack of commas.

## Control Flow

## if

Evaluates code based on truthiness or falsiness

```clojure
(if boolean-form
    then-form
    optional-else-form)
```

Note that each branch can only have a single form to execute. This limitation can be worked around by using....

### do

Used to *wrap up* multiple forms into a single form.

```clojure
(do form1
    form2
    ...
    formn)
```

```clojure
(if true
    (do (println "I'm a success!")
        "Another form here!!"
        "Guess what?!")
    (do (println "This would be a failure....")
        "Sad horn sound here."))
```

Note also that the last item evaluated in the expression is also the return value. So in the example above, in the `true` case the return value would be `"Guess what?!"`.

### when

Similar to `if`, without the *else* branch:

```clojure
(when true
    (println "truthy form")
    "return value form")
```

## Variable binding

### def

`def` is used to bind a value to a name

```clojure
(def vector-of-strings
    ["string one" "string two" "string three"])
```

## Data structures

### Numbers

Numbers just *are*. Including `ratios`.

```clojure
12
89.4565
57/125
```

### strings

Used to represent text, only used with double quotes, concatenation is by way of the `str` function.

```clojure
"This is a string"
"Want to get a double-quote in a string? Then you'll need to \" escape with the backslash."
(str "The str function " "is used" " to concat strings."
    "Note the distinct lack of 'plusses' here.")
```

### Maps

Similar to a hash or dictionary, used to associate a value with a key.

```clojure
{}
{:keyA "valueA"
:keyB "valueB"
:im-a-function +
:empty-map {}}
```

The `hash-map` function can be used to create a new map:

```clojure
(hash-map :key1 1 :key2 2)
```

Use the `get` function to look up values:

```clojure
(get {:key1 1 :key2 2} :key2)
```

`get` returns `nil` if the key is not found, so you can give it a default value to return:

```clojure
(get {:key a :anotherkey b} :non-existant-key "value not found, sorrry")
```

As maps can be nested, the `get-in` function can look inside children maps. The following would return the string "stringy here":

```clojure
(get-in {:not-nested 1 :is-nested {:child-map "stringy here"}} 
    [:is-nested :child-map])
```

A shortcut syntax to access a value in a map is the following method, which treats the map as a function and the key you're needing as a parameter:

```clojure
({:need-to-access-this "really want this value"} :need-to-access-this)
```

#### Keywords

Generally used as, well, _keys_ in a map, they can also be used as functions that fetch their value in a structure - similarly as noted above:

```clojure
:this-is-a-key
:anotherKey
:42
```

When used as functions:

```clojure
(:keyC {:keyA 1 :keyB 2 :key3 5 :keyC 87})
```

The previous example would be identical to the following:

```clojure
(get {:keyA 1 :keyB 2 :key3 5 :keyC 87} :keyC)
```

Default values can be provided as well:

```clojure
(:not-gonna-find-this {a: 1 b: 2 c: 3} "We did not find that key.")
```

### Vectors

A 0-indexed collection, similar to an array.

```clojure
[5 8 0 3]
[5 "string" {:key "value"} nil]
```

Can use `get` to access items, this returns `1`:

```clojure
(get [1 2 3] 0)
```

Use the `vector` function to make them manually, for fun and profit:

```clojure
(vector "a" "b" "c")
```

Use `conj` (conjunction) to add elements to the *end* of a vector:

```clojure
(conj [1 5 4 67] 9)
```

### Lists

Clojure wouldn't be a LISP without Lists...lists are denoted with a single quote `'`. 

```clojure
'(1 2 3 4)
```

Instead of `get`, use `nth` to retrieve items from a list:

```clojure
(nth '(:a :b :c) 0)
```

Lists can be created with the `list` function:

```clojure
(list 8 "string" {5 4})
```

To swap things up for a change, the `conj` function adds to the _beginning_ of lists:

```clojure
(conj '(1 2 3) 0)
```

Lists are good for needing to add to the beginning of a sequence, otherwise use a vector.

### Sets

Come in hash-sets and sorted-sets. Here's a hash-set:

```clojure
#{"string" 5 :key "whatever"}
```

And another, made with `hash-set`:

```clojure
(hash-set 1 2 3 4)
```

Keep in mind, that there are no duplicates in a hash set.

Hash sets can be created with the `set` function as well, from existing vectors:

```clojure
(set [0 1 3 4])
```

Use `contains?` to check for existance within the set:

```clojure
(contains? #{:a :b 0 1 "string"} :b)
(contains? #{:a :b 0 1 "string"} :not-gonna-find-me)
```

Keywords work the same as in Maps:

```clojure
(:keyItem #{:keyItem :keyItemAnother})
```

The above returns `:keyItem`. 

The `get` function works as expected, too.
