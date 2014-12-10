---
layout: default
title: "Showcases"
description: ""
class: case-study
---
{% comment %}
NOTE: the spotlight header required a modifier to render properly
      If the image in the spotlight-header div is a portrait image
      make sure to add 'spotlight-header--portrait'.
      If the image is landscape, make sure you add 'spotlight-header--landscape'
{% endcomment %}

<header class="spotlight-header spotlight-header--portrait clear">
  <div class="spotlight-header__container container">
    <div class="spotlight-header__copy g--half">
      <div class="spotlight-explainer" style="margin-top: 52px;">
        Every month, we talk with the engineering team behind a successful mobile web offering to share with you what worked, what didn't and how you can follow their footsteps.
      </div> 
      <div class="divider divider--fluid">
        <span class="divider-icon divider-icon--secondary"></span>
      </div>
      <h2 class="huge">
        <strong class="subsection-number">Featured case study</strong>
        Yelp
      </h2>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quaerat, error cupiditate.</p>
      <a href="./example-showcase" class="spotlight-header__cta cta--primary">Read the case study</a>
    </div>
    <div class="spotlight-header__media g--half g--last">
      <img src="../../imgs/placeholder--device-portrait.png" class="spotlight-header__image">
    </div>
  </div>
</header>

<div class="latest-spotlights">
  <div class="container clear">
    <h2>Also noteworthy</h2>

    <ul class="latest-spotlights__list list-reset">
      <li class="latest-spotlights__item">
        <a href="./example-showcase" class="latest-spotlights__link">
          <img src="../../imgs/image-portrait.jpg" alt="image example">
          <p class="small">Spotlight name</p>
        </a>
      </li>
      <li class="latest-spotlights__item">
        <a href="./example-showcase" class="latest-spotlights__link">
          <img src="../../imgs/image-portrait.jpg" alt="image example">
          <p class="small">Spotlight name</p>
        </a>
      </li>
      <li class="latest-spotlights__item">
        <a href="./example-showcase" class="latest-spotlights__link">
          <img src="../../imgs/image-portrait.jpg" alt="image example">
          <p class="small">Spotlight name</p>
        </a>
      </li>
      <li class="latest-spotlights__item">
        <a href="./example-showcase" class="latest-spotlights__link">
          <img src="../../imgs/image-portrait.jpg" alt="image example">
          <p class="small">Spotlight name</p>
        </a>
      </li>
      <li class="latest-spotlights__item">
        <a href="./example-showcase" class="latest-spotlights__link">
          <img src="../../imgs/image-portrait.jpg" alt="image example">
          <p class="small">Spotlight name</p>
        </a>
      </li>
    </ul>
  </div>
</div>

<div class="featured-section">
  <div class="container-medium">
    <ul class="featured-list">
      <li class="featured-list__item clear">
        <div class="container-small">
          <div class="featured-list__content g--half">
            <h3>Case study</h3>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium, incidunt harum aut quae eaque sequi sunt molestiae tenetur vitae.</p>
            <a href="#" class="cta--primary">View Google</a>
          </div>
          <figure class="featured-list__img-wrapper g--half g--last">
            <img src="../../../imgs/placeholder--medium.png" alt="image example">
          </figure>
        </div>
      </li>
      <div class="divider divider--fluid divider--spaced">
        <span class="divider-icon divider-icon--secondary"></span>
      </div>
      <li class="featured-list__item clear">
        <div class="container-small">
          <div class="featured-list__content g--half">
            <h3>Case study</h3>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium, incidunt harum aut quae eaque sequi sunt molestiae tenetur vitae.</p>
            <a href="#" class="cta--primary">View Google</a>
          </div>
          <figure class="featured-list__img-wrapper g--half g--last">
            <img src="../../../imgs/placeholder--medium.png" alt="image example">
          </figure>
        </div>
      </li>
    </ul>
  </div>
</div>

{% include modules/related_guides.liquid list=page.related-guides.create-amazing-forms minimal=true %}
