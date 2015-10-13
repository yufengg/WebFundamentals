---
layout: article
title: "개발 단계"
description: "모든 개발자는 프로젝트 개발 과정 동안 다양한
  단계를 거칩니다. Web Starter Kit는 생산성을 높이고 각 단계에서
  수행해야 하는 작업의 범위를 간소화합니다."
introduction: "개발 과정 동안 gulp serve, gulp 및 gulp serve:dist 등 3개의 명령을
 정기적으로 사용하게 됩니다.
  각 작업이 사이트를 개발하는 데 어떤 식으로 도움이 되는지 살펴봅시다."
notes:
article:
  written_on: 2014-04-17
  updated_on: 2014-10-21
  order: 2
id: development-phases
priority: 1
collection: web-starter-kit
authors:
  - mattgaunt
key-takeaways:
---

{% wrap content %}

{% include modules/toc.liquid %}

## 로컬 서버 시작하기

살펴볼 첫 번째 작업은 `$ gulp serve`입니다.

표면상, 이 작업은 브라우저에서 사이트를 볼 수 있도록 로컬 HTTP 서버를
시작하지만 그 배후에는 작동하는 도구가 몇 가지 더 있습니다.

### 라이브 다시 로드(Live Reload)

라이브 다시 로드 기능은 편집기에서 변경하고 브라우저로 전환하고
CTRL-R을 누른 후 페이지가 다시 로드될 때까지 기다리는 등 기존의 새로 고침 작업을
제거합니다.

라이브 다시 로드를 사용하면 편집기에서 변경 작업을 수행하고 사이트가 열린 상태로 모든 유형의 브라우저에서 변경 내용을 즉시
적용할 수 있습니다.

<div class="media media--video">
  <iframe src="https://www.youtube.com/embed/JE-ejS8N3YI?controls=2&amp;modestbranding=1&amp;showinfo=0&amp;utm-source=crdev-wf&amp;rel=0" frameborder="0" allowfullscreen=""></iframe>
</div>

### 여러 장치에서 테스트하기

브라우저 동기화(Browser Sync) 기능은 여러 장치에서 사이트를 테스트하는 데 도움이 됩니다. 모든 스크롤,
탭 또는 키보드 누르기 동작은 모든 연결된 브라우저에서 공유됩니다.

<div class="media media--video">
  <iframe src="https://www.youtube.com/embed/RKKBIs_3svM?controls=2&amp;modestbranding=1&amp;showinfo=0&amp;utm-source=crdev-wf&amp;rel=0" frameborder="0" allowfullscreen=""></iframe>
</div>

이 기능은 `gulp serve`를 사용하여 사이트를 실행할 때만 작동합니다. `gulp serve`를 실행하고
URL을 두 개의 브라우저 창에 나란히 연 후 페이지 중 하나를
스크롤해 보십시오.

### 접두사 지정 자동화하기

다양한 브라우저를 대상으로 할 때 각 브라우저에 포함된 기능을 사용할 수
있도록 공급업체 접두사를 사용해야 합니다. Web Starter Kit는 접두사 지정
작업을 자동화합니다.

아래에 예로 든 CSS에는 공급업체 접두사가 없습니다.

    .app-bar-container {
      display: flex;

      width: 100%;
      height: 60px;
      position: relative;

      flex-direction: row;

      margin: 0 auto;
    }

빌드 프로세스는 autoprefixer를 통해 CSS를 실행하여 아래와 같은
최종 출력을 생성합니다.

    .app-bar-container {
      display: -webkit-flex;
      display: -ms-flexbox;
      display: flex;

      width: 100%;
      height: 60px;
      position: relative;

      -webkit-flex-direction: row;
          -ms-flex-direction: row;
              flex-direction: row;

      margin: 0 auto;
    }

### Javascript 확인하기

