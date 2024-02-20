---
title: "Full Screen Video in Html"
date: 2024-02-20T09:42:49+02:00
draft: false
---

I had a task to capture peoples faces for AI biometric recognition for authentication purposes. The "hard" part supposed to be the face recognition (silly me). There are a bunch of libraries to do that for me, but the `video` html tag went out of control.

The tricky part was to make sure that the video is filling up the screen on desktop, but also on mobile.

When setting `width` and `height` to the `video` tag via `js` - the video looks weirdly out of place.

The answer lied in the `aspect-ratio` style. I have to set it to be `screenWidth / screenHeight` and voila - all looks much better.


```html
<!-- transform: rotate(180deg) so that the video looks like you're looking in the mirror -->
<video id="video" playsinline class="video" style="transform: rotateY(180deg); width: 100%; height: 100%; object-fit: cover;"> </video>
```

```js
const video = document.getElementById('video');

window.onload = () => {
    video.style.aspectRatio = `${window.innerWidth / window.innerHeight}`
}

window.onresize = () => {
    video.style.aspectRatio = `${window.innerWidth / window.innerHeight}`
}
```