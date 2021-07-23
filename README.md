# Web video player using HLS.js & Go 

## Forked from the original repo by [bosor](https://github.com/borosr/), [who forked](https://github.com/borosr/hls-usage) a rad tutorial by [Rohit Mundra](https://www.rohitmundra.com/video-streaming-server). The original concept demonstrates how to build a browser-based streaming video player using [HTTP Live Streaming](https://en.wikipedia.org/wiki/HTTP_Live_Streaming), using a Go-based web server on the back-end and a web client using the [HLS.js](https://github.com/video-dev/hls.js/) library.

***
#### This is a simple evolution of [my previous repo](https://github.com/jasonsalas/go-streaming-media-server) that deals with managing encoding media files and then serving them over HLS. This repo handles video content and uses a web front-end instead of a third-party to test the output.

**Technologies used:**
- [HTML5 video](https://web.dev/media/)
- [Go](https://golang.org) & the [Chi](github.com/go-chi/chi) router
- [ffmpeg](https://www.ffmpeg.org/)
- [HTTP Live Streaming](https://developer.apple.com/documentation/http_live_streaming)
- [HLS.js](https://github.com/video-dev/hls.js/)
***
### How to run this demo
- [See how](https://github.com/jasonsalas/web-video-player-hls-go/tree/main/assets/media/README.md) to encode MP4 files into HLS segments using ffmpeg. The segments will be served as streaming chunks to the web client instead of forcing the browser to load the entire file all at once before playback, and also keeping the source data from prying eyes.
- Start the web server using `go run main.go` or `go build -o server main.go` and then `./server` (or `./server.exe` if you're on Windows).
- Launch [http://localhost:8000/](http://localhost:8000/) in your browser (the video *should* auto-play).

**Now for added fun, launch Chrome's Developer Tools (`Ctrl+Shift+I`) and watch the streaming chunks progressively load in the Network tab as your video advances in 10-second segments. COOL!**

![HLS segments load progressively as your video advances](https://github.com/jasonsalas/web-video-player-hls-go/blob/main/static/streaming_traffic.jpg)

***
**Dockerize the web app**

Run the following command at a terminal to build the system as a Docker image
- Build the image: `docker build -t go-hls-streaming .`
- Run the image: `docker run --name go-hls-streaming -d -p 8000:8000 go-hls-streaming`
- Verify the server is running: `curl -i localhost:8000/media/1/stream/`
***
TODOs:
- Adaptive streaming - automatically adjust playback quality levels based on network fidelity
- Support livestreams - this one's _slightly_ more involved...
