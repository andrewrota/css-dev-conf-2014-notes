# Embracing Performance Optimization
**#perfopt; Jon Bellah, [@jonbellah](http://twitter.com/jonbellah)**

**What is Performance Optimization?**

In the context of web, it's the science of making websites faster.

Speed is a feature.  An organizational decision that needs to be budgeted for.

Mozilla Case Study from 2010.  Reducing load speed by 2.2 seconds they saw 15.4% increase in downloads and conversions.

**Perceived Speed vs. Actual Speed**

"Progressive Rendering", which Facebook uses (perceived speed).

## Four Pillars of Performance Optimization

### Optimize the Critical Rendering Path

When you visit a website and hit the network it sends back the file, constructions the DOM and CSSOM, and sends it back from the screen.  JavaScript blocks the browser from creating the render tree because it needs all the CSS in place before it runs the JS.

In general (with exceptions) place your CSS at the top, JavaScript at the bottom.


### Minimize HTTP Requests

Avoid redirects.

Concatenate CSS and JavaScript to reduce requests.

Use image sprites.

### Leverage Caching

"Cache rules everything around me"

Cache database queries.  Cache the results.  Don't run filters against queries, etc. every time the page loads.

Use a content delivery network (CDN).  Caches a static version of your site across the globe.  Unless you're working with video or something, download speeds aren't your enemy, but latency is limiting, so you place servers at places around the world.

### Reduce Payload

Gzip compresses based on repeated on repeatable strings and can reduce file size by around 70%.

Minifying removes unnecessary comments and spacing, reducing overall file size.

Compress and serve scaled images.

## CSS Performance

### Browser Jank

Vertical synchronization (v-sync), sync'ing the frames so you're running animations between the frames so visibly you're not seeing anything.  The human eye can only interpret about 60fps.  You want to make sure any changes in state happen in between those captures.  You only have the time between screen refreshes to complete a frame (~16ms on a 60Hz screen)

### Two Key Parts

#### Outside Braces

Don't overload your selectors

Avoid ancestors

Avoid tag attributes.

Avoid universal selectors

#### Inside Braces

Eliminate duplicate rulesets (goes back to reducing payload).

Avoid unnecessary repaints.  A repaint occurs when changes are made to an elements appearance but does not affect its layout.

Minimize browser reflow.  Reflow is a big problem.  Reflowing a single element causes reflows of all child and ancestor elements as well as any elements following it in the DOM.  What triggers reflow?  Resizing the window.  Changing the font.  Adding/removing stylesheets.  Content changes such as user input.  Activating CSS pseudo classes.  Calculating offset width and offset height.

### Google Guidelines on CSS Performance Best Practices

* Reduce unnecessary DOM depth
* Minimize CSS rules and remove unused CSS rules
* Do animations out of the flow.  Use position absolute or position fixed to accomplish this.
* Avoid unnecessary complex CSS selectors, descendant selectors in particular, which require more CPU power to do matching

### Think Scalable and Modular

### Tool Time

* Sass/LESS
* Chrome Devtools CSS Profiler
    * Track painting with the timeline
    * Continuous page repainting
* Browserscope.org Reflow Timer
* Grunt/Gulp
* UnCSS
* CSSCSS
