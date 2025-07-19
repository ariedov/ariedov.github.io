---
title: "Tmux as Docker"
date: 2025-03-08T21:29:03Z
draft: false
---

I highly recommend using a vps with a custom domain name and https configuration for testing ones backend. 127.0.0.1 is fine for start, and there is not a way of avoiding it, however, having an actual server is bound to uncover some obvious issues that were missed in development.

But there is an issue at hand: how to keep the backend code running after the ssh connection is lost? There are a few options.

### Docker

This one is the most obvious: containerize the code, run it in docker, expose a port and voila - you're all set. And while there are ways to keep the docker container up to date with all the code changes, it's not the most smooth experience.

### Daemon

A daemon is basically a worst docker: it is harder to track, harder to make sure the code is up to date and harder to kill.


### tmux

Yes. Tmux. The terminal multiplexer. It has an extremely useful feature of retaining active sessions, which means that the code that is running in tmux is going to keep running as long as the session is alive. Which means your `npm dev`, `manage.py runserver`, `go main.go` and `uvicorn --reload` are going to run.

I wasn't sure this crazy idea is viable, however I did try running a few services for a relatively long time and it just worked for testing some development builds across the team, with changes being applied immediately and being up when the team is ready to take a look. I'm yet to be dissapointed by this setup.

Cheers!
