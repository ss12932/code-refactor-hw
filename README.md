# Horiseon Codebase Refactor

## Overview

![Horiseon Application Screenshot](./assets/images/01-html-css-git-homework-demo.png)

The main objective of refactoring this codebase is to improve acccessibility for end users with disabilities and also to optimise Search Engine Optimization (SEO) of the application as outlined in the user story set by the client:

```
AS A marketing agency
I WANT a codebase that follows accessibility standards
SO THAT our own site is optimized for search engines
```

In order to tackle the project as a whole, I will first focus on the HTML followed by the CSS.

## Part 1: HTML Changes

I decided to change the HTML structure with HTML5 semantic elements such as `<header>`, `<main>`, `<section>`, `<nav>`, `<aside>` and `<footer>`. This will not only provide much more meaningful structure but also will help improve SEO and allow the webpage to become more relevant during web searches. The reason for this change is the whole web page is constructed entirely with `<div>` tags which doesn't give much information or purpose with regards to the HTMl structure semantics-wise. Here are the detailed changes outlined below:

- Located at the top of the webpage, The main `<div>` wrapper with class `header` was changed with `<header>` element. Also nested `<div>` tag containing `<ul>` of navigation links changed with `<nav>` element instead.

- For the main content of the webpage located in the center left of application just below the hero image, I have decided to use the HTML `<main>` element instead of using the `<div>`. The 3 `<div>` tags nested inside this main`<div>` wrapper each containing `<h2>` and `<p>` tags, I changed with the HTML `<section>` element instead.

- For the `<div>` wrapper with class `benefits` on the right side panel of the webpage, I decided to change it with the `<aside>` element. Since the 3 `<div>` tags nested inside have headings, images and related information, I decided to use `<section>` elements for each of them instead of a `<div>`.

- Located at bottom of webpage, I changed the `<div>` with class `footer` to using the `<footer>` element instead. Also changed heading element to `<h4>` in order for heading elements to fall in sequential order and to avoid anti-pattern. The previous codebase already changed font-size for this element with class "footer".

- I changed the content of the `title` element with `Horiseon | Social Solution Services Inc` as supposed to having just `website` as the title in the tab is very generic and won't help with improving SEO and the search engine won't understand or how to rank your webpage. This also helps the end users understand what the webpage is.

- I changed class attribute name `"seo"` to `seo-title`. This will make it more meaningful and specific.

- For the hero image thats inserted through css into `<div>` of class `hero` (main image digital-marketing-image.jpg of images subfolder) changed class attribute name from `"hero"` to `"hero-image"` to make it more meaningful and specific.

- The first `<section>` of the `<main>` element with class `search-engine-optimization` was missing id attribute, causing link in nav bar to not work. fixed by inserting `id="search-engine-optimization"` into first `<section>` opening tag.

- I have inserted `alt` attributes for every single image in each of the sections of the `<main>` and `<aside>` element. This includes accompanying concise descriptions to describe the image. This will help improve accessibility especially those who are visually impaired and rely on a screen reader.

## Part 2: CSS Changes

- The CSS for the `<nav>` in the `<header>` element containing the navigation links with selectors such as `.header div` and `.header div ul` and `.header div ul li` stopped working because of changing HTML structure in Part 1 by replacing `<div>` with `<nav>`. I changed the div in the selectors to nav instead.

- Changed selector `.header h1 .seo` to `.header h1 .seo-title` to reflect name change of class attribute from `.seo` to `.seo-title` as previous CSS stopped working.

- Removed the CSS for `p { font-size: 16px; }` as default font size for p is already 16 pixels. No need to specify in stylesheet, just extra dead code.

- Changed selector of `.hero` to `.hero-image` of hero banner to reflect change in naming selector to being more specific.

- Used grouping selector to group together the CSS selectors used for the `<aside>` bar like `.benefit-lead`, `.benefit-brand`, `.benefit-cost` as they all share the same styling. clear codebase of extra clutter. likewise for `.benefit-lead h3`, `.benefit-brand h3`, `.benefit-cost h3` and `.benefit-lead img`, `.benefit-brand img`, `.benefit-cost img` I grouped together these selectors that share the same similar styling.

- Used grouping selector to group together the selectors used for `<main>` sections for `.search-engine-optimization`, `.online-reputation-management`, `.social-media-marketing` also `.search-engine-optimization img`, `.online-reputation-management img`, `.social-media-marketing img` and `.search-engine-optimization h2`, `.online-reputation-management h2`, `.social-media-marketing h2` since the 3 groups of selectors share the same CSS styling, in order to remove further unnecesary code.

- Changed Selector in footer `.footer h2` to `.footer h4` to reflect change of Heading element so they fall in sequential order.

- Header nav selector `.header nav ul li` overly specific, with specificity of (0,0,1,3) it will make it very difficult in the future to overide this style. Decided to use a class selector called `nav-menu` for `<nav>` and changed selector to `.nav-menu li` reducing specificity to (0,0,1,1). also for selector '.header nav ul`, I changed to `.nav-menu ul` reducing specificity and keeping it low - easier for maintainablity and overide styles later on.

- Header selector `.header h1 .seo-title` again is over specific with 2 class selectors and a type selector. Would make it difficult to override style in the future. changed to just '.seo-title' as this class selector is directly targeting the `<span>` element for which we are applying the style to.

- I added comments in my CSS to help divide different sections of my CSS in a logical order like viewing the HTML document from top to bottom starting from `<header>` going down to the `<footer>`so the client and future developers maintaining the application can easily navigate through the CSS as I included Contents Table with numbered sections, they can easily navigate using the find function.
