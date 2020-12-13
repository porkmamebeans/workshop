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


##点を作成する方法

左のタブの中の**Geometry**から**Point**を選択すると点を作成するノードがあります。
![image](https://user-images.githubusercontent.com/48234687/101980088-497b7f00-3ca6-11eb-934a-c47ad8939f99.png)

座標などを指定して点を作ることができます。
![image](https://user-images.githubusercontent.com/48234687/101980139-b98a0500-3ca6-11eb-9c11-7f04367c04d5.png)


{% hint style="danger" %}
ノード組み合わせていると，膨大なノードで分からなくなるので，整理することが大切です。
例としてノードをBoxなどで整理しましょう。
![image](https://user-images.githubusercontent.com/48234687/101980329-da9f2580-3ca7-11eb-9fec-95041b761e37.png)
{% endhint %}



## 2点から線の作成方法

以下のノード構成で二点から線を作成することができます.

![image](https://user-images.githubusercontent.com/48234687/102004657-0b3d9880-3d56-11eb-942e-334cccc2e87c.png)


##　作成した線から面を押し出す方法
** Geometory ** の中にある**Curve**から**Extrude**を選択します.

![image](https://user-images.githubusercontent.com/48234687/102004748-c2d2aa80-3d56-11eb-99b4-8ffe16470aad.png)

**Cureve**の箇所を**Line**と接続して，**Distance**をNumber Sliderなどとつなげます.
するとXY平面の面が作成されます.

![image](https://user-images.githubusercontent.com/48234687/102004787-3aa0d500-3d57-11eb-820f-8e35f1570fb8.png)


サーフェスを表示している際に，点や線が不要に感じた場合はラインの場合だとラインを作成しているノードを右クリックします.
そこでプレビューをオフにします.オフにすることでラインが非表示になります.

![image](https://user-images.githubusercontent.com/48234687/102004859-ee09c980-3d57-11eb-87a6-e27fdf2d6c54.png)


次にノードを右クリックをしてフリーズを選択するとノードとノードにつながるものが点線になります.
フリーズはプログラミングの際にコメントアウトする機能と同じです.

![image](https://user-images.githubusercontent.com/48234687/102004907-5f497c80-3d58-11eb-9213-fa96a90f401d.png)

![image](https://user-images.githubusercontent.com/48234687/102004923-8902a380-3d58-11eb-9fba-c3dce76bc9da.png)

{% hint style="danger" %}
フリーズはノードが多くなった場合，動作が重くなるため必要な時以外はフリーズにすることをお勧めします.
必要な時にだけフリーズを解除して表示してください.
{% endhint %}




