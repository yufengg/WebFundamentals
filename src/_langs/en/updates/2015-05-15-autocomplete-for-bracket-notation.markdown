---

layout: update
published: true
title: Autocomplete for bracket notation
date: 2015-05-15
article:
  written_on: 2015-05-15
  updated_on: 2015-05-20
authors:
- umarhansa
collection: updates
type: tip
category: tools
product: chrome-devtools
description: Did you know you can autocomplete bracket notation in the Sources panel?
featured-image: /web/updates/images/2015-05-20-console-panel-autocomplete-with-properties-bracket-or-dot-notation/console-autocomplete.gif
source_name: DevTips
source_url: https://umaar.com/dev-tips/30-console-autocomplete
permalink: /updates/2015/05/15/autocomplete-for-bracket-notation.html
---
<img src="/web/updates/images/2015-05-20-console-panel-autocomplete-with-properties-bracket-or-dot-notation/console-autocomplete.gif" alt="Console Panel autocomplete with properties (bracket or dot notation)">

Autocomplete in the Console Panel not only works with regular dot notation (e.g. <code>window.onload</code> → <code>window.onload</code>), but also with square bracket notation e.g. <code>window['onloa</code> → <code>window['onload']</code>.

Even if you have an array, you get autocomplete for the index e.g. <code>arr[0</code> → <code>arr[0]</code>.