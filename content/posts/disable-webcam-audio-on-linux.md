---
title: "Disable Webcam Audio on Linux"
date: 2021-11-11T10:59:01+02:00
draft: false
---

Sometimes I play around with my sound devices, just because I have quite a few connected to my laptop. Sometimes it means I forget to switch them back to where they need to be.

This particularly works for my webcam audio, which is selected automatically when I change my output to hdmi audio.

To locate the desired audio device call `cat /proc/asound/modules`. My output looked like this:
```
 0 snd_hda_intel
 1 snd_hda_intel
 2 snd_usb_audio
```

Since I only have one usb audio device installed, and it is my webcam, I want to block `snd_usb_audio`. To do that open the `/etc/modprobe.d/blacklist.conf` and add the last line to it:
```
blocklist snd_usb_audio
```

After a restart voila - webcam has no sound more.

If you change your mind just remove the line and restart your machine. The sound should come back.

Enjoy!