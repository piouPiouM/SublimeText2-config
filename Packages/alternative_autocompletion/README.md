Alternative autocompletion for Sublime Text 2
=============================================

This plugin adds an autocompletion command to Sublime Text 2 that acts similarly to TextMate:

* Hitting the autocomplete key will attempt to complete the current word by looking at similar words in the current document.

* Hitting the autocomplete key multiple times will cycle through the available words.

* The last autocomplete position is remembered, so you can perform an autocompletion, move the cursor around, move back to where you were, and continue cycling through the completions.

* Candidate completions are selected prioritized by distance to the cursor.

The plugin improves on TextMate in one respect: If no candidates are found, the plugin reverts to using a simple fuzzy, case-insensitive matching algorithm that is similar to Sublime's file/class matching algorithm. For example, typing `appc` might match `ApplicationController`.

Tested with Sublime Text 2 build 2095.

Installation
------------

Drop the entire folder in Sublime's `Packages` folder. You can do this using `git clone` thus:

    $ cd .../Packages  # Whatever the location is
    $ git clone git://github.com/alexstaubo/sublime_text_alternative_autocompletion.git

Add something like the following to your key bindings:

    { "keys": ["escape"], "command": "alternative_autocomplete", "context":
      [
        { "key": "num_selections", "operator": "equal", "operand": 1 },
        { "key": "overlay_visible", "operator": "equal", "operand": false }
      ]
    },
    { "keys": ["shift+escape"], "command": "alternative_autocomplete", "args": {"cycle": "previous"}, "context":
      [
        { "key": "num_selections", "operator": "equal", "operand": 1 },
        { "key": "overlay_visible", "operator": "equal", "operand": false }
      ]
    },

License
-------

Copyright 2011 Alexander Staubo. MIT license. See `LICENSE` file for license.
