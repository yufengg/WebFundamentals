---
layout: section
title: "端末画面の向き"
description: "端末モーションと画面の向きのイベントによって、モバイルデバイスに組み込まれた
加速度計、ジャイロスコープ、およびコンパスへアクセスすることができます。"
introduction: "端末モーションと画面の向きのイベントによって、モバイルデバイスに組み込まれた
加速度計、ジャイロスコープ、およびコンパスへアクセスすることができます。"
article:
  written_on: 2014-06-17
  updated_on: 2014-10-21
  order: 4
id: device-orientation
collection: device-access
authors:
  - petelepage
priority: 1
remember:
  not-stable:
    - device motion イベントまたは device orientation イベントの使用を決定する際には、<b>最大限に</b>注意を払ってください。  残念ながら、すべてのブラウザが同じ座標系を 使用するとは限りません。また、同じような状況の下で別の値が 報告されることがあります。
---
{% wrap content%}

これらのイベントは多くの目的のために使用することができます。
たとえばゲームでは、キャラクターの向きを制御したり、キャラクターがジャンプする高さを
決定するために使用します。 GeoLocation と共に使用する際には、より正確なターンバイターンのナビゲーションシステム
を作成したり、店の場所に関する情報を提供することができます。

{% include modules/remember.liquid title="Warning" list=page.remember.not-stable %}

## どちらの端が上か?

device orientation イベントや motion イベントによって返されたデータを使用するためには、
提供される値を理解することが重要です。  

### 地球の座標フレーム

地球の座標フレームは `X`、`Y`、および `Z` の値によって記述され、
重力と標準磁気の向きに基づいて配列されます。

<ul>
  <li>
    <b>X:</b> は東西方向を表します (東が正)。
  </li>
    <li>
    <b>Y:</b> は南北方向を表します (北が正)。
  </li>
    <li>
    <b>Z:</b> 地面に対して垂直上下方向を表します
    (上が正)。
  </li>
</ul>

### 端末の座標フレーム

端末の座標フレームは `x`、`y`、および `z` の値によって記述され、
端末の中心に基づいて配列されます。

<img src="images/axes.png" alt=" 端末の座標フレームの図">
<!-- Sheppy の(https://developer.mozilla.org/en-US/profiles/Sheppy) 
  パブリックドメインへの画像投稿に感謝します。 -->

<ul>
  <li>
    <b>x:</b> 画面の平面、右方向が正。
  </li>
    <li>
    <b>y:</b> 画面の平面、上方向が正。
  </li>
    <li>
    <b>z:</b> 画面またはキーボードに対して垂直、延びている方向が
    正。
  </li>
</ul>

携帯電話やタブレットで、端末の向きは画面の典型的な向き
に準じています。  携帯電話やタブレットで、縦表示の端末
に準じています。 デスクトップまたはラップトップ コンピュータの場合は、画面の向きはキーボードとの関連性で
考慮されます。

### 回転データ

回転データは [Euler angle](http://en.wikipedia.org/wiki/Euler_angles) として返されます。
これは、端末の座標フレームと地球は座標フレーム間の
f差異度の数を表します。

<div>
  <div class="g--third">
    <img src="images/alpha.png"><br>
    <b>アルファ:</b> Z 軸周りの回転は、端末上部が
真北に向いている場合 0 &deg;です。  端末が反時計回りに回転するにつれて
    `alpha` 値が増加します。
  </div>
  <div class="g--third">
    <img src="images/beta.png"><br>
    <b>ベータ:</b> X 軸周りの回転は、端末の上部と底部が地球の
表面から等距離にある場合 0 &deg;です。 端末の上部が
地球の表面に向かって傾斜するにつれて、値が増加します。
  </div>
  <div class="g--third g--last">
    <img src="images/gamma.png"><br>
    <b>ガンマ:</b> Y 軸周りの回転は、端末の左端と右端が地球の
表面から等距離にある場合 0 &deg;です。  端末の右端が
地球の表面に向かって傾斜するにつれて、値が増加します。 
  </div>
</div>

<div style="clear:both;"></div>


{% include modules/nextarticle.liquid %}

{% endwrap %}
