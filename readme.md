# Video players

Hi, my name is Martin and I'm a software engineer at Accedo.
This is a summary of video playback and players.

- Video & streaming related file types
- HTML5 video element
- Players: dash.js, ExoPlayer, AVPlayer, etc...

## Video & streaming related file types

There are a lot of different file types when it comes to media container formats: the most famous ones are .mp4, .avi, .mov, .ogg.
When it comes to streaming though, you'll see there is another group of file types that describes the stream: .mpd, .m3u8, .ismc.
You'll get to know these better later, I just wanted to spare a few words on them because we'll work with these later in this presentation.

## HTML5 Video

I know HTML is not a programming language, but as I mentioned: this session is not about programming, it's about video players.
So HTML is a markup language that was originally designed for CERN researchers to share documents in the 80s. It allows the usage of links (or hyperlinks).
Later in the 90s it made it to the internet and other technologies started to rise to support it: CSS to specify appearance & JavaScript to specify behavior.

Jump to the 2010s, HTML5 became the standard for describing webpages. It's goal was to improve the language with the support of the latest multimedia.
HTML5 allows you to embed a media player in your document. There are two HTML elements to serve this purpose: video, audio

### Attributes

There are several attributes to control the player itself. I'm showing you only some of them:

- autoplay: true/false  - you can control whether the player should start the playback automatically or not
- controls: true/false  - if it's truthy, it shows the default player controls of the browser
- height: number        - height of the video element in pixels
- width: number         - width of the video element in pixels
- loop: true/false      - if you want to play the video on loop
- poster: string (URL)  - the URL of the image to be shown while the video is loading

### Events

There are events dispatched on various playback events. You can subscribe to these events in JS. Some of these events:

- play: playback has begun
- pause: playback has been paused
- ended: playback stopped because it reached the end of the media
- canplay: playback can be started, but media is not completely buffered
- seeking: seek operation started
- seeked: seek operation completed

### Examples

#### Simple video

Simple HTML5 video element with a single source:

- Poster image sample: <https://peach.blender.org/wp-content/uploads/title_anouncement.jpg?x11217>
- MP4 sample: <https://archive.org/download/BigBuckBunny_124/Content/big_buck_bunny_720p_surround.mp4>

#### Multiple sources

Allows the video to be watched regardless of which codecs are supported by the browser.
Add multiple sources to support various browsers.

- Poster image sample: <https://upload.wikimedia.org/wikipedia/commons/e/e8/Elephants_Dream_s5_both.jpg>
- OGG sample (type=video/ogg): <https://archive.org/download/ElephantsDream/ed_hd.ogv>
- AVI sample (type=video/avi): <https://archive.org/download/ElephantsDream/ed_hd.avi>
- MP4 sample (type=video/mp4): <https://archive.org/download/ElephantsDream/ed_1024_512kb.mp4>

#### MPEG DASH Streaming

Instead of specifying a static video source, the .mpd format allows you to load a stream instead.
You'll learn more about MPD and streaming, for now I just want to show you, when it comes to streaming,
the HTML5 video element is not enough. The playback must be handled with JS in order to make it work.

Web browsers do not natively support the dash format.

- MPD sample (type=video/dash+xml): <https://dash.akamaized.net/akamai/bbb_30fps/bbb_30fps.mpd>

### Sources

### Sources

- <https://stackoverflow.com/questions/28529383/why-do-i-need-dash-js-for-streaming-mpeg-dash-videos>
- <https://shaka-player-demo.appspot.com/docs/api/tutorial-basic-usage.html>
- <https://en.wikipedia.org/wiki/HTML5>
- <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video>
- <https://reference.dashif.org/dash.js/latest/samples/getting-started/manual-load-single-video.html>
