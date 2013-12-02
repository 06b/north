North
====================
**Align and Guide Your Project**

North is a set of standards and best practices for developing modern web based properties. Included are standards and best practices for all aspects of a project, from kick off through development. North encourages an agile, content-first, approach to product development and a mobile-first, in-browser, system based approach to design and development.

North is meant to be a living document. Standards and best practices change, and as they do and have been vetted, North will grow and change with them. North will be versioned using [SEMVER](http://semver.org/) to provide a way for you to specify what version of North you are using for your project.

*This project is currently a work in progress*

## Table of Contents

1. Development Process
2. Content Strategy
3. [Visual Design](#visual-design)
	* [Design in Browser](#design-in-browser)
		* [Pair Design](#pair-design)
		* [Sketching](#sketching)
	* [Rapid Prototyping](#rapid-prototyping)
	* [Style Prototyping](#style-prototyping)
		* [Style Tiles](#style-tiles)
		* [Style Guide](#style-guide)
		* [Component Guide](#component-guide)
		* [Layout Guide](#layout-guide)
4. [Responsive Web Design](#responsive-web-design)
	* [Future Friendly](#future-friendly)
	* [Device Detection](#device-detection)
	* [Progressive Enhancement](#progressive-enhancement)
		* [Feature Detection](#feature-detection)
		* [Graceful Degradation](#graceful-degradation)
5. [Performance](#performance)
	* [Testing and Grading Performance](#testing-and-grading-performance)
	* [Payload Performance](#payload-performance)
	* [Page Performance](#page-performance)
	* [Front End Optimizations](#front-end-optimizations)
		* [Critical Optimizations](#critical-optimizations)
		* [Recommended Optimizations](#recommended-optimizations)
		* [Experimental Optimizations](#experimental-optimizations)
6. [Website Building Blocks](#website-building-blocks)
  * [Markup](#markup)
	  * [HTML Semantics](#html-semantics)
	  * [Accessibility](#]accessibility)
	  * [RDFa](#rdfa)
	  * [Viewport Meta Tag](#viewport-meta-tag)
  * [Styling](#styling)
	  * [Base Browser Styling](#base-browser-styling)
	  * [Components](#components)
	  * [Layouts](#layouts)
	  * [Aspects](#aspects)
	  * [Elements](#elements)
	  * [CSS Naming Conventions](#css-naming-conventions)
	  * [Sass and Compass](#sass-and-compass)
	    * [Mixin/Extend Pattern](#mixinextend-pattern)
	    * [Partial Structure](#partial-structure)
  * [Interaction](#interaction)
	  * [Style and Syntax](#style-and-syntax)
	  * [Libraries, Plugins, and Frameworks](#libraries-plugins-and-frameworks)
	  
# Content Strategy

# Visual Design

As the web comes into its own as a medium and the [rituals of print design](http://snugug.github.io/designing-the-modern-web/#/ritual) are cast off, websites can no longer be designed in the same tools built for print design. Websites have interaction, states change, items come in and out. The [differences in browsers browsers](#progressive-enhancement) force designs to change based on capabilities available. Even something as simple as screen size is not static. As [Brad Frost put it](https://twitter.com/brad_frost/status/195241868383092736), "You can't articulate fluidity on paper." The reality of the web has always been that a single, static bitmap representation of a page isn't what a final site will be, it's just taken the push of [responsive web design](#responsive-web-design) to bring the web into its own as a medium. In order to accommodate for the fluidity and flexibility of the medium of the web, new tools and techniques are needed to create a site's look and feel.

## Design in Browser

**Photoshop is not a web design tool.** It's even in the name; *photo*shop. All static website drawings (often called mockups, mocks, comps) are nothing more than a representation, many times a fairly inaccurate one, of what a site may look like when finally built. In the world of the fluid and flexible web, [a pixel is not a pixel](http://alistapart.com/article/a-pixel-identity-crisis/), in fact, **pixel perfect does not exist**.

> Guess what. The web's not a laser printer.
>
> *Karen McGrane*

To combat these inaccuracies, instead of designing websites in static graphic design tools, design should take place with the tools of the web; [HTML](#markup), [CSS](#styling), and [JavaScript](#interaction). This goes for both user interface design (UI) and user experience design (UX). UX should be sussed out utilizing [rapid prototyping](#rapid-prototyping) and UI utilizing [style prototyping](#style-prototyping). By doing so, what gets signed off on by the client is work that inherently conforms to the realities of the web as opposed to a picture that may or may not. In addition, by designing in browser, how design choices affect [performance](#performance) can be readily seen allowing for performance to be part of the design process, not an afterthought.

Because design decisions will need to be made throughout the lifespan of a project, the designers (both UI and UX) responsible for the design of a site need to be part of the full lifecycle of a project and cannot simply hand off initial designs and walk away from a project when development starts.

### Pair Design

One proven method of transitioning design teams from designing in bitmap tools to designing in browser is to pair designers with front end developers in a method similar to [pair programing](http://en.wikipedia.org/wiki/Pair_programming). With pair design, the front end developer acts as hands and the designer acts as the eyes. The two then work together to create a design. As this is happening, the developer should encourage the designer write code and the designer should encourage the developer to give input into the design and suggest technical solutions to design challenges or decisions.

During this process, it is also helpful for front end developers to create reusable patters in CSS (especially around creating functions and mixins in [Sass](#sass-and-compass)) and explain to and work with the designer to enhance these patterns, allowing the designer to get comfortable writing pattern-based code. This also lays the foundation for rapid iteration of a design idea.

Eventually, the designer should be allowed to take over full responsibility of coding and designing with the front end developer moving on to focus their efforts on [semantics](#html-semantics), [accessibility](#accessibility), and [JavaScript](#interaction).

### Sketching

While designing in browser is the standard to achieve for, many times a designer will want to work out design ideas outside of browser. This may include a static graphic design tool, pencil and paper, tablet sketching app, or anything else they may find handy. This is encouraged! However, what is produced through these design sessions should be considered sketches and should not be a deliverable to be signed off on by the client. All work to be signed off on must be in browser.

## Rapid Prototyping

Rapid prototyping is a technique used to quickly create example interactions, styles, or flows. Traditionally done through code, although [paper prototyping](http://alistapart.com/article/paperprototyping) would fall under rapid prototyping, rapid prototypes are meant for demonstration purposes. Built as stand-alone projects to demonstrate a single purpose, they are used to demonstrate an idea or suss out a UI or UX problem. They also are a great tool for experimenting different options quickly. When finished, rapid prototypes can be used to create production ready code (once all gates for production ready code, including cross-browser testing, have been completed).

## Style Prototyping

Style prototyping is a technique used to create a typical instance of a design from which a final site can be assembled. A style prototype is a combination of a [style tile](#style-tiles), [style guide](#style-guide) a [component guide](#component-guide), and a [layout guide](#layout-guide). A tool for generating style prototypes, happily called [Style Prototypes](https://github.com/team-sass/generator-style-prototype), is a [Yeoman](http://yeoman.io/) generator for quickly and easily creating style prototypes and includes a [content strategy](#content-strategy) and a color guide as well as the standard set of items for a style prototype. It also is set up to create a Compass extension out of the prototype in order to drop the styling in to a project easily.

### Style Tiles

To quote the [style tiles site](http://styletil.es/):

> Style Tiles are a design deliverable consisting of fonts, colors and interface elements that communicate the essence of a visual brand for the web.

The main idea behind style tiles is that moodboards are too vague to get a real sense of look and feel and mockups are too precise, with clients and designers futzing over pixel-level precision instead of overall look and feel. Style tiles provide an abstracted but precise way of getting look and feel across that exists between the two extremes. They provide the core set of design decisions needed for a responsive site, fonts, coloring, and font size relations, without creating pages. When done in browser, it becomes trivial to see how these decisions work across browsers, devices, and operating systems. This is especially helpful for fonts which [render differently pretty much everywhere](http://blog.typekit.com/2010/10/05/type-rendering-on-the-web/). Style tiles also lay the groundwork for [style guides](#style-guide), and components from the [component guide](#component-guide) can be easily brought in to get a larger view of how style decisions affect components.

### Style Guide

A style guide is the core set of styling for each element on a page. It is the combined [base browser styling reset](#base-browser-styling) and the [base component](#base-component) styling, so it may be referred to as either the base guide or element guide as well. Items styled in the style guide should be contained under the `.base--STYLED` class as basic styling should not bleed outside of that class. Each element in in a style guide should include the markup required to create it as well as the styling applied to allow for easy reference and self documentation.

### Component Guide

A component guide is a listing of each [component](#components) for a project, grouped by component, with a rendered display of each aspect utilizing each of the component's elements. Accompanying each aspect display should be the markup and styling used. Each component group should include a listing of available element, the available extendable classes, mixins, and variables. If a component has JavaScript associated with it, the JavaScript filename should be included along with the source code.

### Layout Guide

A layout guide is a listing of each [layout](#layouts) for a project , grouped by layout, with a rendered display of each aspect utilizing each of the layout's elements. Accompanying each aspect display should be the markup and styling used. Each layout group should include a listing of available element, the available extendable classes, mixins, and variables. If a component has JavaScript associated with it, the JavaScript filename should be included along with the source code. Layout guides should not include components in their display, but should rather use placeholder components (generally, a grey box).

# Responsive Web Design

> 'Responsive' is not a line item. It's Design
>
> *Jason Pamental*

Responsive web design (RWD) is an approach to design that, as [Brad Frost](http://bradfrostweb.com/blog/web/responsive-web-design-missing-the-point/) eloquently puts it, attempts to "…create functional (and hopefully optimal) user experiences for a growing number of web-enabled devices and contexts." Users don't care if a site is responsive or not, what users care about is that all content is available, navigable, and predictable at the same place regardless of what device they choose to access a given site from. They care that it is fast, reliable, and accessible. [Performance](#performance) is of the upmost importance. This is especially true for mobile, where a [57% of users will abandon a site after waiting 3 seconds for a page to load](http://www.strangeloopnetworks.com/web-performance-infographics/) and 80% of those users will not return. So RWD is not about making a design squish to fit phones, tablets, and desktops; it is really a methodology to deliver content in a compelling and performant manner regardless of how a user chooses to access that content.

## Future Friendly

The methodology of RWD is a methodology of creating sites that are [Future Friendly](http://futurefriend.ly/). The core tenants of being future friendly are as follows:

1. Acknowledge and embrace unpredictability.
2. Think and behave in a [future-friendly way](http://futurefriend.ly/thinking.html).
	* We can't be all things to **all** devices.
	* Create meaningful content and services.
	* Design services and information architecture [content](http://adactio.com/journal/4523/) and [mobile](http://www.lukew.com/ff/entry.asp?933) first
	* Design content models to be used across presentations (website, apps, APIs, etc…)
	* Design content models around standards to be interoperable. Focus on its long term integrity
	* Having well-structured content is essential to art direction. Structure and store content accordingly
3. Help others do the same.

The set of suggestions from the Future Friendly manifesto that should not be followed as written are those dealing with device categorization and [device detection](#device-detection). The sentiment is correct, enhance any given device with a user experience that is tailored to its capabilities, but that should be done using [progressive enhancement](#progressive-enhancement) and [feature detection](#feature-detection) instead. Creating enhanced experiences this way, and encouraging users to take advantage of those enhanced experiences (as opposed to forcing them upon users based on their user agent string) allows for a more sustainable and future looking approach to delivering these experiences.

## Device Detection

#### Don't Do It.

Device detection is a bad and unsustainable practice. Relying upon current knowledge, device detection is a method of identifying a device based on its [User Agent String](http://en.wikipedia.org/wiki/User_agent). This is a poor method of identification in and of itself; it is based on current knowledge, meaning that lists need to be maintained and can only be updated after a device has been released, making said lists consistently out of date. Additionally, if used for categorizing devices, for instance into phone, tablet, and desktop devices, it requires subjective determinations that may or may not reflect the realities of the actual device and its user, and itself pushes lists out of date and can create divergent lists. Oh, and user agent strings can (and often times, especially on the mobile web, do) be faked to emulate the user agent string of another device and/or browser. It should go without saying that using user agent strings to determine and pivot on browsers and browser versions should also not be done.

Device detection extends to choices made when designing sites as well, not just user agent strings. Common examples of non user agent string device detection include mimicking iOS native app visual styling and user experience patterns on the web, constraining designs to "phone", "tablet", and "desktop" sizes (or "small", "medium", and "large"), choosing media queries and breakpoints based on "common" device sizes, and making assumptions about features based on screen size (such as small screens have touch capabilities).

The reason device and/or browser detection was used in the past, and some still believe it has a place in a modern web development workflow, is because it is often used as a means to make guesses at the features available to work with or at the stereotypical expected user behavior. Unfortunately, it is a pretty terrible tool for doing both. On the feature side, there is a widely accepted best practice of using [progressive enhancement](#progressive-enhancement) and [feature detection](#feature-detection) to "ask" a browser what features are available and enhance the experience with those features. This approach means that a web page can adapt to what is actually available in a way that works across all past, present, and future devices in a way that is much more reliable and hardy than device detection. On the expected user behavior side, as [Josh Clark points out](http://globalmoxie.com/jhc/prez/mobile-myths.pdf):

> Any time you say somebody won't want that on their phone, you're wrong.

and

> If it's not good for the mobile user, it's not good for any user. We're the same people.

While talking about mobile, the point is as follows: users are the same regardless of the device they choose to use. Assuming a user has a different set of wants or needs exclusively based on the fact a user agent string says they are using a tablet device will always be wrong. Bring personal experience into decision making; when browsing a resultant website on your phone, are your wants and needs there all that different than when you do so on a desktop computer?

> Mobile users want to see our menu, hours, and delivery number. Desktop users definitely want this 1MB .png of someone smiling at a salad.
>
> *Mat Marquis*

## Progressive Enhancement

Take away what we can't know: screen size, device capabilities, concurrent activities, depth of focus, purpose of visit.

> Take away the make believe. Take away what we can't know. They're fantasies.
>
> *Jason Pamental*

Since about 2003, [Progressive Enhancement](http://alistapart.com/article/understandingprogressiveenhancement) has been a technique that has been used to create sites that work across any and all browsers and devices, from screen readers and and search engine spiders to the most bleeding edge alpha browsers on the highest end computers. The technique can be boiled down fairly simply: start with content that is richly marked up semantic HTML and layer on everything else, from styling to interactions, after. By building websites content and markup first, it allows everything from the most sparse browser to the most robust one (and everything in between) to get an experience that works well for their capabilities.

When building sites, they should always be built content first. Once the content is built, each enhancement that is added, from styling to interaction, should be added with this in mind. A good experience needs to be available to all users; do not design pages for the most cutting-edge browsers, design for the content.

### Feature Detection

Progressive Enhancement isn't regulated to broad features like all styling or all interactions, but can and should be done on a feature-by-feature level as well. They best way to determine what level of support a given browser has is to ask it. The most widely used feature detection library is [Modernizr](http://modernizr.com/). Modernizr is a tool built and maintained by some of the leading minds in web development today, and should be considered the go-to solution for feature detection.

Where feature detection based progressive enhancement differs from standard progressive enhancement is that where standard progressive enhancement is concerned with the whole site and the overall user experience, feature detection based progressive enhancement is generally based around a single user experience enhancement, such as a flexbox powered layout or a location based enhancement to search.

When adding in feature-specific enhancements, they should only be loaded in if that feature is available in a given browser. This should be done asynchronously. This provides a site with two levels of progressive enhancement, the core set of content to shared feature set and experience, followed by additional enhancements for feature-specific experience enhancements. Modernizr's [load](http://modernizr.com/docs/#load) option allows for asynchronous loading of resources, especially useful when used in conjunction with Modernizr feature tests.

### Graceful Degradation

Whereas progressive enhancement starts with content and enhances up the experience until a full web page is built, graceful degradation starts with a completed web page built to support the newsiest and most capable browsers and ensure the experience is passable in less capable browsers. While progressive enhancement is always the preferred route to take by default, there are times in projects where graceful degradation can be an approach worth considering, for instance when it comes to [polyfilling](http://remysharp.com/2010/10/08/what-is-a-polyfill/) support for HTML5's semantic tags for browsers that do not support them or providing styling that would be constrained to media queries to browsers that likewise do not support them.

# Performance

When building modern websites, performance is a real design and development constraint and must be taken into account at every level of the development process. The reason it is a design and development constraint is fairly simple: with the explosion of an everything-conencted world and the rise of the mobile-only user, the chances that a site is going to be viewed primarily by someone sitting at a workstation with a high speed internet connection diminishes daily. This constraint isn't new either; way back in 2006, Amazon reported that a [100ms delay cost them 1% of sales](https://sites.google.com/site/glinden/Home/StanfordDataMining.2006-11-28.ppt?attredirects=0). This was before the great reach of broadband took hold and before the current mobile computing boom came full swing, which have only lessened the patience of consumers. As [Compuware Reports](http://e-commercefacts.com/research/2011/07/what-usrs-want-from-mobil/19986_WhatMobileUsersWant_Wp.pdf), *75% of mobile web users expect a site to load as fast or faster* on their mobile devices as they do their desktop computers, with *60% of mobile web users leaving a site and not coming back if it takes more than 3 seconds to load, with 78% of users trying only one more time*. Moreover, if a user abandons your mobile site, *33% will go to a competitor's site*. What all this means is that **performance affects website revenue**. Google, helpfully, provides some interesting insight into how performance could have affected their 2011 revenue:

* Google made approximately [$18.8 Million](http://blog.hubspot.com/blog/tabid/6307/bid/33784/An-Industry-Breakdown-of-Google-s-100-Million-Per-Day-Advertising-Revenue-INFOGRAPHIC.aspx) per day on search advertising.
* A 400ms delay (less than half of a second) [reduces average number of daily searches by 0.59%](http://www.igvita.com/slides/2013/breaking-1s-mobile-barrier.pdf) (and is about twice their warning threshold)
* That amounts to a **daily loss of $111,000**, or about **$40.5 Million a year**

When discussing and testing performance, it is important to do both with an eye toward mobile. This means that all performance testing needs to take place on actual devices, not just emulations, and on actual networks. Many of the standards have some wiggle room, but presented are the ideals and maximums for performance standards. The ideals and maximums have been chosen with an eye towards the realities of a media heavy site, including the realities of advertising and heavy multimedia usage. As [80% of the end-user response time is spend on the front-end](http://developer.yahoo.com/blogs/ydn/high-performance-sites-rule-1-fewer-http-requests-7163.html), most of the performance suggestions are front-end based.

## Testing and Grading Performance

In addition to the below, sites should be able to hit and maintain certain performance benchmarks from a variety of different resources across the internet. These systems are a good way of doing easy tests of a site to determine how they stack up. The following are good testing and grading resources, and the minimum target scores for each resource:

* [Page Speed](https://developers.google.com/speed/pagespeed/insights) - 85
* [Web Page Test](http://www.webpagetest.org/)
	* First Byte Time: 85
	* Use persistent connection: 85
	* Use gzip compression for transferring compressable responses: 90
	* Compress Images: 90
	* Use Progressive JPEGs: 90
	* Leverage browser caching of static assets: 90
	* Use a CDN for all static assets: 85
* [YSlow](http://developer.yahoo.com/yslow/) - 85

## Payload Performance

Load times, load sizes, and number of requests are extraordinary important and often overlooked or left to the end of a development cycle to start to optimize. Ideal statistics are presented first, with maximums presented second that should only be broached under edge circumstances. It is always best to keep actual performance as much under these numbers as possible.

* *Time To First Byte:* **200ms** - 350ms
* *DOM Content Loaded:* **1000ms** - 2000ms
* *JS Load Event Fired:* **900ms** - 2200ms
* *Total Download Size:* **1MB** - 2MB
* *DNS Lookup:* **10ms** - 20ms
* *HTTP Requests:* **50** - 75

## Page Performance

Once a site has been downloaded, performance of the user interactions is important as well. The goal to reach for is a site running at or above **60 frames per second**. Anything below this makes sites appear poorly built, sluggish, and unresponsive. When dealing with user input, interactions should be **under 100ms to feel instant** and **under 250ms to feel fast**. Anything longer and interactions begin to feel sluggish. Some good rules of thumb to avoid the user interface from feeling this way are:

* Do not bind expensive processes to document/window events (scroll, resize, etc…)
* [Use CSS3 `translate`](http://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/) instead of absolute position with top and left properties
* Do not emulate fixed positioning using JavaScript
* Animate through CSS3 instead of JavaScript
* Group JavaScript document reads and writes separately. Use [`requestAnimationFrame` to reduce layout thrashing](http://www.paulirish.com/2011/requestanimationframe-for-smart-animating/) when reading and writing to the DOM
* Avoid Internet Explorer's CSS expression selectors

## Front End Optimizations

There are a number of optimization techniques that can be employed in order to enhance overall performance on a site. Some of these are battle-hardened optimizations that should be employed on all sites, while others are more experimental. As such, they will be divided into categories based on which are most critical for success, and which can be played with.

### Critical Optimizations

* Avoid page redirects
* Provide proper headers for all files
	* Static files (fonts, js, css) should have sufficiently long cache, at least 30 days
	* Images should have a slightly shorter cache, at least 15 days
	* HTML should have a short cache, around 15 minutes
	* Internet Explorer Edge header should always be passed
* All JavaScript should be moved to the footer
* `document.write` should be avoided
* Images with no transparency should be served as progressive JPEGs, not as PNG files
* CSS and JavaScript should be minified and aggregated
* Reduce all blocking in the [critical path](http://sethgodin.typepad.com/seths_blog/2013/11/understanding-critical-path.html) to only page HTML and CSS
* Do not group CSS by media in `<link>` tags; all of the CSS gets downloaded any. Instead, reduce number of aggregates and wrap internal CSS in media queries.
* Use a CDN
* Cache page requests
* Utilize [progressive enhancement](http://alistapart.com/article/understandingprogressiveenhancement) with [feature detection](http://modernizr.com/) to server only what is needed to a user
* Ensure that files that are only useful on particular pages only load on those pages, not all pages
* Always load CSS before JavaScript

### Recommended Optimizations

* Lazy load non-critical content. See Filament Group's [Ajax-Include Pattern](https://github.com/filamentgroup/Ajax-Include-Pattern/)
* Employ a Responsive Image solution. Until a standard exists, look for one based on image width over viewport size.
* `ASYNC` and `DEFER` all on-page scripts (for instance, DART tags). See [$script.js](https://github.com/ded/script.js) for a light weight async JavaScript loader
* `ASYNC` all ads
* When utilizing a CDN such as Akami, use that to serve scripts such as jQuery instead of Google's CDN as it will be faster on a cold cache
* Inline small but important files (generally <3Kb) to reduce HTTP requests. Aggregate other small files to reduce HTTP requests

### Experimental Optimizations

* Inline above-the-fold CSS into the HTML. Push additional CSS to the footer
* Utilize [.webp](https://developers.google.com/speed/webp/) and [.webm](http://www.webmproject.org/) file formats
* Employ the [spdy](http://www.chromium.org/spdy/spdy-whitepaper) protocol
* Dynamically serve appropriately sized images from server side instead of relying upon a client side technique

# Website Building Blocks

No matter what back end technology is used to generate a website, when it gets rendered to a page it always becomes HTML, CSS, and JavaScript when displayed in browser. As such, a common set of best practices can be employed to ensure that what the user gets is as good as it can be, regardless of the device or method they choose to browse the site with. The methodology described below presents a content focused, component based, semantic, and accessible approach for building web sites. Designing this way is challenging, and requires a different approach than traditional desktop-sized Photoshop documents. That will be covered in other sections of this document, but one of the best ways to design this way is in browser using [Style Prototypes](https://github.com/Team-Sass/generator-style-prototype).

## Markup

The core of every website is the underlying markup that, through [styling](#styling) and [interaction](#interaction), gets transformed into a web experience. This underlying code is the heart and soul of every site and should be treated as such. By properly utilizing HTML5 semantic markup and ensuring content is accessible and properly marked up with Resource Description Framework in Attributes (RDFa), websites will be able to achieve better search engine optimization (SEO) and ensure that the content will be highly available no matter the accessing system and last long in to the future.

### HTML Semantics

When developing websites, HTML semantic tags should be used and the HTML5 standard should be utilized. Any elements that are obsolete or deprecated as of HTML5 should not be used. For a complete listing of available HTML elements and their defined meaning, see the [Web Platform Elements Reference](http://docs.webplatform.org/wiki/html/elements). The proper semantics for each element should always be used, for instance, the `<table>` element should only be used to mark up tabular data, never for layout or lists. Elements designed for style, such as `<b>` and `<center>` should never be used and should be done through styling instead. Should confusion arise as to exactly how to use a given element, or if its definition is not clear, [HTML5 Doctor](http://html5doctor.com/)is an excellent supplementary resource to Web Platform. If support is needed for browsers that do not natively implement all semantic elements, the [HTML5 Shiv](https://github.com/aFarkas/html5shiv) should be conditionally made available.

### Accessibility

The accessibility of a web site's content, including its source order without any applied CSS or JavaScript, must be taken into account. [Web Platform's Accessibility Basics](http://docs.webplatform.org/wiki/concepts/accessibility) article is a good introduction to accessibility for those unfamiliar with them. During development, websites should be checked with a screen reader to ensure they are easy to use. All developers using Apple computers or that have access to iOS device have access to [VoiceOver](http://www.apple.com/accessibility/osx/voiceover/) as it is installed on both operating systems. VoiceOver, especially on iOS devices, is an extremely popular screen reading application and will allow for inexpensive accessibility testing on a product users actually use. Another popular screen reading application, especially for Windows machines, is [JAWS](http://www.freedomscientific.com/products/fs/jaws-product-page.asp), although that is proprietary software and fairly expensive at that. A final resource for testing accessibility is to access a website using the [Lynx Browser](http://lynx.browser.org/). As a text-only browser, it will strip out styling and interactions, leaving raw content in the order it is presented. As an added bonus, this is also a good analogue to how crawlers and search engines view a given page.

### RDFa

[Resource Description Framework in Attributes](http://www.w3.org/TR/rdfa-primer/), more commonly known as [RDFa](http://rdfa.info/), is an extension to HTML5 allowing for robust markup of objects in HTML, including items such as people, places, events, recipes, and reviews. They are used to precisely describe these objects, mostly to machines, by attaching metadata about each object as attributes. The most common immediate use for this metadata is in use by search engines and social networks, amongst others, allowing their crawlers to understand exactly what is on any given page. This, in turn, allows them to provide more accurate and higher ranked information about each piece of content. A useful side effect of marking up all content with RDFa information, especially when using a Content Management System (CMS), is that it ensures that all of the relevant metadata is readily available in individual chunks and thus becomes fine-grain points of control for each piece of content that can be syndicated outside of pure markup.

### Viewport Meta Tag

When building responsive websites, for the time being, a non-standard meta tag needs to be used in order to tell browsers how to react. This is colloquy known as a "viewport tag". While there are many options that can go in to the viewport tag, the tag, in its entirety, that should be used is as follows:

`<meta name="viewport" content="initial-scale=1.0">`

There is currently a [CSS Device Adaptation](http://dev.w3.org/csswg/css-device-adapt/) development specification in the works which, when done, will move this from a markup tag to a CSS directive known as the [`@viewport`](http://dev.w3.org/csswg/css-device-adapt/#the-atviewport-rule) directive. Currently, Internet Explorer 10 and up, including on mobile devices, does not use the viewport tag, but rather the viewport directive, so both should be included on all projects.

## Styling

If markup is the skeleton of a website, styling is the funny hat. Through CSS, a stack of content on a page can become flexible and fantastically flourished. With the introduction of CSS3, styling can now include such fanciful additions such as animations, perspective, and even 3D. But with all of this power, and all of this responsibility, a firm structure to create a system of style needs to be in place or else everything can run off of the tracks. Below represents a component based systematic approach to styling.

### Base Browser Styling

Due to lack of standards around it, each browser manufacturer creates their own styling for their browser, leaving each browser's default base rendering of elements different. This, of course, causes inconsistencies across browsers that must be fixed. The two most prominent ways of doing this is through either to [reset](http://meyerweb.com/eric/tools/css/reset/) or [normalize](http://necolas.github.io/normalize.css/) the appearance of all elements. While normalization has become the go-to method for many projects recently, it introduces can introduce new issues into the cascade. This is the same reason it is recommended to create a [base component](#base-component) instead of allowing site-specific base styling to cascade throughout the entire site. Because of this, it is recommended to use the **reset** method; preferable one that discreetly targets the elements that need resets, fixes the bugs that the common Normalize.css fixes, and adds the correct baselines for HTML5 elements if they are not otherwise recognized (for instance, applying `display: block` to the `<main>` element).

### Components

Components are the primary building block of any interface. They are the bits and bobs that combine to form a cohesive user interface; from menus to messages, pagers to pictures, and everything else in between. Components should be written to be able to be dropped in to any position in a layout. The way to accomplish this is to build components using [**eq.js**](https://github.com/snugug/eq.js). This will allow a component and its elements to respond appropriately regardless of where they land in a given document flow. Components should simple layouts to position elements inside of themselves either through extends or by constructing a component with elements placed inside an internal layout (decide before starting a project and carry that decision through the lifespan of the project) if the layout is not component specific. They may choose to control their overall sizing and one-off sizing and positioning, but those choices should be relative the container they are dropped in to and not layout or position specific.

#### Base Component

Each project should contain a `base` component which contains base styling for raw tags (`h2`, `blockquote`, `p`, etc…). The `base` component's elements should be named after the tag they style, so basic styling for `h2` would provide both an extendable and full class `.base--h2`. To apply these styles, create a `styled` aspect, providing a `.base--STYLED` class. This aspect should have raw elements styled without classes, allowing it to be dropped into any section of a site and provide basic styling. Additional aspects can be created to create different base stylings.

### Layouts

Layouts are the structure of an interface. Providing structure to pages and components, layouts are responsible for sizing and positioning of their elements. There are two kinds of layouts, simple and complex. The distinguishing factor between simple and complex layouts is that complex layouts adapt and change their sizing and positioning based on media queries whereas simple layouts do not. Complex layouts are generally used for laying out pages and regions within pages, with simple layouts being used for laying out sub-sections inside complex layouts and providing common layouts for components. While simple layouts may be used within components or even within other simple or complex layouts, complex layouts should never be used within one another.

### Aspects

Aspects are a specific implementation of a component or layout. Components and layouts always should have an aspect when used to determine what kind implementation is being worked with. Aspects can be used as a way to pivot styling of elements if need be or to control implementation-specific styling, such as changing colors in a message component or determining exact sizing of a body element of a layout. It is preferable to use aspects as pivot points than to create unique classes for each element as it allows for the reuse of identical elements regardless of the aspect of a component or layout they are used in.

### Elements

Elements are the individual pieces that make up a component or layout, each being component or layout specific. Think of them as individual elements (`h2`, `blockquote`, `p`, etc…) in components and regions and items in layouts. When styling an item inside components or layouts, it is strongly discouraged to use raw tag selectors and instead use element classes for each. This is to avoid any potential conflicts, such as would happen if you have a pager component inside of a slider component (`.slider li` and `.pager li`). The only exception to this rule is for the [base component](#base-component).

### States

States provide a way to alter how a component, layout, element, or aspect behaves. Common states include `active`, `open`, and `closed`. Because states live in the in-between world of JavaScript and CSS, often changing with interactions from the user, states are controlled by data attributes and get attached to the components, layouts, elements, or aspects they are modifying. This provides easy to maintain states on a per-object basis without needing per-object states.

### CSS Naming Conventions

Components and layouts form prefixes the prefixes for aspects and elements, separated by double dash (`--`). Simple layouts start with an underscore (`_`) and complex layouts start with two underscores (`__`) to distinguish them from components, and aspects are written in all caps (`CAPS`) to distinguish them from elements, written in all lowercase (`lowercase`). States are applied to the state data attribute (`data-state`) and queried using attribute selectors as they have the strong tendency to either be manipulated by JavaScript or be used as a hook for JavaScript. A sample document written up using this naming convention could look like the following:

```html
<!-- Article layout with Big Media aspect -->
<div class="__article--BIG-MEDIA">
  <!-- Main element of Article layout -->
  <article class="__article--main">
    <!-- Heading element of Article layout -->
    <div class="__article--heading">
      <!-- PRIMARY Heading aspect of Typography component -->
      <h1 class="typography--PRIMARY-HEADING">Article Title</h1>
    </div>
    <!-- Media element of Article layout -->
    <figure class="_article--media">
      <!-- Video components, Full HD aspect -->
      <div class="video--FULL-HD">
        <!-- Video element of Video component -->
        <video class="video--video" />
      </div>
    </figure>
    <!-- Body element of Article layout, Area aspect of Typography component  -->
    <div class="__article--body typography--AREA">
      <h2>Some user entered copy goes here</h2>
      <p>Yay Copy!</p>
    </div>
  </article>
  <!-- Secondary element of Article layout  -->
  <aside class="__article--secondary">
    <!-- Popular aspect of Related component -->
    <div class="related--POPULAR">
      <!-- Heading element of Related component -->
      <div class="related--heading">
        <!-- Tertiary Heading aspect of Typography component -->
	     <h2 class="typography--TERTIARY-HEADING">Block Title</h2>
	   </div>
	   <!-- Body element of Related component -->
	   <div class="related--body">
	     <p>Yay Copy!</p>
	   </div>
	 </div>
  <aside>
</div>
```

### Sass and Compass

When writing CSS, use [Sass](http://sass-lang.com/) with the [Compass](http://compass-style.org/) authoring framework. When compiling Sass and Compass, only use the Ruby gems to compile them or a tool that calls out to the Ruby gems. The `scss` syntax should be used exclusively when writing and sharing Sass. In order to ensure that all environments are the same, the minimum version of Ruby that should be used is `2.0.0` (standard on OS X version 10.9 and up) and all gems should be installed and versions managed by [Bundler](http://bundler.io/). When writing a [Gemfile](http://bundler.io/v1.5/gemfile.html), versions should all be specified using the `~>` specifier to ensure that gems stay on the same major and minor versions, making upgrades in minor versions purposeful. Gems should be installed in to a `vendor` folder in each project, which should be ignored from version control. In addition to Bundler, there are a number of Compass extensions that should be used as a standard for a variety of needs.

* [Singularity](https://github.com/Team-Sass/Singularity) - Grid framework
* [Breakpoint](https://github.com/Team-Sass/breakpoint) - Media query framework
* [Toolkit](https://github.com/team-sass/toolkit) - Variety of useful tools for web design and development
* [Jacket](https://github.com/Team-Sass/jacket) - Tool for deciding what gets printed in a given stylesheet
* [Color Schemer](https://github.com/Team-Sass/color-schemer) - Advanced color functions
* [Modular Scale](https://github.com/Team-Sass/modular-scale) - Numeric relationships, especially for typography

The following should be using the standard [Compass configuration](http://compass-style.org/help/tutorials/configuration-reference/) for all projects:

```ruby
# Set this to the root of your project when deployed:
http_path = "/"
css_dir = "css"
sass_dir = "sass"
images_dir = "images"
javascripts_dir = "js"
fonts_dir = "fonts"

# You can select your preferred output style here (can be overridden via the command line):
# output_style = :compressed

# To enable relative paths to assets via compass helper functions. Uncomment:
relative_assets = true

# To disable debugging comments that display the original location of your selectors. Uncomment:
line_comments = false
```


#### Mixin/Extend Pattern

Mixins are best used when they don't needlessly duplicate the properties they write. We can do this using placeholder selectors and `@extend`. The only properties that should be erectly written to the selector calling a mixin should be properties that have been directly altered due to mixin arguments. Any other properties should be extended. All arguments that have default values should have those default values controlled by globally namespaced `!default` variables to make overriding those defaults easy and accessible. All mixins that provide extends should also have an `$extend` optional argument, ideally as its last argument, also globally defaulted.

Mixins should also be divided up by purpose. While an omni mixin may be easier to write, having smaller mixins will make maintaining and using your mixins, as well as changing discrete parts of a rendered component, easier to do.

Let's take a look at a typical message component mixin as an example of how to re-write it using our mixin/extend pattern.

```scss
// Sass
@mixin message($color, $padding: .25em .5em, $width: 80%) {
  box-sizing: border-box;
  padding: $padding;

  width: $width;
  margin: 0 auto;

  border: 2px solid $color;
  background: mix(white, $color, 25%);
  color: mix(black, $color, 25%);
}

.message--STATUS {
    @include message(green);
}

.message--WARNING {
    @include message(yellow);
}

.message--ERROR {
    @include message(red);
}
```

```css
/* CSS */
.message--STATUS {
  box-sizing: border-box;
  padding: .25em .5em;
  width: 80%;
  margin: 0 auto;
  border: 2px solid green;
  background: #3f9f3f;
  color: #006000;
}

.message--WARNING {
  box-sizing: border-box;
  padding: .25em .5em;
  width: 80%;
  margin: 0 auto;
  border: 2px solid yellow;
  background: #ffff3f;
  color: #bfbf00;
}

.message--ERROR {
  box-sizing: border-box;
  padding: .25em .5em;
  width: 80%;
  margin: 0 auto;
  border: 2px solid red;
  background: #ff3f3f;
  color: #bf0000;
}
```

While the single mixin may allow us to easily get the output we want, it does so at the cost of duplicating properties, and thus vastly bloating, our output CSS. This can be remedied almost entirely simply by rewriting our original mixin using our new mixin/extend pattern.

```scss
// Sass
$message-padding: .25em .5em !default;
$message-width: 80% !default;
$message-extend: true !default;

@mixin message--CORE($padding: $message-padding, $width: $message-width, $extend: $message-extend) {
  // If we're not extending ($extend == false), we write properties directly
  @if not $extend {
    box-sizing: border-box;
    padding: $padding;
    
    width: $width;
    margin: 0 auto;
    
    // Border's color is based off of the `color` property, so we can write valid 
    //  shorthand without the color. Border options aren't dynamic to clearly show a 
    //  succinctly show this short hand method.
    border: 2px solid;
  }
  @else {
    // If we are extending ($extend == true), we extend the placeholder selector
    @extend %message--CORE;
    // If $padding is different than our default padding, we write that property
    @if $padding != $message-padding {
        padding: $padding;
    }
    // If $width is different than our default width, we write that property
    @if $width != $message-width {
      width: $width;
    }
  }
}

@mixin message-coloring($color) {
  border-color: $color;
  background: mix(white, $color, 25%);
  color: mix(black, $color, 25%);
}

%message--CORE {
  // We include the message-core mixin with $extend == false to force the properties to be written
  @include message--CORE($extend: false);
}

.message--STATUS {
  @include message--CORE;
  @include message-coloring(green);
}

.message--WARNING {
  @include message--CORE;
  @include message-coloring(yellow);
}

.message--ERROR {
  @include message--CORE;
  @include message-coloring(red);
}
```

```css
/* CSS */
.message--STATUS, .message--WARNING, .message--ERROR {
  box-sizing: border-box;
  padding: 0.25em 0.5em;
  width: 80%;
  margin: 0 auto;
  border: 2px solid;
}

.message--STATUS {
  border-color: green;
  background: #3f9f3f;
  color: #006000;
}

.message--WARNING {
  border-color: yellow;
  background: #ffff3f;
  color: #bfbf00;
}

.message--ERROR {
  border-color: red;
  background: #ff3f3f;
  color: #bf0000;
}
```

While this approach certainly requires more work up front to build the mixins and extendables, it produces much more controlled and succinct output CSS, which is what we're aiming to write. 

#### Partial Structure

Sass partials are a way for us to organize our styling knowledge into maintainable and easily grokable chunks. An example Sass partial structure is available in the folder `sass`.

At the root of our Sass folder is our `style.scss` file, which holds the core of our styling, and a `no-script.scss` file to provide a CSS fallback if scripting isn't available. In the `sass` folder, create an `enhancements` folder a `fallbacks` folder, and a `partials` folder for your stylesheets that provide enhanced styling for powerful browsers, fallback styling less powerful browsers, and partials for all to draw from, each respectively.

Each feature you're enhancing with or providing a fallback for should be named `feature.scss` and be placed into their respective folder; for instance if you were to provide enhancements and fallback for CSS Animations, you would have a folder structure that looked something like `sass/enhancements/css-animations.scss` and `sass/fallbacks/css-animations.scss`.

The `partials` directory should be divided up into 3 sub directories, `global`, `components`, and `layouts`. Inside of `global`, you should have a  folder a piece for `variables`, `functions`, `mixins`, and `extendables`, with partials to match. Inside each of those folders should go partials whose content should be made available globally and aren't component specific. For instance, global color and typographic variables, background/text color contrast mixins, ligature extendables, etc… 

Both your components and your layouts should be built using a similar partial structure, henceforth known as the component partial structure. Each component should have a partial and matching folder, and inside that folder a partial a piece for `variables`, `functions`, `mixins`, and `extendables`. Each of these partials should hold styling knowledge specific to that component; for instance, `variables` could have color variables specific to that component, but the color it is set to should come from the global color partial. An example of this can be seen in in the example `sass` folder.

All extendable classes should be wrapped in a solution to only have the selector written once to ensure that selectors don't get needlessly duplicated. Mixins should share their naming convention with the object they are used to style. The solution provided by the North Compass extension is derived from Wilson Page's [Sass Import Once](https://github.com/wilsonpage/sass-import-once) partial.

## Interaction

What is better than a funny hat? A funny hat that spins. JavaScript adds interactivity to web pages, transforming them from static documents into living ones. JavaScript is a very flexible and powerful tool, but as Stan Lee says, "with great power there must also come -- great responsibility".

### Style and Syntax

A most reasonable approach to JavaScript is the [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript). It provides an excellent set of rules and industry best practices for writing JavaScript, and it should be followed. In addition to the Airbnb guide, the following guidelines should also be followed:

* Functions must be declared before they are used
* All custom scripts should be wrapped in anonymous, self-executing functions with any external dependencies passed in.

```javascript
(function($) {
  var intro = 'Once upon a time…',
      $heading = $('#heading'),
      $princess = $('#princess');
  
  function fairytale()
  
  heading.html(intro);
})(jQuery);

```

### Libraries, Plugins, and Frameworks

When building site, very often a point will come when a decision must be made as to if a certain JavaScript library, plugin, or framework should be used. In addition to evaluating 3rd party scripts based on the quality of their code and their adherence to the JavaScript Style Guide, the following questions should be considered:

* Is the added functionality worth the weight? A lot can be accomplished with very little in JavaScript. If a minified version of a script is larger than 5KB, seriously consider if everything that it offers is needed or if something smaller and lighter weight can be just as effective. Is a 21.5KB slider library plus the weight of jQuery really work the precious few bytes and HTTP requests needed for a fast and performant site?
* If the script builds off of another framework, such as a jQuery Plugin, examine the problem and determine if writing a custom solution can be as effective and lighter. Not everything needs to be a jQuery Plugin.
* If a script does not come with a minified version, determine if it can be minified. All scripts should be minified, so if a script being evaluated cannot, that should be taken into consideration.
* Is the script performant? Does it have performance benchmarks? If not, can it be benchmarked? If a script, regardless of weight, slows down a site significantly its use should be reconsidered.
* Given browser support, is a heavy JavaScript library like jQuery or Dojo needed? Can paired down versions of those libraries be used? Does usage require the full support behind one of these libraries, or can a small DOM/AJAX library such as [Chibi](https://github.com/kylebarrow/chibi) be effective?
