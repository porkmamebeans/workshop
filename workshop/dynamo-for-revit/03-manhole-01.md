---
description: ググってマンホールの寸法を取りながらマンホール作ってみよう。
---

# \#03 マンホール作成 01

## \#03 マンホール作成 01

{% embed url="https://unihole.jp/kouzou/size/manhole\_1/" caption="" %}

マンホール作成するにあたって上記サイトの中に記載されている，寸法が重要になってきます． 今回特に重要な寸法は高さ，直径，厚みになってきます．

## 空中円柱の作成

### 円柱の作成

Dynamoから新規作成を選択します．

整数のみの数値を指定できる_Integer Slider_を使用します．

![image](https://user-images.githubusercontent.com/48234687/103218602-cbce9900-495e-11eb-9596-3d82e2d6f5af.png)

範囲は直径を想定して600から1500で指定します．ステップを100で設定します．

![image](https://user-images.githubusercontent.com/48234687/103218779-616a2880-495f-11eb-862c-d3b6e4341d2b.png)

ノードの名前を変更します．ノードを右クリックするとノードの名前を変更するが出てくるので選択します．

![image](https://user-images.githubusercontent.com/48234687/103218874-95dde480-495f-11eb-9ded-5b425213eb0b.png)

変更すると以下のようになります．

![image](https://user-images.githubusercontent.com/48234687/103219000-e0f7f780-495f-11eb-917b-454b58301f0d.png)

Ctrlキーを押しながらドラッグすると，ノードを複製することができます．

![image](https://user-images.githubusercontent.com/48234687/103219077-143a8680-4960-11eb-8ea5-37f9716c8433.png)

ノードの名前を高さに変更して，範囲を0〜2000にして，ステップを50にします．

![image](https://user-images.githubusercontent.com/48234687/103219186-5bc11280-4960-11eb-9c66-f48f77d280de.png)

左のタブから_Geometry_,_Solids_,_Cylinder_から_ByRadiusHeight_を選択します．

![image](https://user-images.githubusercontent.com/48234687/103219372-e144c280-4960-11eb-984f-c02b98445ab5.png)

このノードは半径と高さを指定することができます．

![image](https://user-images.githubusercontent.com/48234687/103219579-76e05200-4961-11eb-9d61-02c62c1f5e4a.png)

以下の画像のように直径を２で割って，radiusに接続します． 高さをheightに接続します．

![image](https://user-images.githubusercontent.com/48234687/103219760-f2da9a00-4961-11eb-901e-ed2db5f1bc1d.png)

\*\*差分を使用して空中円筒を作成する

先程の円柱を作成するノードの組み合わせをグループ化します．

![image](https://user-images.githubusercontent.com/48234687/103220365-6df08000-4963-11eb-91ec-7a4fb8111c28.png)

名前を_外の円柱_にします

![image](https://user-images.githubusercontent.com/48234687/103220462-ac863a80-4963-11eb-957e-ceec56bc4c1b.png)

ノードグループをCtrlキーを押しながらドラッグして複製します． 名前を_内の円柱_にします．

![image](https://user-images.githubusercontent.com/48234687/103220605-fd962e80-4963-11eb-8cd3-ba7496aea5b8.png)

厚みを考えるにあたって以下のように考えます．

![image](https://user-images.githubusercontent.com/48234687/103221362-c759ae80-4965-11eb-941d-feaef27a3ea5.png)

厚みのノードを以下のように設定します． 範囲を50〜150にして，ステップを25にします．

![image](https://user-images.githubusercontent.com/48234687/103221600-61b9f200-4966-11eb-98f2-f06982d2fcf9.png)

先程の内側の円を求める式を参考にして以下のようにノードを配置します． ここで，高さは同じなので変数を同じにします．

![image](https://user-images.githubusercontent.com/48234687/103248498-26431600-49ae-11eb-9de5-9459821acbf2.png)

次に内側の円柱をくり抜いていきます． 左のタブの中から**Geometry**,**Solids**,**Solid**の中にある**Difference**を選択します．

![image](https://user-images.githubusercontent.com/48234687/103248620-c5680d80-49ae-11eb-85c0-d407a1c19e08.png)

Solidに元となる図形，otherに引きたい図形を接続します． 先程作成した円柱のプレービュー設定をオフにします．Slinderのノードを右クリックすると設定できます．

![image](https://user-images.githubusercontent.com/48234687/103248801-9e5e0b80-49af-11eb-99e5-b46606131650.png)

\*\*押し出しから空中円柱を作成

円を作成します． **Geometry**,**Curves**,**Circle**から**ByPointRadius**を選択します．

![image](https://user-images.githubusercontent.com/48234687/103249079-e3cf0880-49b0-11eb-8ce4-1e12add26e8d.png)

先程作成した直径，割り算，2を持ってきて接続します．

![image](https://user-images.githubusercontent.com/48234687/103249235-a028ce80-49b1-11eb-811b-b48da21bdf18.png)

次に押し出し**Extrude**を選択します Distanceの方を選択します

![image](https://user-images.githubusercontent.com/48234687/103249329-f990fd80-49b1-11eb-8477-3d39c3d30432.png)

先程作成した円柱のノードのプレビューをオフにします． 高さを接続すると以下のようなサーフェスが作成されます

![image](https://user-images.githubusercontent.com/48234687/103249435-905dba00-49b2-11eb-8f5b-08d9913b5e30.png)

次にサーフェスに厚みを持たせるため右クリックで**Thick**を入れます．

![image](https://user-images.githubusercontent.com/48234687/103249561-34dffc00-49b3-11eb-88b4-5dbc1f29d2bc.png)

二つの種類があるのですが，基本厚みを与える際に，＋方向は外側のことを指します．そのため，内側の直径は変わらずに外側の直径が大きくなってきます． **both\_side**の方はブーリアンでTrueかFalseを入力することで内側の円を基準に両サイド均等に厚みを与えます．

![image](https://user-images.githubusercontent.com/48234687/103249631-8ab4a400-49b3-11eb-9179-841573e1232e.png)

both\_sideの方で厚みを持たせると空中円柱が作成できます．

![image](https://user-images.githubusercontent.com/48234687/103249995-22ff5880-49b5-11eb-8633-64eb14455f9c.png)

