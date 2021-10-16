---
title: "Fix Audio Distortion on Internal Mic on Linux"
date: 2021-10-16T15:41:46+03:00
draft: false
---
_I am writing this article since I had this issue on pretty much every linux installation_
_This will only work if you're using pulseaudio for sound on Linux_

The general advice I found was editing every `analog-input*.conf` file in `/usr/share/pulseaudio/alsa-mixer/paths/`, however only changing `analog-input-internal-mic.conf` worked for me, since I only experienced the issue with the internal mic.

In the `analog-input-internal-mic.conf` change:
- Under [Element Capture] set `volume` to `zero`
- Under [Element Internal Mic Boost] set `volume` to `zero`.
- Under [Element Int Mic Boost] set `volume` to `zero`.
- Under [Element Mic Boost] set `volume` to `zero`.

Restart pulseaudio by calling:
```
systemctl --user restart pulseaudio
```

Source: https://wiki.archlinux.org/title/PulseAudio/Troubleshooting#Microphone_distorted_due_to_automatic_adjustment:%7E:text=Under%20%5BElement%20Internal%20Mic%20Boost%5D%20set,Mic%20Boost%5D%20set%20volume%20to%20zero

Enjoy your clean Linux microphone experience :)
