---
description: '#03のつづき。斜壁部分。'
---

# \#04 マンホール作成 02

## 前回の続きで今回はマンホールの途中の箇所を作成します．

右クリックで**Explode**と検索して以下のノードを選択します． Surface.ThickenのSolidと接続します．

![image](https://user-images.githubusercontent.com/48234687/103391860-bb850c80-4b5e-11eb-9d4e-adae38332ec0.png)

以下のノードのプレビューを非表示にします．

![image](https://user-images.githubusercontent.com/48234687/103392068-6e556a80-4b5f-11eb-94c9-947da0c2e48e.png)

右のタブの中の**LIst**,**Inspect**,**GetItemAtINdex**を選択します．

![image](https://user-images.githubusercontent.com/48234687/103392124-baa0aa80-4b5f-11eb-9f76-a152c89a913c.png)

以下のようにIntegerSliderを設定して，ノードを接続します． Listの中の番号に対応したSurfaceが出力されます． こちらのノードをはたくさん使います．

![image](https://user-images.githubusercontent.com/48234687/103392305-79f56100-4b60-11eb-849c-b44a4424a7fd.png)

今回は2で設定して上部のsurfaceを選択します

![image](https://user-images.githubusercontent.com/48234687/103392398-0738b580-4b61-11eb-8ecd-bd8ef0c8210c.png)

次にPerimeterCurveを選択します．

![image](https://user-images.githubusercontent.com/48234687/103392532-b9707d00-4b61-11eb-9da4-ab7a003d764b.png)

Itemの出力と接続すると以下のようになります．現在選択されているsurfaceは２つの線から構成されているため二つ出力されます．

![image](https://user-images.githubusercontent.com/48234687/103392590-02283600-4b62-11eb-86aa-b5f3771a0ab5.png)

内側の線を同様に抽出していきます．

![image](https://user-images.githubusercontent.com/48234687/103392734-a90cd200-4b62-11eb-8cfd-aa52c04476d6.png)

以下の三つをコピーして選択した状態で右クリック，カスタムノードの作成を選択します． カスタムノードを作成は複数のノードから独自のノードを作成することができます．

![image](https://user-images.githubusercontent.com/48234687/103392930-73b4b400-4b63-11eb-9976-65f1936303d7.png)

以下のように名前をつけてカテゴリをRevitにしておきます．

![image](https://user-images.githubusercontent.com/48234687/103393004-df971c80-4b63-11eb-9888-05874e6a81b7.png)

以下のように作成されて，検索から見つけやすくなります

![image](https://user-images.githubusercontent.com/48234687/103393126-7ebc1400-4b64-11eb-8974-24041596a61b.png)

以下のように接続します．厚みは前回と同じ箇所から持ってきます．

![image](https://user-images.githubusercontent.com/48234687/103393272-2e918180-4b65-11eb-9445-069902df1546.png)

カスタムノードをダブルクリックすると中身を確認することができます．

![image](https://user-images.githubusercontent.com/48234687/103393218-f1c58a80-4b64-11eb-821f-6ddc72c44648.png)

高さを菅取り付け高さに名前を変更する．

![image](https://user-images.githubusercontent.com/48234687/103393365-9b0c8080-4b65-11eb-8710-94ab73ea6caa.png)

コピーしてノードの名前を直壁高さにします．

![image](https://user-images.githubusercontent.com/48234687/103393412-dc9d2b80-4b65-11eb-88e0-4c3731a14034.png)

Distanceに直壁高さを接続すると以下のようになります．

![image](https://user-images.githubusercontent.com/48234687/103393483-2ede4c80-4b66-11eb-8130-edb212be7bca.png)

次に中心が欲しいため **Geometry**,**Curve**,**Circle**,**CenterPoint**を選択する

![image](https://user-images.githubusercontent.com/48234687/103395166-1a9f4d00-4b70-11eb-815c-7be5997c1096.png)

先程の内部線を取り出す一連のノードをカスタムノードにし，接続するとデータ型が違うためエラーが出ます

![image](https://user-images.githubusercontent.com/48234687/103395840-81723580-4b73-11eb-9647-4dc8d083536a.png)

なので，surfaceを一度作成してから中心点を作成する ByPatchを選択してsurfaceを作成する．

![image](https://user-images.githubusercontent.com/48234687/103396020-415f8280-4b74-11eb-81fe-d4624ed69cb9.png)

面が作成される．

![image](https://user-images.githubusercontent.com/48234687/103396090-79ff5c00-4b74-11eb-9c53-5dc83a44742b.png)

**Geometry**,**Surface**,**surface**からPointatparameterを選択する．

![image](https://user-images.githubusercontent.com/48234687/103396175-fbef8500-4b74-11eb-89c7-099b4ffb65fa.png)

uvのベクトル座標から今回は真円なので\[0.5,0.5\]が中心となるため以下のようにノードを繋げると中心になる．

![image](https://user-images.githubusercontent.com/48234687/103396259-8a640680-4b75-11eb-80b7-c70a1f7d5124.png)

![image](https://user-images.githubusercontent.com/48234687/103396259-8a640680-4b75-11eb-80b7-c70a1f7d5124.png)

斜壁高さのノードを作成します．

![image](https://user-images.githubusercontent.com/48234687/103396372-4291af00-4b76-11eb-9d1e-ea8fdb87af01.png)

moveのノードも作成します． zTranslationに斜壁高さを接続します

![image](https://user-images.githubusercontent.com/48234687/103396520-25111500-4b77-11eb-8258-c7e17123a2d0.png)

ByPointRadiusを作成します

![image](https://user-images.githubusercontent.com/48234687/103396573-5be72b00-4b77-11eb-98eb-c28a7cf06080.png)

以下の直径とそれにつながるノードをコピーしてノード名を斜壁直径にします．

![image](https://user-images.githubusercontent.com/48234687/103396642-b5e7f080-4b77-11eb-93a6-3c3c7293613a.png)

以下の様に配置すると円が描かれます．

![image](https://user-images.githubusercontent.com/48234687/103396744-3ad30a00-4b78-11eb-9360-b86b9b8f4884.png)

loftと検索して以下のノードを作成します．

![image](https://user-images.githubusercontent.com/48234687/103396797-8980a400-4b78-11eb-840f-4150f907f882.png)

次にリストを作成します．

左のタブの**List**,**Generate**,**List Create**を選びます

![image](https://user-images.githubusercontent.com/48234687/103396867-e4b29680-4b78-11eb-84a1-d01f3796788a.png)

以下の様にノードを構成します．

![image](https://user-images.githubusercontent.com/48234687/103396965-60acde80-4b79-11eb-8ad7-59d1fd8edc98.png)

