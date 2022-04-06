The main objective of refactoring this codebase is to improve acccessibility for end users with disabilities and also optimise Search Engine Optimization (SEO) of the application as requested by the client. In order to tackle the project as a whole, will have to break down into 2 parts, firstly I will focus on the HTML then the CSS.

Part 1: HTML CHANGES

I decided to change the HTML structure with HTML5 semantic elements such as <header>, <main>, <section>, <nav>, <aside> and <footer>. This will not only provide much more meaningful structure but also will help improve SEO and allow the webpage to become more relevant during web searches. The reason for this change is the whole web page is constructed entirely with div tags which doesn't give much information or purpose with regards to the HTMl structure semantics-wise. Here are the detailed changes outlined below:

~~HTML CHANGES~~

> Located at the top of the webpage, The main div wrapper with class "header" was changed with header element. Also nested div tag containing unordered list of navigation links changed with nav element instead.

> For the main content of the webpage located in the center left of application just below the hero image, I have decided to use the HTML main element instead of using the div. The 3 div tags nested inside this div wrapper each containing h2 and p tags, I changed with the HTML section element instead.

> For the div wrapper with class "benefits" on the right side of the webpage, I decided to change it with the aside element. Since the 3 div tags nested inside have headings, images and related information, I decided to use section element instead of a div as we're not just styling and would provide for more meaning semantically.

> Located at bottom of webpage, I changed the div with class "footer" to using the footer element instead. Also changed heading element to h4 in order for heading elements to fall in sequential order and to avoid anti-pattern. The previous codebase already changed font-size for this element with class footer.

> I changed the content of the title element with "Horiseon | Social Solution Services Inc" as supposed to having just "website" as the title in the tab is very generic and won't help with improving SEO and the search engine won't understand or how to rank your webpage. This also helps the end users understand what the webpage is.

> I changed class attribute name "seo" to "seo-title". This will make it more meaningful and specific.

> For the hero image thats inserted through css into div of class "hero" (main image digital-marketing-image.jpg of images subfolder) changed class attribute name from "hero" to "hero-image" to make it more meaningful and specific.

> The first section of the main element with class "search-engine-optimization" was missing id attribute, causing link in nav bar to not work. fixed by inserting id="search-engine-optimization" into first section opening tag.

> I have inserted alt attributes for every single image in each of the sections of the main and aside element. This includes accompanying concise descriptions to describe the image. This will help improve accessibility especially those who are visually impaired and rely on a screen reader.
