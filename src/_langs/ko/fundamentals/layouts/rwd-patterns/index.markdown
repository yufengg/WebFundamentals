---
layout: section
title: "반응형 웹 디자인 패턴"
description: " 반응형 웹 디자인 패턴은 빠르게 진화하고 있지만,
              데스크톱 및 모바일 장치에서 잘 작동하는
              확립된 패턴은 소수입니다."
introduction: " 반응형 웹 디자인 패턴은 빠르게 진화하고 있지만,
              데스크톱 및 모바일 장치에서 잘 작동하는
              확립된 패턴은 소수입니다."
authors:
  - petelepage
article:
  written_on: 2014-04-30
  updated_on: 2014-10-21
  order: 2
id: rwd-patterns
priority: 1
collection: multi-device-layouts
---

{% wrap content%}


반응형 웹 페이지에 사용되는 대부분의 레이아웃은 유동형, 열 끌어놓기, 레이아웃 시프터, 미세 조정 및 오프 캔버스라는 5가지 패턴 중 하나로 분류될 수 있습니다.

일부 경우에 페이지에서 패턴 조합(예: 열 끌어놓기 + 오프 캔버스)을 사용할 수
있습니다.  [Luke
Wroblewski](http://www.lukew.com/ff/entry.asp?1514)가 처음으로 식별한 이러한 패턴은 모든 반응형
페이지에 강력한 시작점을 제공합니다.

## 패턴

간단하고 이해하기 쉬운 패턴을 생성하기 위해, [`flexbox`](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Flexible_boxes)을 사용하여 아래의 각 샘플을 생성했습니다. 이때 일반적으로 기본 컨테이너 `div`에 3개의 콘텐츠 `div`가 포함됩니다.



 각 샘플은 먼저 가장 작은 보기부터 작성하고 필요한 경우 중단점을 추가했습니다.
  최적의 지원을 위해 공급업체 접두어가 필요할 수도 있지만 최신 브라우저에서 [flexbox 레이아웃 모드가 잘 지원됩니다](http://caniuse.com/#search=flexbox).



{% include modules/nextarticle.liquid %}

{% endwrap %}
