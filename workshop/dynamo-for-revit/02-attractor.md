---
description: パラメトリックに変化する点の集合体を作成する。
---

# \#02 初歩: アトラクタ

## コードの作成方法

画面を**ダブルクリック**するとCode Blockノードが作成されます。
![CodeBlock画像](https://user-images.githubusercontent.com/48234687/101979865-1801b400-3ca4-11eb-9969-689899c4b0bf.jpg)



試しに以下のコードを記入します。
~~~
a = 4;
b = 2;
a + b;
~~~
![CodeBlock2](https://user-images.githubusercontent.com/48234687/101979873-2f40a180-3ca4-11eb-9055-f674f0ba91a6.jpg)


出力結果を確認する時は**Watch　Block**を使用します。
![image](https://user-images.githubusercontent.com/48234687/101979951-dde4e200-3ca4-11eb-90e7-56a19b601812.png)



変数を指定しない場合は
Code Block内を以下の様に記述します。
~~~
a;
b;
a + b;
~~~

左タブから**Input**を選択して、**Number Slider**を選択するとスライダーが出てきます。
このスライダーの出力先とCode Blockの**a,b**の箇所に接続するとスライダーで変数を変えることができます。
![BlockConnection](https://user-images.githubusercontent.com/48234687/101979881-467f8f00-3ca4-11eb-92e9-115e80216c08.jpg)


NumberSliderの設定は左側の矢印を選択すると設定することができます。
![SliderBox](https://user-images.githubusercontent.com/48234687/101979900-729b1000-3ca4-11eb-8c52-caa8360ca807.jpg)


**Inputタブ**の中には文字列を入力できる**String**ノードなどもあります。

プラスマークと雷マークの違い

プラスマークは**Create**で何かを作成(または構築)をします。

雷マークは**Action**で何かに対してアクションを実行します。

**Query**は時間など既知の値を取得してくれます。


##　点を作成する方法

左のタブの中の**Geometry**から**Point**を選択すると点を作成するノードがあります。
![image](https://user-images.githubusercontent.com/48234687/101980088-497b7f00-3ca6-11eb-934a-c47ad8939f99.png)

座標などを指定して点を作ることができます。
![image](https://user-images.githubusercontent.com/48234687/101980139-b98a0500-3ca6-11eb-9c11-7f04367c04d5.png)


{% hint style="danger" %}
ノード組み合わせていると，膨大なノードで分からなくなるので，整理することが大切です。
例としてノードをBoxなどで整理しましょう。
![image](https://user-images.githubusercontent.com/48234687/101980329-da9f2580-3ca7-11eb-9fec-95041b761e37.png)
{% endhint %}



## アトラクタの作成

まず，基準となる点を作成します.

![image](https://user-images.githubusercontent.com/48234687/102007649-42b83f00-3d6e-11eb-86b8-51d1bffa645f.png)

次に**Geometry**に中の**Modifiers**の中の**Geometry**内にある**DistanceTO**を選択します。

![image](https://user-images.githubusercontent.com/48234687/102007688-8ca12500-3d6e-11eb-90ce-fb446fd7a8b6.png)


DicetanceToは今回の場合，アトラクトと他の点の距離を計算してくれます.

![image](https://user-images.githubusercontent.com/48234687/102007741-03d6b900-3d6f-11eb-987a-9b48338b29f8.png)

次に**Geometry**内の**Curve**の中の**Circle**から**ByCenterPointRadius**を選択します．
**centerPoint**が中心の位置，**rasius**が半径となります．

![image](https://user-images.githubusercontent.com/48234687/102007824-86f80f00-3d6f-11eb-8a65-b6f20ce12324.png)

**ByCenterPointRadius**の半径をを先ほどの二点間距離の出力に接続します.
そうすることで，二点間距離が半径になります．

![image](https://user-images.githubusercontent.com/48234687/102007879-f7069500-3d6f-11eb-90d1-489d138b43ec.png)

割り算のノードを加えることで円の直径が割った値になります．

![image](https://user-images.githubusercontent.com/48234687/102008047-0cc88a00-3d71-11eb-9a2c-80be73d9b059.png)


次に**Sequnece**といったノードを使用します．
こちらのノードは
例として**Point.ByCoordinates**と接続した際は
**start**で点の位置
**amount**で点の個数
**step**で点の間隔幅
を決めます．

![image](https://user-images.githubusercontent.com/48234687/102008130-a3954680-3d71-11eb-93fd-9e091fd42bf7.png)

Sequenceの出力をx,yに接続した後に，**Point.ByCoordinates**の出力を先ほどの**ByCenterPointRadius**ノードのcenterpositionに接続すると，Sequenceで指定した位置に円が作成されます.

![image](https://user-images.githubusercontent.com/48234687/102008300-c83dee00-3d72-11eb-9837-093aace477db.png)

次に**Sequence**に接続された**Point。ByCoordinates**ノードを右クリックして**レーシング**から**外積**を選択します．

![image](https://user-images.githubusercontent.com/48234687/102008410-7fd30000-3d73-11eb-9253-7da8b95724b0.png)

すると以下の様になります．

![image](https://user-images.githubusercontent.com/48234687/102008446-d93b2f00-3d73-11eb-8c93-3b66b32ce35b.png)

他の点の出力を切りSequenceによる**Point.ByCoordinates**の出力をつなげます．
そうすることでアトラクタの位置に応じて円の半径が変わる仕組みが作成できます．

![image](https://user-images.githubusercontent.com/48234687/102008617-4bf8da00-3d75-11eb-91e9-8af5f459b299.png)


現在配列構造が構築されているため，配列を一列にすることも可能です．
**List.Flatten**といったノードを使用することでListの形式がフラットになります．

![image](https://user-images.githubusercontent.com/48234687/102008759-4059e300-3d76-11eb-8bb3-9f008a0f5443.png)

押し出しの操作を加えることで以下の様に円柱も作成可能になります．

![image](https://user-images.githubusercontent.com/48234687/102008841-b8280d80-3d76-11eb-8176-e1cd7066d654.png)
