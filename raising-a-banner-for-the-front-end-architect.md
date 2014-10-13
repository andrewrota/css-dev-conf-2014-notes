# Raising a Banner for the Front-End Architect
**#frontendarch; Micah Godbolt, [@micahgodbolt](http://twitter.com/micahgodbolt)**

Back in the day, the "webmaster" did many things and wore many hats.  Eventually they started to define things that interested them more.  They found a hat they preferred to wear.

History of front-end disciplines

People that love content -> content strategy

Battling the iPhone -> responsive web design (fluid grids, responsive images, media queries: put the pieces together)

Today front end devs are starting to band together.  They're demanding that we treat our front end code with the same respect and attention as our back-end code.  We're tired of the 'theme' being an after thought, after all the "important" work has been done.

**It's time to make front-end architecture matter.**

**Coding Standards**

A lot's been said on this one already.  At last year's CSS Dev Conf this was basically Micah's talk.

**Documentation**

If coding standards are the rule, documentation is the proof that we're actually following those rules.

Pattern libraries or style guides are very common documentation methods.  They're tiny bootstraps for every client, that contain an inventory of colors, fonts, icons, functions, variables, mixins, etc.  Create a common vocabulary.

Creating a modern styleguide:

* Pattern Lab (Brad Frost)
* Hologram (Trulia)

Or just roll your own.  If the collection of pieces is small enough it's not a huge deal to write your own.

Document how your system works.  Examples.

Granularity, of course, is always the question.

**Regression Testing**

We're depending too much on the cascade.  We're using too much location inheritance or class inheritance.

Changing an inheritance model to a composition model.

But even so, we still can't prove nothing is going to break.

Enter visual regression testing.

* Wraith.js
    * Page based
    * Multiple domains
    * Multiple widths
    * Multiple pages

Avoid entire page diffs.  Move away from styling page and styling diffs.

* PhantomCSS
    * **Selector based regions**
    * Single domain
    * Multiple states (Hover/Context)
    * Multiple widths

Write tests as you develop a feature.  Once you have a lot of tests you can run the tests before merging in new code.

**Automation**

Automate all the things.

Dependency management.

Build system.

Continuous integration.