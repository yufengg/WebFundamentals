---
layout: article
title: "Tiny Tweaks (Крошечные изменения)"
description: "Приемы отзывчивого веб-дизайна быстро эволюционируют, но есть
              много проверенных вариантов, которые хорошо работают при использовании как
              настольных компьютеров, так и мобильных устройств"
introduction: "Шаблон Tiny Tweaks (Крошечные изменения) просто вносит небольшие изменения в макет, например, регулирует размер
  шрифта, меняет размер изображений или перемещает контент.  "
authors:
  - petelepage
article:
  written_on: 2014-04-30
  updated_on: 2014-10-21
  order: 4
priority: 1
collection: rwd-patterns
---

{% wrap content%}

Он хорошо работает на таких макетах, состоящих из одного столбца, как одностраничные линейные веб-сайты и статьи
с большим количеством текста.

{% link_sample _code/tiny-tweaks.html %}
  <img src="imgs/tiny-tweaks.svg">
  Попробовать
{% endlink_sample %}

Как можно понять из названия шаблона, при изменении размера экрана в этот образец вносятся незначительные модификации.
По мере увеличения ширины экрана, больше становятся размер шрифта и поля вокруг текста.

Сайты, созданные с использованием этого шаблона:

 * [Opera's Shiny Demos](http://shinydemos.com/)
 * [Ginger Whale](http://gingerwhale.com/)
 * [Future Friendly](http://futurefriendlyweb.com/)

{% include_code _code/tiny-tweaks.html ttweaks css %}

{% include modules/nextarticle.liquid %}

{% endwrap %}
