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


