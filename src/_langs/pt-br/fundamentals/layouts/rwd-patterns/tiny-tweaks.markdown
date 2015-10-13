---
layout: article
title: "Tiny tweaks"
description: "Os padrões de design da Web responsivos estão evoluindo rapidamente, mas
              há muitos padrões estabelecidos que funcionam bem em
              dispositivos móveis e desktop"
introduction: "Pequenos ajustes simples fazem pequenas mudanças no layout, como ajustar o tamanho da
  fonte, redimensionar imagens ou mover conteúdo em espaços bem pequenos.  "
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

Funciona bem em layouts de coluna única como sites de uma página linear, artigos
de texto pesado.

{% link_sample _code/tiny-tweaks.html %}
  <img src="imgs/tiny-tweaks.svg">
  Tente
{% endlink_sample %}

Como o nome já diz, pequenas mudanças nesta amostra pois o tamanho da tela muda.
Conforme a largura da tela fica maior, também aumenta o tamanho da fonte e o preenchimento.

Estes são alguns dos sites que usam esse padrão:

 * [Opera's Shiny Demos](http://shinydemos.com/)
 * [Ginger Whale](http://gingerwhale.com/)
 * [Future Friendly](http://futurefriendlyweb.com/)

{% include_code _code/tiny-tweaks.html ttweaks css %}

{% include modules/nextarticle.liquid %}

{% endwrap %}
