# CSS

Don't write CSS manually in all but the very simplest cases.  CSS in
itself is not maintainable and much better alternatives exist Today.

We prefer to use [Stylus](http://learnboost.github.io/stylus/), but
LESS or SASS are also good candidates.


## <a name="structure"></a>Structure your CSS like code

Usually CSS is the culprit when productivity on a web project comes to
a grinding halt. It quickly becomes a big pile of unstructured
selectors, with increasing specificity.

We use
[BEM](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
(or atleast a variation) thereof to make sure that the styles are
structured and reusable. This has proven highly effective on large
projects.

You can check out the styles for
[our website](//github.com/triforkse/trifork.se) if you want an
example.

## Keep Specificity Low

The fewer classes, ids and element names you use in your selectors the
better. Usually you can write your entire application with no more
that 2 classes in each rule (not counting pseudo classes).

The more selectors you include in a rule that harder it is to
override, and maintain.


## Keep Page Specific Styling Low

Write your CSS in terms of resuable components. This allows you to
reuse the styles and have a consistent look in your entire
application.

If you use something like [BEM](#structure) then you will likely not
run into problems, because it forces you to think in terms of
components.


## Don't nest selectors

This seemingly very usful feature is often


## Minification

Whether or not you minify your source should be an educated desicion.
Remember that just like any other optimisation you should first see
that it is actually a problem, measure it, and THEN optimise.

Minification (and concatination) can make debugging very
difficult. And with the advent of HTTP/2 with the server multiplexing
all files on a single connection and using cross-resource compression
on concatination and minification have very little impact in many
cases.

That being set do it, IF you need it, else don't.


## Never inline styles

While it sometimes seems the easiest to apply styles with a
`style="..."` attribute if you just need the modification in one place
on your page, it is counter productive and hard to maintain.


## Specificity & Stacking Contexts

To truly become good at CSS you have to intemitly understand these two
important concepts: Specificity and The Stacking Contexts.

Without understanding these you will usually end up doing something
like applying `!important` to lots of properties or setting `z-index =
9999`. Both are telltale signs that you don't know what you are doing,
and are hard to maintain.
