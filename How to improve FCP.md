# FIRST CONTENTFUl PAINT
Measures the time from when the page starts loading to when any part of page's content is first rendered on screen

Explore web vitals library, what it is ? 
How it can be used?

How to measure FCP in Javascript
1. We can use Paint Timing API. But instead of it , we can use web-vitals

`
import { onFCP} from 'web-vitals'
onFCP(console.log)
`


# How to improve FCP
1. Eliminate render blocking resources
   1. Script tag in head
   2. Does not have defer
   3. Does not have async
   4. link tag with no disabled attribute
   5. Does not have media attribute

    ### How to identify critical resources
      1. Use coverage tab in chrome dev tools to identify non critical CSS and JS
      2. Reduce size of pages by shipping code and styles that you need

    ### How to eliminate render blocking scripts
          1. Once critical code is identified , move that piece of code to inline 
          2. For not critical , use script tags and mark url with async or defer

    ### How to eliminate render blocking stylesheets
        1. similar to JS , inline critical styles required for first paint inside a style tag in head of HTML page
        2. Then load rest of styles asynchronously using preload link(See Defer unused CSS)
        3. Split up files into multiple files, organised by media query
        4. Minify CSS
2. Minify CSS
3. Remove unused CSS
   1. By default , browser must download , parse and process all external stylesheets that it encounters before it can display any content to user's screen
   2. Unused CSS , slows down browser's construction of render tree.
   3. The more unused css, more time that a browser might potentially need to spend calculating styles for each node
   4. Inline critical css, preload other css
4. Remove unused JS
5. Preconnect to required origins
6. Reduce server response times (TTFB)
7. Avoid multiple page redirects
8. Preload key requests
9.  Avoid enormous network payloads
10. Serve static assets with an efficient cache policy
11. Aboid an excessive DOM size
12. Minimize critical request depth
13. Ensure text remains during webfont load
14. Keep request counts low and transfer sizes low
