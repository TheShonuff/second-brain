---
title: PipeWire
Created: 2023-09-27 19:27
tags:
  - linux
aliases:
---
# PipeWire
- Aims to offer capture and playback for both audio and video with minimal latency.
- Support for PulseAudio, JACK, ALSA, GStreamer

## Session Manager
- implements no logic internally
- Burden of watching for new streams and connect them to the apprioriate out device or application is left to an external component called a **session manager**
- Current recommendation is [[WirePlumber]]

## Configuration
- `~/.config/pipewire`

