# Adaptive Images in Responsive Web Design
**#rwdimg; by Christopher Schmitt, [@teleject](http://twitter.com/teleject)**

With devices we now have to deal with speed, display size, and higher resolution display (pixel density).  If you know one part it doesn't mean you know other other two parts.  You need to know all three to give them the right image at the right time (referring to raster or jpg images).

**Why don't we ask the browser?**

In the beginning we used to do that with user agent.  That's difficult to do now...

There is the `Client-Hint` proposal that would share that information through headers.

**We can do feature testing**

With JavaScript or CSS media queries.  That gives us some of the inforamtion but not all.  We used to be able to use 72ppi, but Retina displays are at 300ppi.  So images would take up less space and browsers would scale them up and they would look terrible.  We'd prefer to deliver a higher resolution images.  The problem is that when you double the size you 4x the file size.

**Bandwidth?**

Speed tests hinder speed, user experience.

> Testing for speed of an internet connection is like stepping in front of a car to see how fast it is.  [But you only have to do it once.] - Tab Atkins

Speed testing an image requires you do download a 50k image and see how long it took.

There will be a native speed test though, and it is on its way in Modernizr.  Check `navigator.connection`.  Available in Android devices.

**Using img**

`srcset` in `img` allows you to list additional images for different widths (i.e., 200w) or resolutions.  Great for fixed width layout that's a really basic image swapping solution.  We can also use `sizes` in `img` which works in tandem with `srcset`.  `sizes` says if you match this condition, `(max-width: 50em)` shrink down to 50vw.  It's still up to browser to pick which image to use.  But you will use these attributes most of the time.  Basic image swap and you can define it based on how wide the browser is.

**Picture Element**

We take a basic `img` and wrap a `picture` element around it and add `source` elements. 

Use this when you're trying to solve the problem of art direction - you want to swap in a different image based on size - and when you've exausted all other options.

Picturefill 2.0 is a polyfill for `picture`.

**Non-Native Solutions**

24+ other solutions out there.

However, most have 2x HTTP Requests + JS

**Work Arounds and Tricks in Context**

`background-size: 100%`.  FitText is a great polyfill.  Great for headings.  It fits text, and you can scale background images as a webpage scales.

SVG.  It's native in browsers now (IE9+).  Sometimes an SVG will actually be smaller than a PNG.  The main thing with SVG is you want to make sure it's optimized (see SVGO-GUI).  And use `Modernizr.svg`.  And `grunticon`.

Font-based solutions.  Kind of falling out of popularity now.  But there are screenreader issues.  Font-based RWD: thicker/thinner font based on screen size.  Unfortunately font file sizes are avg. 40k/file.  Icon fonts: pretty cool.  But make sure you code your icons in a way that's accessible for screen readers (aria-hidden:true).

Compressed JPEGS.  Compress a large image all the way down to 0 quality in Photoshop.  Serve one image for all size browsers.  But it doesn't work great on certain kinds of images (especially sharp contrast colors).  So you want an image where the histogram is a nice hill rather than a lot of peaks and valleys.  Combine the highly compressed image with the mobile friendly version of the images.

**Future?**

It would be great if we had a solution that was a simple design for users/designers.  A browser/server handshake (like `client-hint`), and an image with the same file but several formats.  Microsoft already did this sith favicon.  The .ico file could share multiple version of the same image in the same file.  Compare that to mobile icons on iOS where you need several multiple versions.

