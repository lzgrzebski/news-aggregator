# My solution for final project on [Browser Rendering Optimization](https://www.udacity.com/course/browser-rendering-optimization--ud860) course by Udacity

**Problems**

* Layout Thrashing
* Expensive painting
* Unnecessary layouts
* Long-running and badly-timed JavaScript
* Bad touch handling

**Fixes**
* By debugging performance I saw that on scroll we are using calling *colorizeAndScaleStories* method which was causing forced sync layout
* Some of the code was elements was moved to separate composite layer since checking page flashing we had many "green" spots
* I removed code for js animation to show the stories and I simply used a css transitions and translate which seems to be the most performant + I moved it to separate composite layer
* I replace setTimeout with requestAnimationFrame
* Simply override instead of adding new story details component so the DOM is not growing each time we are loading new story.

https://github.com/lzgrzebski/news-aggregator/commit/0205d14412f455296996711a33369d9be139ec28


All the bugs found by Udacity team:
https://classroom.udacity.com/courses/ud860/lessons/4129068601/concepts/41357988410923

