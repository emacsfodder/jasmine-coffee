# jasmine-coffee

Helpful stuff for Jasmine on CoffeeScript

## Installation

This script is still very much a work in-progress, so it's not
available via MELPA or any other package repository yet. 

Installation is manual only:

Place the `jasmine-coffee.el` script in your emacs `load-path` and add:

    (eval-after-load "coffee-mode"
        (require 'jasmine-coffee))

To your `~/.emacs` (or ~/.emacs.d/init.el).

### Spec launchers

Launch the first Jasmine coffee-script `it` spec found at or above the
current point.

    M-x jasmine-coffee/verify-it
    M-x jasmine-coffee/verify-single

Launch the first Jasmine coffee-script `describe` group found at or
above the current point.

    M-x jasmine-coffee/verify-describe
    M-x jasmine-coffee/verify-group

Set the variable `jasmine-coffee/base-url` to set your jasmine spec runner base URL.

e.g.
   
    (setq jasmine-coffee/base-url "http://localhost:3000/jasmine?spec=")

The helper commands above will compose the URL for you.  Note I've
only tested this with Jasmine-rice, so please post an issue if you use
the Karma runner or another Jasmine runner, and you find this
incompatible.

### Moving to outer blocks

These commands move the current line or region into enclosing `describe`
block (useful for lazy/jlet) or into the previous `beforeEach`.

Move the current line or region to the previous `describe` body

    M-x jasmine-coffee/move-to-previous-describe

Move the current line or region to the previous `beforeEach` body

    M-x jasmine-coffee/move-to-previous-before-each

### Lazily evaluated vars

Jasmine-Let by Diego Garcia (github @xaethos) allows you to use a lazy
variable which is evaluated when your `it` spec is run. For more info
see: https://github.com/xaethos/jasmine-let

Convert a local var assignment to a `lazy`

    M-x jasmine-coffee/var-to-lazy

In my day-to-day we assign `jasmineLet` to an alias `jlet` (instead of
`lazy`) so this command is really just for me and my team.

Convert a local var assignment to a `jlet`

    M-x jasmine-coffee/var-to-jlet

We also use `jset` which works like `let!` in rspec, so:

Convert a local var assignment to a `jset`

    M-x jasmine-coffee/var-to-jset

### More

I have a collection of coffee-mode yasnippets for jasmine, which I'll
migrate to this package soon. 

If you're impatient to grab them, you can get them directly from my
`.emacs.d`.  See the coffee-mode snippets folder
https://github.com/ocodo/emacs.d/tree/master/snippets/coffee-mode

I'll also be adding navigation and further editing helpers (feature
matching
[buster-mode](https://gitorious.org/buster/buster-mode/source/c9d4b6b6f85283e18363c8236620905f58110831:buster-mode.el))
