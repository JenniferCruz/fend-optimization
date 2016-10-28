# Website Performance Optimization portfolio project
This project was completed for the Website Optimization Course in the Udacity Fron End Development Nanodegree program. 

## Getting started
- To see the application go to [https://jennifercruz.github.io/fend-pageSpeed/](https://jennifercruz.github.io/fend-pageSpeed) or to [this Github repository](https://github.com/JenniferCruz/fend-pageSpeed).
- To run The PageSpeed tool for index.html [click here](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Fjennifercruz.github.io%2Ffend-pageSpeed%2F).
- To run the PageSpeed Insights for pizza.html [click here](***).

## Optimizations made
#### Optimized PageSpeed Insights score for _index.html_
The changes listed below allowed to get a PageSpeed Insights score of __95 for Mobile__ and __94 for Desktop__. 
* Hosted images were resized and compressed
* All JavaScript files were externalized and made async (However, I am worried about how this could impact analytics in a "real live" project).
* All styles were inlined in the index.html file's header.
* The linked web font was removed and substituted for a web safe font. 

##### A note on minification
I considered minifying all text files. However, I found out this had zero impact in the PageSpeed score, probably because the files are already very small by themselves. 

#### Optimize Frames per Second in pizza.html