# Website Performance Optimization portfolio project
This project was completed for the Website Optimization Course in the [Udacity Front-End Development Nanodegree program](https://www.udacity.com/course/front-end-web-developer-nanodegree--nd001).

## Getting started
- To see the application go to [https://jennifercruz.github.io/fend-optimization/](https://jennifercruz.github.io/fend-optimization) or download it from [this Github repository](https://github.com/JenniferCruz/fend-optimization).
- To run The PageSpeed tool for index.html [click here](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Fjennifercruz.github.io%2Ffend-pageSpeed%2F).
- To see loading time and fps for [views/pizza.html](https://jennifercruz.github.io/fend-optimization/views/pizza.html), use [Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/).

## Optimizations made
#### Optimized PageSpeed Insights score for _index.html_
The changes listed below allowed to get a PageSpeed Insights score of __95 for Mobile__ and __94 for Desktop__.
* Hosted images were resized, compressed and stripped off their meta information.
* All JavaScript files were externalized and made `async` (However, I am worried about how this could impact analytics in a "real live" project).
* All styles were inlined in the `index.html` file's header (but I don't believe this would be a good solution for bigger sites).
* The linked web font was removed and substituted for a web safe font.

##### A note on minification
I considered minifying all text files. However, I found out this had zero impact in the PageSpeed score, probably because the files are already very small by themselves.

#### Optimized Frames per Second in pizza.html
* In `pizza.html`, reduced the size of the big main image in more than half and added an additional image with `srcset` for smaller devices.
* In the `updatePositions()` function, took `document.body.scrollTop` access outside of loop, assigning it to a variable named `docBodyScrollTop`. This reduced significantly the forced reflow caused by this function.
* In the `DOMContentLoaded` event listener, reduced number of sliding pizzas from 200 to 50, which helped reduced the fps rate (I think this number can be reduced even further, but I wonder if it'd affect how the page display in larger devices).
* In the `for-loop` to add pizzas to menu, took call to `document.getElementById("randomPizzas")` out of the loop. Also, reduced number of pizzas to 50 (and is still too much! Very few people -if any- likes so huge menus!!!).
* In the `changePizzaSizes()` function (inside `resizePizzas()`), moved the following out of the loop: `offsetWidth` access,  `document.querySelectorAll(".randomPizzaContainer")`, call to `determineDx()` and `newWidth` declaration.
