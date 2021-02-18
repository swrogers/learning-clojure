# Emacs - The Ultimate Clojure Editor

If I'm being honestly frank, and it's more like honestly Shane...but whatever....the reason I wanted to pick up a LISP is because I've been wanting to get more in depth into Emacs. Since Emacs is basically a LISP machine, it helps to have some knowledge of LISP in order to use Emacs to its fullest. That, and who knows, maybe learning Clojure can help with future employment prospects, self taught or not.

One thing that I have been doing over the past few months, is building up [my Emacs config](https://gitlab.swrgroups.net/swrogers/dot-emacs-config) from scratch using Org mode. Which is, in and of itself, quite a time consuming beast. For Clojure, I've been using a handful of handy packages.

## Emacs Keyboard References

Here is a handy table of Emacs keys that one might find useful from this page

| Command       | Keyboard shortcut                                   | Function name      |
| ------------- | --------------------------------------------------- | ------------------ |
| Create buffer | <kbd>C</kbd>-<kbd>x</kbd> <kbd>b</kbd>              | `switch-to-buffer` |
| Kill buffer   | <kbd>C</kbd>-<kbd>x</kbd> <kbd>k</kbd>              |                    |
| Visit file    | <kbd>C</kbd>-<kbd>x</kbd> <kbd>C</kbd>-<kbd>f</kbd> |                    |
| Save file     | <kbd>C</kbd>-<kbd>x</kbd> <kbd>C</kbd>-<kbd>s</kbd> | `save-file`        |
| Kill line     | <kbd>C</kbd>-<kbd>k</kbd>                           |                    |
| Undo          | <kbd>C</kbd>-<kbd>/</kbd>                           |                    |

## CIDER Keyboard Reference

| Command                                                           | Keyboard shortcut                        | Function name              |
| ----------------------------------------------------------------- | ---------------------------------------- | -------------------------- |
| Eval last expression                                              | <kbd>C-x C-e</kbd>                       | cider-eval-last-expression |
| Set namespace                                                     | <kbd>C-c M-n M-n</kbd>                   |                            |
| Compile buffer                                                    | <kbd>C-c C-k</kbd>                       |                            |
| Cycle REPL history                                                | <kbd>C-[UP]</kbd> or <kbd>C-[DOWN]</kbd> |                            |
| Display Documentation for symbol at point                         | <kbd>C-c C-d C-d</kbd>                   |                            |
| Navigate to source for symbol at point                            | <kbd>M-.</kbd>                           |                            |
| Navigate back to original buffer and position                     | <kbd>M-,</kbd>                           |                            |
| Search for arbitrary text across function names and documentation | <kbd>C-c C-d C-a</kbd>                   |                            |

## Paredit Keyboard Reference

| Command                | Keyboard shortcut    | Function name |
| ---------------------- | -------------------- | ------------- |
| Wrap                   | <kbd>M-(</kbd>       |               |
| Slurp                  | <kbd>C-[RIGHT]</kbd> |               |
| Barf                   | <kbd>C-[LEFT]</kbd>  |               |
| Move to closing parens | <kbd>C-M-f</kbd>     |               |
| Move to opening parens | <kbd>C-M-b</kbd>     |               |

## Now to actually start learning the language

Hopefully that makes some sense, now it's on to starting to learn things...
