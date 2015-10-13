---

layout: update
published: true

collection: updates
category: chrome
product: chrome
type: news
date: 2011-11-15

title: "&quot;Stream&quot; video using the MediaSource API"
description: ""
article:
  written_on: 2011-11-15
  updated_on: 2011-11-15
authors:
  - ericbidelman
permalink: /updates/2011/11/Stream-video-using-the-MediaSource-API.html
---
The [MediaSource API](http://html5-mediasource-api.googlecode.com/svn/trunk/draft-spec/mediasource-draft-spec.html) extends the `HTMLMediaElement` to allow JavaScript to generate media streams for playback. Allowing JavaScript to generate streams facilitates a variety of use cases like adaptive streaming and time shifting live streams.

Here is a quick [demo](http://html5-demos.appspot.com/static/media-source.html) and example usage of API:

{% highlight javascript %}
const NUM_CHUNKS = 5;

var video = document.querySelector('video');
video.src = video.webkitMediaSourceURL;

video.addEventListener('webkitsourceopen', function(e) {
  var chunkSize = Math.ceil(file.size / NUM_CHUNKS);

  // Slice the video into NUM_CHUNKS and append each to the media element.
  for (var i = 0; i < NUM_CHUNKS; ++i) {
    var startByte = chunkSize * i;

    // file is a video file.
    var chunk = file.slice(startByte, startByte + chunkSize);

    var reader = new FileReader();
    reader.onload = (function(idx) {
      return function(e) {
        video.webkitSourceAppend(new Uint8Array(e.target.result));
        logger.log('appending chunk:' + idx);
        if (idx == NUM_CHUNKS - 1) {
          video.webkitSourceEndOfStream(HTMLMediaElement.EOS_NO_ERROR);
        }
      };
    })(i);

    reader.readAsArrayBuffer(chunk);
  }
}, false);
{% endhighlight %}

[DEMO](http://html5-demos.appspot.com/static/media-source.html)

The example splits a .webm video into 5 chunks using the File APIs. The entire movie is then 'streamed' to a `<video>` tag by appending each chunk to the element using the MediaSource API.

If you're interested in learning more about the API, see the [specification](http://html5-mediasource-api.googlecode.com/svn/trunk/draft-spec/mediasource-draft-spec.html).

*Support:* Currently, the MediaSource API is only available in Chrome Dev Channel 17+ with the `--enable-media-source` flag set or enabled via `about:flags`.
