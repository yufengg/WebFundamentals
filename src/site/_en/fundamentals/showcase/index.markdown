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
      <h2 class="xlarge">
        <strong class="subsection-number">January case study</strong>
        Chrome Dev Summit
      </h2>
      <p>Built in-house by our own Paul Lewis, the CDS website showed how to build a great mobile web experience for conference visitors.</p>
      <a href="./example-showcase" class="spotlight-header__cta cta--primary">Read the case study</a>
    </div>
    <div class="spotlight-header__media g--half g--last">
      <img src="../../imgs/placeholder--device-portrait.png" class="spotlight-header__image">
    </div>
  </div>
</header>

<div class="latest-spotlights">
  <div class="container clear">
    <h2 class="large">Also noteworthy</h2>
    <p class="g--half">Sites and apps we love, regardless of their mainstream success. Always pushing the web forward.</p>

    <ul class="latest-spotlights__list list-reset">
      <li class="latest-spotlights__item">
        <a href="./example-showcase" class="latest-spotlights__link">
          <img src="../../imgs/image-portrait.jpg" alt="image example">
          <p class="small">Spotlight</p>
        </a>
        <div class="latest-spotlights__description">
          <h3>Spotlight name</h3>
          <p>Small splotlight descrition noting why this spotlight is such a great app.</p>
          <a href="#" class="cta--primary">View Spotlight</a>
        </div>
      </li>
      <li class="latest-spotlights__item">
        <a href="./example-showcase" class="latest-spotlights__link">
          <img src="../../imgs/image-portrait.jpg" alt="image example">
          <p class="small">Spotlight</p>
        </a>
        <div class="latest-spotlights__description">
          <h3>Spotlight name</h3>
          <p>Small splotlight descrition noting why this spotlight is such a great app.</p>
          <a href="#" class="cta--primary">View Spotlight</a>
        </div>
      </li>
    </ul>
  </div>
</div>

<div class="featured-section">
  <div class="container-medium">

  <h2>Previously</h2>

    <ul>

      <li class="featured-list__item clear">
        <div class="container-small">
          <div class="featured-list__content g--half">
            <h3 class="xlarge">
              <strong class="subsection-number">December case study</strong>
              Yelp
            </h3>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium, incidunt harum aut quae eaque sequi sunt molestiae tenetur vitae.</p>
            <a href="#" class="cta--primary">Read the case study</a>
          </div>
          <figure class="featured-list__img-wrapper g--half g--last">
            <img src="../../../imgs/placeholder--medium.png" alt="image example">
          </figure>
        </div>
      </li>

      <div class="divider divider--fluid divider--spaced">
        <span class="divider-icon divider-icon--secondary"></span>
      </div>

      <div class="spotlights clear">
        <li class="featured-list__item clear g--half">
          <div class="container-small">
            <div class="featured-list__content g--half">
              <h3 class="xlarge">
                <strong class="subsection-number">Spotlight</strong>
                Some Spotlight
              </h3>
              <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
              <a href="#" class="cta--primary">View Spotlight</a>
            </div>
            <figure class="featured-list__img-wrapper g--half g--last">
              <img src="../../imgs/image-portrait.jpg" alt="image example">
            </figure>
          </div>
        </li>

        <li class="featured-list__item clear g--half g--last">
          <div class="container-small">
            <div class="featured-list__content g--half">
              <h3 class="xlarge">
                <strong class="subsection-number">Spotlight</strong>
                Some Spotlight
              </h3>
              <p>Accusantium, incidunt harum aut quae eaque sequi sunt molestiae tenetur vitae.</p>
              <a href="#" class="cta--primary">View Spotlight</a>
            </div>
            <figure class="featured-list__img-wrapper g--half g--last">
              <img src="../../imgs/image-portrait.jpg" alt="image example">
            </figure>
          </div>
        </li>
      </div>

      <div class="divider divider--fluid divider--spaced">
        <span class="divider-icon divider-icon--secondary"></span>
      </div>

      <li class="featured-list__item clear">
        <div class="container-small">
          <div class="featured-list__content g--half">
            <h3 class="xlarge">
              <strong class="subsection-number">October case study</strong>
              Winning Site
            </h3>
            <p>This page is just a pure winner. It wins in so many ways. Let's have a look it its continuous winning.</p>
            <a href="#" class="cta--primary">Read the case study</a>
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
