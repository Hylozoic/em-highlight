EM Highlight
=========

Looks for given words or expressions in a text and highlights them with
`<em class='highlight'> TERM </em>`

This fork of [Tessmore/em-highlight](https://github.com/Tessmore/em-highlight) has been modified not to depend on lodash. It is being used in a browserify bundle in a front-end environment where lodash is a global (it's loaded via a separate script tag), so we want to avoid increasing the bundle size with an extra copy of lodash.

# Usage

```javascript
var highlight = require('em-highlight');

var text   = "We cannot rule this rule out on other rules and there is no stopping.";
var lookup = [
    "rule",
    "rule out"
];

var result = highlight.find(text, lookup);

// "We cannot <em class='highlight'> rule </em> this
//  <em class='highlight'> <em class='highlight'> rule </em> out </em> on other
//  rules and there is no stopping."
```

# Notes

* Allows case insensitive matching.
* Not extensively tested with very large texts.
* Nested lookup terms are highlighted again. You could use css `opacity` to display this.
