*Author:* Jason Milkins<br>
*Version:* 20141114<br>

 This file is not a part of Emacs

## Installation

This script is still very much a work in-progress, so it's not
available via MELPA or any other package repository yet.

## Installation is manual only

Place the `jasmine-coffee.el` script in your Emacs `load-path` and add:

        (eval-after-load "coffee-mode"
            (require 'jasmine-coffee))

To your `~/.emacs` (or ~/.emacs.d/init.el).

## Commands

### Code transforms

* `jasmine-coffee/toggle-spec-enabled`

Convert an `it` to an `xit`

* `jasmine-coffee/var-to-lazy`

Convert a variable assignment to `lazy` eg.

    myVariable = "value"

Becomes

    lazy 'myVariable', -> "value"

`lazy` is equivalent to RSpec`s `let`

* `jasmine-coffee/var-to-jlet`

Convert a variable assignment to `jlet` eg.

    myVariable = "value"

Becomes

    jlet 'myVariable', -> "value"

`jlet` is equivalent to RSpec`s `let`

* `jasmine-coffee/var-to-jset`

Convert a variable assignment to `jset` eg.

    myVariable = "value"

Becomes

    jset 'myVariable', -> "value"

`jset` is equivalent to RSpec`s `let!`

### Move spec code

* `jasmine-coffee/move-to-previous-describe`

Move the current selection or line to the previous `describe`
statment (moving code from an `it` or `beforeEach` for example.)

Note: This command doesn't move code from one `describe` to the
previous one.

* `jasmine-coffee/move-to-previous-before-each`

Move the current selection or line from an `it` spec, to the
previous `beforeEach`.

### Verify specs and groups

* `jasmine-coffee/verify-describe` & `jasmine-coffee/verify-group`

Verify the current describe block via opening a jasmine url, using
`jasmine-coffee/base-url` (a custom variable)

* `jasmine-coffee/verify-it` & `jasmine-coffee/verify-single`

Launch the current spec in a browser window, using the
jasmine-coffee/base-url (custom variable)

### Navigations

These commands should be self explanatory

* `jasmine-coffee/navigate-to-next-it`
* `jasmine-coffee/navigate-to-previous-it`
* `jasmine-coffee/navigate-to-next-describe`
* `jasmine-coffee/navigate-to-previous-describe`
* `jasmine-coffee/navigate-to-next-before-each`
* `jasmine-coffee/navigate-to-previous-before-each`

### Code / Spec toggling

* `jasmine-coffee/toggle-code-and-spec`

Switch between the Spec / Code of the current spec or code file.
Set the following customizable variables to tailor for your own
projects.

* `jasmine-coffee/code-root` - location of code, defaults to `app/assets/javascripts`
* `jasmine-coffee/spec-root` - location of specs, defaults to `spec/javascripts`
* `jasmine-coffee/extension` - standard coffeescript file extension, defaults to `.js.coffee` (Rails style)
* `jasmine-coffee/spec-suffix` - standard spec name suffix, defaults to `_spec`

Licence: GPL3

Requires: ((coffee-mode) (s) (dash) (projectile))
Code:


---
Converted from `jasmine-coffee.el` by [*el2markdown*](https://github.com/Lindydancer/el2markdown).
