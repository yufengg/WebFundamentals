---
rss: false
layout: update
published: true
title: Project wide search with optional file scope
date: 2015-07-09
article:
  written_on: 2015-07-09
  updated_on: 2015-07-09
authors:
- umarhansa
collection: updates
type: tip
category: tools
product: chrome-devtools
description: Learn the secret commands to search like a pro in DevTools.
featured-image: /web/updates/images/2015-07-09-a-project-wide-search-with-an-optional-file-scope/project-search-with-file-scope.gif
source_name: DevTips
source_url: https://umaar.com/dev-tips/56-project-search-with-file-scope
permalink: /updates/2015/07/09/project-wide-search-with-optional-file-scope.html
---
<img src="/web/updates/images/2015-07-09-a-project-wide-search-with-an-optional-file-scope/project-search-with-file-scope.gif" alt="A project wide search with an optional file scope">

Search across all sources with <kbd class="kbd">Cmd</kbd> + <kbd class="kbd">Opt</kbd> + <kbd class="kbd">F</kbd> / <kbd class="kbd">Ctrl</kbd> + <kbd class="kbd">Shift</kbd> + <kbd class="kbd">F</kbd>. If your query returns too many matching files, you can limit the search scope by changing the search query from:

<pre><code>query</code></pre>

To:

<pre><code>query file:main.js</code></pre>

Or:

<pre><code>query file:main</code></pre>