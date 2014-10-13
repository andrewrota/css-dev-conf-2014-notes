# A Vision for Style Guides in 2015
**#styleguide15; by Nico Hagenburger, [@Hagenburger](http://twitter.com/Hagenburger)**

livingstyleguide.org

**Styleguide History**

Paper style guides in the 70s.

PDF style guides in the 90s, or styleguides on coorporate wikis after that.  Hard to distribute.  Confusion about latest version.  Hard to update.

Now, living styleguides.

**HTML/CSS Integrated in Living Styleguide**

* Are made with HTML and CSS
* Use the production CSS
* Are under version control

Back-end developers love it.  They can start functionality with something looking good.

HTML, CSS, and Data.  Data is the content, not the HTML.

**How do you deal with changes?**

A change log is one way.  There are so many small details, you don't know the audience of the change, etc. 

Show all versions?  It might mess up and it will be a lot of work.

**How do we take care of edge cases?**

Having HTML with different amount of text (including no text).  Without images or images too small.

**Annotations in Styleguide examples**

    @mustache
    @template hello-world.template
    @data {
        "name": "Homer",
        "text": "Lorem Ipsum"
    }
    
If we extract the template the developer has to copy the ID, not a bunch of HTML.  We just defined and API.  A simple interface.  An API is easy to test, front ends are not.

**APIs**

* One 'call' per action
* Specified input, output, and name/URL/ID
* Written tests for every action

**Automated Testing**

* Take screenshots of every example
* Include all edge cases
* Compare before/after
* Warn for every change

**Each template should have:**

* The HTML
* The CSS
* Normal examples (markdown?  annotations?  json?)
* Edge cases (show only when needed)
* Reference screenshots

**What's a Style Guide Good For?**

* Front-end developers (and designers)
* Back-end/application developers
* QA
* Designers
* External Designers
* HR

**Vision for Styleguides in 2015: an API**

Styleguide is part of the system.  Easy to test, living for itself without influence from the outside.

* Independent
* Easy to use
* Maintainable
* Testable

(And beautiful.)
