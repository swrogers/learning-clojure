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

Used to _wrap up_ multiple forms into a single form.

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

Similar to `if`, without the _else_ branch:

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


