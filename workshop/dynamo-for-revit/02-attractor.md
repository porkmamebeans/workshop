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