JSHint는 작성한 JavaScript 코드를 검사하여 JavaScript 논리와 관련하여 발생할 수 있는
문제를 확인하고 [코딩 모범 사례를 적용](http://www.jshint.com/docs/)하는 도구입니다.

프로젝트를 빌드할 때마다 또는 gulp 서버를 실행하는 경우 JavaScript
파일을 변경할 때마다 이 도구가 실행됩니다.

### Sass 컴파일하기

serve 명령을 실행하는 동안 프로젝트의 Sass 파일 변경 내용은
CSS로 컴파일되고 접두사가 지정된 후에 라이브 다시 로드를 통해
페이지가 다시 로드됩니다.

Sass에 새로 추가된 사항이 있는 프로젝트는 "CSS 확장
언어"라고 합니다. 근본적으로 CSS 확장 언어는 몇 가지 기능이 추가된 CSS입니다. 예를 들어,
CSS 확장 언어는 재사용 가능한 모듈 형식으로 CSS를 구성하는 데 도움이 되는
변수 및 함수를 추가로 지원합니다.

## 사이트의 프로덕션 버전 빌드하기

단순한 `gulp` 명령을 사용하여 사이트의 프로덕션 준비 버전을
빌드할 수 있습니다. 이 명령은 앞에서 이미 살펴본 일부 작업을 실행할 뿐만 아니라 사이트 로드를
더 빠르고 효율적으로 만드는 작업도 실행합니다.

프로덕션 빌드가 수행하는 주요 작업은 다음과 같습니다.

### 스타일 빌드하기

첫 번째 빌드 단계에서는 프로젝트에서 Sass를 컴파일합니다. Sass가 컴파일된 후
Autoprefixer가 모든 CSS에서 실행됩니다.

### JavaScript에서 문제 확인하기

두 번째 빌드 단계에서는 JavaScript에서 JSHint를 실행합니다.

### HTML 페이지 빌드하기

그 다음 단계에서는 HTML 파일을 검토하여 JavaScript를 연결하고 간소화할
빌드 블록을 찾습니다. JavaScript를 검토한 후 빌드 프로세스는 HTML
페이지를 간소화합니다.

간소화 작업에서는 실제로 필요하지 않은 주석 또는 공백 문자와 
기타 기술을 제거하여 최종 JavaScript 파일의 문자 수를
줄입니다. 이는 최종 파일 크기를 줄여 사이트 로드 시간을
단축합니다.

연결은 여러 파일의 내용을 한 파일에 붙여넣는 작업을 의미합니다. 이러한
작업을 하는 이유는 브라우저가 서버에 여러 요청 말고 하나의 요청만
하여 빠른 실행이 가능하도록 하기 위해서입니다.

빌드 블록에는 간소화하고 함께 연결할 JavaScript 파일을 관리하는 데
필요한 모든 것이 들어 있습니다. 샘플 빌드 블록을 살펴보겠습니다.

    <!-- build:js scripts/main.min.js -->
    <script src="scripts/example-1.js"></script>
    <script src="scripts/example-2.js"></script>
    <!-- endbuild -->

빌드 블록은 특별한 형식이 지정된 주석일 뿐입니다.
빌드 블록 사이의 모든 javascript 파일은 main.min.js라는 하나의
파일로 병합(연결)되고 간소화되며 최종 빌드는 script
태그로 이러한 스크립트를 대체합니다.

    <script src="scripts/main.min.js"></script>

### 이미지 자산 최적화하기

JPEG 및 PNG의 경우 이미지의 메타데이터는 이미지를 렌더링하는 데
필요하지 않으므로 제거됩니다. 메타데이터에는 사진을 찍는 데 사용된 카메라와 같은
정보가 들어 있습니다.

SVG의 경우 필요하지 않은 특성이 모두 제거되거나 존재하는 공백 및
주석이 모두 제거됩니다.

### 글꼴 복사하기

이 단순한 작업은 앱의 글꼴을 최종 빌드 디렉터리로 복사합니다.

### 루트 디렉터리에서 모든 파일 복사하기

빌드가 프로젝트의 루트 디렉터리에서 파일을 찾을 경우 이를
최종 빌드에도 복사합니다.

## 프로덕션 빌드 테스트하기

프로덕션하기 전에 모든 것이 예상대로 작동하는지 확인해야
합니다. `gulp serve:dist` 명령은 사이트의 프로덕션 버전을 빌드하고 서버를 시작하고 브라우저를
엽니다. 이 명령은 **라이브 다시 로드나 
브라우저 동기화 기능이 없지만** 사이트를 배포하기 전에 테스트할 수 있는 신뢰할 수 있는 방법입니다.

{% include modules/nextarticle.liquid %}

{% endwrap %}
