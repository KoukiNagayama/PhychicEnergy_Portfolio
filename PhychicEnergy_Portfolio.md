<head>
<style>
.bg-gray{
  background-color: #F0F0F0;
}
</style>
</head>

<body style="background-color: #gray">
<div class="bg-gray">

# **PhychicEnergy**

河原電子ビジネス専門学校  

ゲームクリエイター科2年　長山宏毅  

# **目次**
<font size = "3">

1. [作品概要](#1-作品概要) 
2. [操作説明](#2-操作説明)
3. [担当ソースコード](#3-担当ソースコード)
4. [エンジン側の改造したソースコード](#4-エンジン側の改造したソースコード)
5. [技術紹介](#5-技術紹介)  
  5.1. [世界の回転](#51-世界の回転)   
  5.2. [輪郭線](#52-輪郭線)   
  5.3. [フラスタムカリング](#53-フラスタムカリング)  
  5.4. [カスケードシャドウ](#54-カスケードシャドウ)  
  5.5. [トゥーンシェーディング]()  
  5.6. []()
6. [こだわった点](#6-こだわった点)  
  6.1. [世界を回転させた理由](#61-世界を回転させた理由)  
  6.2. [プレイヤーの動きの軽やかさ](#62-プレイヤーの動きの軽やかさ)   
  6.2. [ロックオン機能](#62-ロックオン機能)  
  6.3. [カメラによるストレスを減らすために](#63-カメラによるストレスを減らすために)


</font>

<br>.

# **1. 作品概要**
## **PhychicEnergy**
&emsp;三人称視点のタイムアタック型のアクションゲームです。  
&emsp;プレイヤーはモードを変更することで浮遊することができます。  
&emsp;浮遊状態の時にオブジェクトに向かって飛ぶことによってぶつかった場所に張り付くことができます。  
&emsp;この力を駆使して、短い時間でマップ上にある全てのリングを取得することが目的です。  
<br>



- 制作人数  
  - 1人
- プレイ人数
  - 1人  
- 制作期間
  - 2022年9月～2023年2月
  
- 開発環境
  - OS
    - Windows 10
  - エンジン
    - 学校内製の低レベルエンジンを改造したもの(DirectX 12)
  - ツール
    - プログラミング
      - Visual Studio 2019
    - モデル
      - 3ds Max 2020
      - VRoid
    - テクスチャ
      - Adobe Photoshop 2023
    - エフェクト
      - Effekseer
    - データ管理
      - git
    - タスク・スケジュール管理
      - Notion

- URL
  - [GitHub](https://github.com/KoukiNagayama/PhychicEnergy)
 
<br>

# **2. 操作説明**
### **Xboxコントローラー**

<font size = "3">

- LTボタン - スライディング
- LBボタン - 浮遊状態を解除
- 左スティック - 移動
- 右スティック - カメラを回転
- RBボタン
  - 通常時 - 浮遊の静止状態に移行
  - 浮遊の静止時 - カメラの方向に向かって移動
  - 浮遊の移動時 - 浮遊の静止状態に移行
- RTボタン - ロックオン
- Aボタン - ジャンプ

</font>

&emsp;<img alt="操作説明_左" src="image/controllerOperation_left.png">

&emsp;<img alt="操作説明_右" src="image/controllerOperation_right.png">

# **3. 担当ソースコード**

<details><summary>メイン側ソースコード(.h , .cpp)</summary>

- Title
  - Title
    - Title.h
    - Title.cpp
  - BackGround
    - TitleBackGround.h
    - TitleBackGround.cpp
  - Camera
    - TitleCamera.h
    - TitleCamera.cpp
  - Sprite
    - TitleSprite.h
    - TitleSprite.cpp
  - BGM
    - TitleBGM.h
    - TitleBGM.cpp
  - Character
    - TitleCharacter.h
    - TitleCharacter.cpp
- InGame
  - Game
    - Game.h
    - Game.cpp
  - Player
    - IPlayerState.h
    - Player.h
    - Player.cpp
    - PlayerIdleState.h
    - PlayerIdleState.cpp
    - PlayerWalkState.h
    - PlayerWalkState.cpp
    - PlayerJumpState.h
    - PlayerJumpState.cpp
    - PlayerSlideState.h
    - PlayerSlideState.cpp
    - PlayerFallState.h
    - PlayerFallState.cpp
    - PlayerIdleInAirState.h
    - PlayerIdleInAirState.cpp
    - PlayerFallInAirState.h
    - PlayerFallInAirState.cpp
  - Ring
    - Ring.cpp
    - Ring.h
  - BGM
    - MainBGM.h
    - MainBGM.cpp
  - Fade
    - Fade.h
    - Fade.cpp
  - Timer
    - DisplayGameTimer.h
    - DisplayGameTimer.cpp
  - LockOn
    - LockOn.h
    - LockOn.cpp
  - GravityGauge
    - GravityGauge.h
    - GravityGauge.cpp
  - Sight
    - Sight.h
    - Sight.cpp
  - BackGround
    - BackGround.h
    - BackGround.cpp
  - Camera
    - GameCamera.h
    - GameCamera.cpp
- Result
  - Result
    - Result.h
    - Result.cpp
  - BGM
    - ResultBGM.h
    - ResultBGM.cpp
  - Sprite
    - ResultSprite.h
    - ResuleSprite.cpp
    

</details>

<details><summary>エンジン側ソースコード(.h , .cpp)</summary>

- RenderingEngine
  - RenderingEngine.h
  - RenderingEngine.cpp
- ModelRender
  - ModelRender.h
  - ModelRender.cpp
- Level
  - MapChipRender.h
  - MapChipRender.cpp
  - LevelRender.h
  - LevelRender.cpp
- PostEffect
  - PostEffect.h
  - PostEffect.cpp
  - OutLine.h
  - OutLine.cpp
  - Fxaa.h
  - Fxaa.cpp
- Lighting
  - SceneLight.h
  - SceneLight.cpp
  - MyRenderer.h
- Geometry
  - GeometryData.h
  - GeometryData.cpp
  - SceneGeometryData.h
  - SceneGeometryData.cpp
- SkyCube
  - SkyCube.h
  - SkyCube.cpp
- Shadow
  - ShadowMapRender.h
  - ShadowMapRender.cpp
  - CascadeShadowMapMatrix.h
  - CascadeShadowMapMatrix.cpp
- Camera
  - SpringCamera.h
  - SpringCamera.cpp
  - CameraCollisionSolver.h
  - CameraCollisionSolver.cpp
- SpriteRender
  - SpriteRender.h
  - SpriteRender.cpp
- ToonMap
  - ToonMap.h
  - ToonMap.cpp
- WorldRotation
  - WorldRotation.h
  - WorldRotation.cpp

</details>

<details><summary>シェーダー(.fx)</summary>

- fxaa.fx
- outline.fx
- blackBackModel.fx
- depthForOutLine.fx
- drawShadowMap.fx
- gravityGauge.fx
- pbr.fx
- redBackModel.fx
- ring.fx
- toomModel.fx
- SkyCubeMap.fx
</details>
<br>

# **4. エンジン側の改造したソースコード**
<details><summary>ソースコード</summary>

- CharacterController
  - CharacterController.cpp  
  ※接触している面の法線を取得できるように変更
- Matrix 
  - Matrix.h  
  ※行列同士の比較をするために==を使えるように変更
- Vector
  - Vector.h  
  ※Vector4クラスにLerp関数を追加し、線形補間をできるように変更
- Physics
  - Physics.cpp   
  ※MyRayResultCallback構造体とRayTest関数を改造し、レイから衝突点の法線を取得できるように変更。

</details>
<br>

# **5. 技術紹介**
<font size="3">

## **5.1. 世界の回転**  
</font>

## 回転方法
<font size = "3">

1. 回転に使用する回転行列を作成する。
2. プレイヤーのワールド行列から平行移動成分を抽出し行列とする。
3. 2で作成した平行移動行列から逆行列を計算する。
4. 回転させるオブジェクトのワールド行列に対して、3で計算したプレイヤーの平行移動行列の逆行列を乗算する。
5. 4で計算された行列に対して、1で作成した回転行列を乗算する。  
6. 5で計算された行列に対して、2で計算したプレイヤーの平行移動行列を乗算する。
</font>
<br>
<br>

<font size = "4">

### 4. 回転させるオブジェクトのワールド行列に対して、3で計算したプレイヤーの平行移動行列の逆行列を乗算する。  
</font>
<br>

<br>

**プレイヤーの平行移動行列の逆行列** とは、 **「プレイヤーの平行移動行列に乗算するとプレイヤーがワールド座標の原点に移動する行列」** のことです。

&emsp;<img alt="inverseMatrix" src="image/inverseMatrix.png">  

よってプレイヤーの平行移動行列の逆行列を乗算した場合、オブジェクトがこのように移動する。

&emsp;<img alt="multiply_1" src="image/multiply_1.png">    

この座標はプレイヤーが世界の原点であると仮定した場合の座標となる。

<br>
<font size = "4">

### 5. 4で計算された行列に対して、1で作成した回転行列を乗算する。
</font>

オブジェクトを90度回転させる回転行列の場合

&emsp;<img alt="multiply_2" src="image/multiply_2.png">  

ワールド座標の原点を中心として回転するため、
<font size="3">

**乗算前のワールド座標と乗算後のワールド座標では原点に対しての距離が変わらない。**  
</font>
<br>

<font size ="4">

### 6. 5で計算された行列に対して、2で計算したプレイヤーの平行移動行列を乗算する。
</font>

&emsp;<img alt="multiply_3" src="image/multiply_3.png">  

プレイヤーの平行移動行列を乗算する理由としては、現在はプレイヤーを世界の原点と仮定した計算を行ったワールド座標となっているため、プレイヤーの平行移動行列の逆行列の逆行列である、プレイヤーの平行移動行列を乗算することで、世界の原点を元のワールド座標の原点とした時のワールド座標にしている。  
<br>
<font size ="4">

### 計算後
</font>

&emsp;<img alt="afterRotation" src="image/afterRotation.png">


<br>


<font size = "3">

## **5.2. 輪郭線**
</font>  
このゲームでは、

  - ポストエフェクトによる輪郭線
  - フロントカリングを行ったモデルを法線方向に拡張して作る背面モデル輪郭線  

の2種類が実装されているハイブリッド輪郭線となっている。

### **2種類にする利点**
2つの輪郭線はそれぞれ細かく違う特徴を持っている。
その中でも今回注目した違いは以下の通りとなっている。
- ポストエフェクトの場合
  - 対象とカメラの距離に関係なく、描画される輪郭線の大きさは指定された大きさから変化しない。
- フロントカリングを行ったモデルから作る場合
  - 対象とカメラの距離によって、描画される輪郭線の大きさが変化する。

<br>

<font size="3">

**[対象とカメラが遠い場合]**
&emsp;<img alt="outlineComparison_far" src="image/outlineComparison_far.png">  
</font> 
背面モデルの輪郭線が小さくてもポストエフェクトの輪郭線がある為、最低限の大きさが確保されており、見えやすい。 

<br>

<font size="3">

**[対象とカメラが近い場合]**
&emsp;<img alt="outlineComparison_near" src="image/outlineComparison_near.png">  
</font> 
背面モデルが目立つようになっている為、ポストエフェクトが見えなくなっている。


<br>

## 手順  
<font size="3">

- ポストエフェクト
  
1. 輪郭線を適用するオブジェクトの深度値をレンダリングテクスチャに書き込む。
2. 1で深度値を書き込んだレンダリングテクスチャから対象ピクセルの周りのピクセルとの深度の違いを検出する。
3. 深度の違いの平均が大きい場合は対象ピクセルは輪郭であると判断する。 
4. 輪郭であると判断された場合には、ピクセルを塗りつぶす。

- 背面モデル
  
1. 輪郭線を適用するオブジェクトのモデルと同じモデルをフロントカリングして同じ座標に設定する。
2. 法線方向に拡張する。
3. モデルを全て黒で出力する。

</font>
<br>
<font size = "3">

## **5.3. フラスタムカリング**
</font>
このゲームでは、オブジェクトを多く配置しているため、1フレームで全てを描画していると処理落ちしてしまうため、必要なオブジェクトは描画しないように減らす必要がある。

<br>

フラスタムカリングは、カメラからの視錐台の範囲内にオブジェクトのAABB(軸平行境界ボックス)の頂点があるかどうかを判断し、それによって描画するかどうかを確定する。

&emsp;<img alt="frustumCulling" src="image/frustumCulling.png">

## 手順  
<font size="3">

1. カメラの情報から作成した透視変換行列とカメラのビュー行列からビュープロジェクション行列を計算する。  
2. オブジェクトに割り当てているAABBの頂点のワールド座標を計算する。
3. 2で計算したワールド座標に対して、1で計算したビュープロジェクション行列を乗算し、ビュープロジェクション空間の座標に変換する。  
4. AABBの頂点座標が既定値の範囲にあれば描画する。

</font>

<br>

<font size="3">

## **5.4. カスケードシャドウ**
</font>
カスケードシャドウは、カメラに対して近いエリアの影を鮮明に描画し、遠いエリアの影ほど品質を下げるという手法。  

具体的な内容としては、分割するエリアの数だけシャドウマップを用意し、エリアに合ったシャドウマップに対して、エリアのオブジェクトを描画し、シャドウマップを作成する。影を適用させる際も、ピクセルがシャドウマップに含まれているのかどうかを判断し、エリアに合わせる。

## 手順
<font size="3">

1. 分割エリアの定義を行う。
2. 1で行った定義に合わせてシャドウマップを用意する。
3. ライトカメラから見たエリアを内包する視錐台の8頂点を計算する。
4. クロップ行列を計算する。
5. ライトビュープロジェクション行列に4で求めたクロップ行列を乗算する。

(ここからシェーダー)  

6. 5で求めたライトビュープロジェクションクロップ行列からピクセルのライトビュースクリーン空間の座標を計算する。
7. 6で求めた座標を用いて、ピクセルがどのシャドウマップに含まれているかを確定させて、影を落とす。　　

</font>





# **6. こだわった点**

<font size="3">

## **6.1. 世界を回転させた理由**
</font>

始めはプレイヤーに合わせて世界を回転させる手法ではなく、プレイヤー自体を回転させるという手法に挑戦していた。プレイヤー自体を回転させるということは「プレイヤーの当たり判定を逐一変化する」ということとなるため、ある角度では壁や床の判定が取れていなかったり、めり込まないような修正ができていなかったりなどの問題が発生した。  
そのため、**世界側を回転させることで、プレイヤーの当たり判定を変化させなくともよい**ということになった。

<br>

<font size="3">

## **6.2. ロックオン機能**
</font>

このゲームのロックオン機能は、カメラで追うのではなく、目標を見失わないようにどこを見ていても分かりやすくするというものとなっている。 
<br>

&emsp;**[画面内に目標がある場合]**  
&emsp;<img alt="lockOnInScreen" src="image/lockOnInScreen.png" width="250px">  

&emsp;**[画面内に目標がない場合]**  
&emsp;<img alt="offScreenLockOn" src="image/offScreenLockOn.png" width="250px">  
(目標のスクリーン座標が画面右側の外にある場合)
  
<br>  

このようにした理由としては、プレイヤーのプレイスタイルに幅がなくなってしまうためとなっている。    
もし、カメラが目標に対して固定されてしまうと、浮遊状態での移動の特徴として、カメラの中心に飛んでいくという性質があるため、プレイヤーはただロックオンをして飛ぶだけで目標に到達することが可能となってしまう。  
そうではなく、目標以外を狙うということも可能にしつつ、目標が画面外に出た場合には見失わないようということにを重視した結果このような形式となった。

<br>

<font size="3">

## **6.3. カメラによるストレスを減らすために**
</font>



## 手順
<font size="3">

1. 


</font>
<font size="3">

## **6.2. プレイヤーの動きの軽やかさ**
</font>
このゲームは、プレイヤーが浮遊をすることや壁に張り付くことなど通常の床に触れている時間が非常に少ない。そのため、プレイするユーザー自身もプレイをしていて「ふわっ」というような感覚を味わえるようにプレイヤーのジャンプや浮遊状態の時は上昇中や下降中は素早く、最高到達点での動きはゆっくりとなるようにしている。




ランプテクスチャ


</div>


