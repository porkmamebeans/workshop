# Dynamo

### C3D Dynamo Pythonノードのテンプレートのエラー

![](<../../.gitbook/assets/image (21).png>)

Pythonノードのテンプレーㇳで、

```
adoc = Application.DocumentManager.MdiActiveDocument
editor = adoc.Editor
```

の行でエラー起きたので、

```
from Autodesk.AutoCAD.ApplicationServices import Application as app
```

を上のインポートの箇所に入れたらいけた

### ProtoGeometryのありか

LineとかVectorとかPointとかビルトインのオブジェクトは、以下のリンクにもあるパスに記述されている

{% embed url="https://forum.dynamobim.com/t/references-protogeometry-dll-in-revit-macro/17227" %}

### Autodesk.DesignScript.GeometryとAutodesk.AutoCAD.DynamoNodes

![](<../../.gitbook/assets/image (18).png>)

Autodesk.DesignScript.Geometryクラスは、Dynamoのノードの中で扱われるオブジェクトのクラスで、Selectノードや、他のCivil3D(Revitも同様)を選択して参照してくるタイプのノードのアウトプットは、Autodesk.AutoCAD.DynamoNodesクラスとなり、別物。

DynamoNodesクラスからDynamoで扱えるようにするように変換するノードは、`Object.Geometryノード。`

![](<../../.gitbook/assets/image (20).png>)

### DesignScriptGuide

{% file src="../../.gitbook/assets/DesignScriptGuide.pdf" %}

