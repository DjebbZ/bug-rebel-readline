## Reproduction repo for 2 bugs in rebel-readline

#### Bug #1

In rebel-readline-cljs (with figwheel at least), when aliasing a namespace the alias doesn't autocomplete its content.

Steps to reproduce:

1. `clojure -A:bug-alias`
2. ... the repl launches
3. `(require '[bug-rebel-readline.core :as bug])`
4. `(bug/<CURSOR POSITION>`
5. Press `<TAB>`

Expected: autocomplete with foo, so that `(bug/foo` is displayed
Actual: Nothing happens

#### Bug #2

In rebel-readline, when trying to alias a namespace, there's no autocomplete for the full ns name.

Steps to reproduce:

1. `clojure -A:bug-autocomplete`
2. ... the repl launches
3. `(require '[bug<CURSOR-POSITION>`
4. Press `<TAB>`

Expected: autocomplete full ns name, so that `(require '[bug-rebel-readline.core` is displayed
Actual: Nothing happens

*Note: Bug #2 doesn't exist with rebel-readline-cljs, and Bug #1 doesn't exist with rebel-readline*
