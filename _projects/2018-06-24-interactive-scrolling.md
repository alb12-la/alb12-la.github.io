---
title: 'Interactive Scrolling Demo'
date: 2018-06-30 00:00:00
description: A small snippet that shows one way to synchronize the a users scrolling with an illustration. 
featured_image: '/images/projects/interactive-scrolling.jpg'
---

A while back I created a webpage that when viewed on a desktop,  synchronized an illustration to a users scrolling. I thought it was neat and wanted to share it. 

I use plain ol vanilla JavaScript to create trigger points that are hit when a user scrolls down far enough. These trigger points adjust a y-axis transformation applied to the illustration on the left hand side. 

[Live Demo](https://alb12-la.github.io/interactive-scrolling/) `|` [Repository](https://github.com/alb12-la/interactive-scrolling)

<iframe src="https://player.vimeo.com/video/328356962?color=ff0179&title=0&byline=0&portrait=0" width="640" height="434" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


### How does it work?
In the video below I remove the mask used to hide the rest of the illustration, to give a better insight into how this works. 

I essentially create one long illustrated graphic and apply a mask over the rest of the illustration so that it only displays the section that I want. 

Next, I subscribe to the `onscroll` event to track the `pageYOffset` , from there I use trigger points that tell me where the user is then adjust the transformation of the illustration accordingly. 

<iframe src="https://player.vimeo.com/video/328360488?title=0&byline=0&portrait=0" width="640" height="435" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

The magic is really all in the [updateIllustrationOffset()](https://github.com/alb12-la/interactive-scrolling/blob/master/index.html#L56) function that is constantly checking the current scroll distance from the top of the window, and comparing that to preset trigger points. 
```javascript 
...
/* trigger_01 */
else if (trigger_01 <= distanceFromTop && distanceFromTop < trigger_02) {
    illustrationContainer.className = "positionA";
    illustration.setAttribute("style", "transform: translate(-50%,-12.7%);")
}
/* trigger_02 */
else if (trigger_02 <= distanceFromTop && distanceFromTop < trigger_03) {
    illustrationContainer.className = "positionB";
    illustration.setAttribute("style", "transform:translate(-50%,-37.7%)");
}
...
```

If you're looking to create something similar, feel free to use this example to get you started!