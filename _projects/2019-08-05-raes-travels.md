---
title: Rae's Travels
date: 2018-06-30 00:00:00
description: This page is a demo that shows everything you can do inside portfolio and blog posts.
featured_image: '/images/projects/raes_travels/raes.png'
---

Rae's Travels is a personal project in which I created an Angular web app that combines the idea of a geotagged photo album, like [Flikr's Map](https://www.flickr.com/map) with a blog, allowing users to create a visualized scrap book of their adventures. 

This specific profile, is of [Terazha Pitts](https://www.instagram.com/tpittts/) from sunny California who is a perfect guinea pig for this project since she's loves the idea of being able to visualize her travels in one place. The entries we've listed here are only a small handful of the places she's been to. 

[Check out the live site!](http://raestravels.com/)

<div class="gallery" data-columns="2">
    <img src="/images/projects/raes_travels/spain-focus-1.png">
    <img src="/images/projects/raes_travels/spain-focus-2.png">
</div>

## Technology

The web app is built around the open source project [WebGL Earth](http://examples.webglearth.com/) which is in charge of rendering a JavaScript based, interactive 3D globe. I build on top of this by using [Angular](https://angular.io) to create a wrapper around WebGL Earth. This wrapper is in charge of mapping the interactions with the globe to specific adventure posts.

 These posts are stored as `Marker` objects which look like this: 
```javascript
export class Marker {
    constructor(
        public latitude: number,
        public longitude: number,
        public title: string,
        public icon: string,
        public associatedContent?: Content[],
        public description?: string,
        public date?: string,
        public featuredImage?: string,
        public iconHeight = 100,
        public iconWidth = 100,
    ) { }
}
```

When a marker is clicked, it's contents are handed to a `detail-view` component that is in charge of neatly rendering the contents. 


## Related projects
The angular wrapper used to build Rae's travels is itself very flexible. In [this](http://34.83.225.79/) iteration, I use [Mapquest's reverse geo-coding api](https://developer.mapquest.com/documentation/geocoding-api/reverse/get/) to live update the address that is sitting at the center of the cross-hairs

![images](/images/projects/raes_travels/gps2.png)






