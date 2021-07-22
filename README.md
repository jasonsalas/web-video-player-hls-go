# Web video player using HLS.js & Go 

## Forked from the original repo by [bosor](https://github.com/borosr/), [who forked](https://github.com/borosr/hls-usage) a rad tutorial by [Rohit Mundra](https://www.rohitmundra.com/video-streaming-server). The original concept demonstrates how to build a browser-based streaming video player using [HTTP Live Streaming](https://en.wikipedia.org/wiki/HTTP_Live_Streaming), using a Go-based web server on the back-end and a web client using the [HLS.js](https://github.com/video-dev/hls.js/) library.

***
#### This is a simple evolution of [my previous repo](https://github.com/jasonsalas/go-streaming-media-server) that deals with managing encoding media files and then serving them over HLS. This repo handles video content and uses a web front-end instead of a third-party to test the output.

Technologies used:
- [HTML5 video](https://web.dev/media/)
- [Go](https://golang.org) & the [Chi](github.com/go-chi/chi) router
- [ffmpeg](https://www.ffmpeg.org/)
- [HTTP Live Streaming](https://developer.apple.com/documentation/http_live_streaming)
- [HLS.js](https://github.com/video-dev/hls.js/)
***
TODOs:
- Adaptive streaming - automatically adjust playback quality levels based on network fidelity
- Support livestreams - this one's _slightly_ more involved...
- Package everything into a Docker image
