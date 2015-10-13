---
layout: update
published: true
rss: true
collection: updates
category: chrome
product: chrome
type: news
date: 2015-09-17
title: "The EME Logger extension"
description: "EME Logger is a Chrome extension that logs Encrypted Media Extensions (EME) events and calls to the DevTools console."
article:
  written_on: 2015-09-17
  updated_on: 2015-09-17
authors:
  - samdutton
tags:
  - audio
  - video
  - media
  - EME
permalink: /updates/2015/09/eme-logger.html
featured-image: /web/updates/images/2015-09-17-eme-logger/featured.png
---
<style type="text/css" media="screen">
img, video {
  max-width: 100%;
}
</style>

Do you use Encrypted Media Extensions?

If so, you may be interested in EME Logger: a Chrome extension from Google that logs EME events and calls to the DevTools console along with debugging information.

You can install EME Logger from the Chrome Web Store [here](https://chrome.google.com/webstore/detail/eme-call-and-event-logger/cniohcjecdcdhgmlofniddfoeokbpbpb).

<p style="text-align: center;">
  <img src="/web/updates/images/2015-09-17-eme-logger/screenshot_page.png" alt="Screenshot of protected content playing in a video element on a web page, with the Chrome DevTools console showing logging from the EME Logger extension">
</p>

<p style="text-align: center;">
  <img src="/web/updates/images/2015-09-17-eme-logger/screenshot_console.png" alt="Screenshot of the Chrome DevTools console showing logging from the EME Logger extension">
</p>

The code for EME Logger is available at [github.com/google/eme_logger](http://github.com/google/eme_logger). Patches, bug reports and feature requests welcome.

More information about EME is available from the HTML5 Rocks article [EME WTF](http://www.html5rocks.com/en/tutorials/eme/basics/)?

As an alternative to 'roll your own' EME, we recommend Shaka Player: an easy-to-use JavaScript library developed by Google that enables adaptive delivery of protected (and unprotected) media. Shaka Player implements [Dynamic Adaptive Streaming over HTTP](http://www.streamingmedia.com/Articles/Editorial/What-Is-.../What-is-MPEG-DASH-79041.aspx) with [Media Source Extensions](http://www.html5rocks.com/en/tutorials/eme/basics/#related-technology-1) to deliver the best possible video performance at any bandwidth. Shaka also supports multilingual content for audio tracks and subtitles. Find out more about Shaka Player at [g.co/shakainfo](http://g.co/shakainfo).

