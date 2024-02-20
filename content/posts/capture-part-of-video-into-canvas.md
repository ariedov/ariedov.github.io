---
title: "Capture Part of Video Into Canvas"
date: 2024-02-20T13:23:26+02:00
draft: true
---

The problem is to identify a face on the webcam feed (done by using one of many js CV library).

The camera not just captures the face, but also a lot of the background. In order to save bandwidth we should only send what is relevant (the face).

That's how to crop out a specific section of the video frame and get the image decoded into base64.

```js
function captureVideoSection(video, facebox) {
    const canvas = document.createElement("canvas");
    canvas.width = facebox.width;
    canvas.height = facebox.height;
    const canvasContext = canvas.getContext("2d");
    canvasContext.drawImage(
        video,
        facebox.x, facebox.y, facebox.width, facebox.height,
        0, 0, facebox.width, facebox.height
    );
    const imageBase64 = canvas.toDataURL('image/png');

// ... process image
}
```
