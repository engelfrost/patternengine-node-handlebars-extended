# The Extended Handlebars engine for Pattern Lab 2 / Node

To install the Handlebars engine in your edition, `npm install patternengine-node-handlebars-extended` should do the trick.

By adding `patternlab-handlebars-config.js` to your project root you may extend the Handlebars instance:

```js
module.exports = function (Handlebars) {
  /*
  Register a Helper called `list` which lets you pass values between patterns:

  Examples:
  {{>partialName class=(list classNames)}}
  {{>partialName class=(list 'closs-one class-two')}}
  {{>partialName class=(list 'closs-one' 'class-two')}}
  */
  Handlebars.registerHelper('list', (...args) => {
    args.pop(); // pop options
    const a = [];
    return a.concat.apply(a, args);
  });
};
```

## Supported features
- [x] [Includes](http://patternlab.io/docs/pattern-including.html)
- [x] Lineage
- [x] [Hidden Patterns](http://patternlab.io/docs/pattern-hiding.html)
- [x] [Pseudo-Patterns](http://patternlab.io/docs/pattern-pseudo-patterns.html)
- [x] [Pattern States](http://patternlab.io/docs/pattern-states.html)
- [ ] [Pattern Parameters](http://patternlab.io/docs/pattern-parameters.html) (Accomplished instead using [native Handlebars partial arguments](http://handlebarsjs.com/partials.html))
- [ ] [Style Modifiers](http://patternlab.io/docs/pattern-stylemodifier.html) (Accomplished instead using [native Handlebars partial arguments](http://handlebarsjs.com/partials.html))
