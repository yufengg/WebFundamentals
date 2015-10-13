---
layout: article
title: "Stick to compositor-only properties and manage layer count"
description: "Compositing is where the painted parts of the page are put together for displaying on screen."
introduction: "Compositing is where the painted parts of the page are put together for displaying on screen."
article:
  written_on: 2015-03-20
  updated_on: 2015-03-20
  order: 6
collection: rendering-performance
priority: 0
authors:
  - paullewis
notes:
  flip:
    - "If you’re concerned that you may not be able to limit your animations to just those properties, take a look at the <a href=\"http://aerotwist.com/blog/flip-your-animations\">FLIP principle</a>, which may help you remap animations to changes in transforms and opacity from more expensive properties."

key-takeaways:
  - Stick to transform and opacity changes for your animations.
  - Promote moving elements with will-change or translateZ.
  - Avoid overusing promotion rules; layers require memory and management.

---
{% wrap content%}

{% include modules/takeaway.liquid list=page.key-takeaways %}

There are two key factors in this area that affect page performance: the number of compositor layers that need to be managed, and the properties that you use for animations.

## Use transform and opacity changes for animations
The best-performing version of the pixel pipeline avoids both layout and paint, and only requires compositing changes:

<img src="images/stick-to-compositor-only-properties-and-manage-layer-count/frame-no-layout-paint.jpg" class="g--centered" alt="The pixel pipeline with no layout or paint.">

In order to achieve this you will need to stick to changing properties that can be handled by the compositor alone. Today there are only two properties for which that is true: **transforms** and **opacity**:

<img src="images/stick-to-compositor-only-properties-and-manage-layer-count/safe-properties.jpg" class="g--centered" alt="The properties you can animate without triggering layout or paint.">

The caveat for the use of transforms and opacity is that the element on which you change these properties should be on _its own compositor layer_. In order to make a layer you must promote the element, which we will cover next.

{% include modules/remember.liquid title="Note" list=page.notes.flip %}

## Promote elements that you plan to animate

As we mentioned in the “[Simplify paint complexity and reduce paint areas](simplify-paint-complexity-and-reduce-paint-areas)” section, you should promote elements that you plan to animate (within reason, don’t overdo it!) to their own layer:

{% highlight css %}
.moving-element {
  will-change: transform;
}
{% endhighlight %}

Or, for older browsers, or those that don’t support will-change:

{% highlight css %}
.moving-element {
  transform: translateZ(0);
}
{% endhighlight %}

This gives the browser the forewarning that changes are incoming and, depending on what you plan to change, the browser can potentially make provisions, such as creating compositor layers.

## Manage layers and avoid layer explosions

It’s perhaps tempting, then, knowing that layers often help performance, to promote all the elements on your page with something like the following:

{% highlight css %}
* {
  will-change: transform;
  transform: translateZ(0);
}
{% endhighlight %}

Which is a roundabout way of saying that you’d like to promote every single element on the page. The problem here is that every layer you create requires memory and management, and that’s not free. In fact, on devices with limited memory the impact on performance can far outweigh any benefit of creating a layer. Every layer’s textures needs to be uploaded to the GPU, so there are further constraints in terms of bandwidth between CPU and GPU, and memory available for textures on the GPU.

In short, **do not promote elements unnecessarily**.

## Use Chrome DevTools to understand the layers in your app

To get an understanding of the layers in your application, and why an element has a layer you must enable the Paint profiler in Chrome DevTools’ Timeline:

<img src="images/stick-to-compositor-only-properties-and-manage-layer-count/paint-profiler.jpg" class="g--centered" alt="The toggle for the paint profiler in Chrome DevTools.">

With this switched on you should take a recording. When the recording has finished you will be able to click on individual frames, which is found between the frames-per-second bars and the details:

<img src="images/stick-to-compositor-only-properties-and-manage-layer-count/frame-of-interest.jpg" class="g--centered" alt="A frame the developer is interested in profiling.">

Clicking on this will provide you with a new option in the details: a layer tab.

<img src="images/stick-to-compositor-only-properties-and-manage-layer-count/layer-tab.jpg" class="g--centered" alt="The layer tab button in Chrome DevTools.">

This option will bring up a new view that allows you to pan, scan and zoom in on all the layers during that frame, along with reasons that each layer was created.

<img src="images/stick-to-compositor-only-properties-and-manage-layer-count/layer-view.jpg" class="g--centered" alt="The layer view in Chrome DevTools.">

Using this view you can track the number of layers you have. If you’re spending a lot time in compositing during performance-critical actions like scrolling or transitions (you should aim for around **4-5ms**), you can use the information here to see how many layers you have, why they were created, and from there manage layer counts in your app.

{% include modules/nextarticle.liquid %}

{% endwrap%}
