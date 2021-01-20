---
description: マンホールのまとめ、演習問題。
---

# \#05 マンホール作成 03

## \#05 マンホール作成 03

**混乱を回避する方法**

カスタムノードの設定 以下のようにインプットする箇所の変数定義名を変更することで混乱を防ぐことができる．

![image](https://user-images.githubusercontent.com/48234687/103401626-f9008e80-4b8c-11eb-8fe5-2ebcea69a23c.png)

![image](https://user-images.githubusercontent.com/48234687/103401798-bbe8cc00-4b8d-11eb-893e-ccbd2251669d.png)

カスタムノードを作る際のポイントとして一度グループを作成してから，カスタムノードを作成すると混乱が防げます．

### 外側のサーフェスの作成

今回はわかりやすくするために以下のようにします． ブーリアンをInputに置き換えます

![image](https://user-images.githubusercontent.com/48234687/103475567-91974880-4df1-11eb-9a81-0ea00d2f6363.png)

![image](https://user-images.githubusercontent.com/48234687/103475605-dfac4c00-4df1-11eb-8832-dd80fa7029ec.png)

今回は前回作成した斜壁に厚みを持たせます． 直壁と同じ厚みを使用して円を作成します．

![image](https://user-images.githubusercontent.com/48234687/103475891-91e51300-4df4-11eb-8854-53ba288d13ce.png)

外側も内側と同様にサーフェスを貼っていきます．

![image](https://user-images.githubusercontent.com/48234687/103475997-5c8cf500-4df5-11eb-9fb4-eb168e15ae2e.png)

前回内側の線を選択したカスタムノードを外側の線を選択するように変更したノードを接続してサーフェスを接続します．

![image](https://user-images.githubusercontent.com/48234687/103476189-e5586080-4df6-11eb-88e6-f635f9a1a90c.png)

**やり方は一様ではないので自分に合ったやり方などで進めてください**

次に上部にサーフェスを貼ります． ここのやり方は前回やっているのでそちらを参考に

![image](https://user-images.githubusercontent.com/48234687/103476336-fe154600-4df7-11eb-9c97-61be2fd8fec6.png)

上部の面を作ったので下部の面を作成します．

最後に作成した４つの面を使用してソリッドを作成します．

![image](https://user-images.githubusercontent.com/48234687/103476412-a4614b80-4df8-11eb-8942-441699e542b9.png)

以下のようにソリッドを作成して完成です．

![image](https://user-images.githubusercontent.com/48234687/103476444-0326c500-4df9-11eb-85b3-267a8f808edc.png)

斜壁の基準点を移動することで以下のようにすることが可能です

![image](https://user-images.githubusercontent.com/48234687/103476470-716b8780-4df9-11eb-9dd2-07dbc849560f.png)

## DynamoからRevitにオブジェクトとして読み込む方法

ImportInstance.ByGeometryを使用してRevitでオブジェクトとして出力することができます．

![image](https://user-images.githubusercontent.com/48234687/103402704-ea1bdb00-4b90-11eb-9eec-43b1aaabb55e.png)

