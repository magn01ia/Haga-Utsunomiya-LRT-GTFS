# Haga-Utsunomiya-LRT-GTFS  
![125547](https://user-images.githubusercontent.com/84883260/220530957-b5af260b-676c-41cc-b8d5-4171e3ea5aa0.png)  
芳賀・宇都宮LRTのGTFSデータを趣味で作っています。  
上図は作成したデータを株式会社MIERUNE様より公開されているQGISプラグインGTFS-GOを利用し可視化したものです。  
背景地図は地理院地図ベクターを使用しています。  
作成当初は手入力で行っていましたが、運航開始に伴って「見える化共通入力フォーマット」を使用しています。  
時刻表データは公開されているものがpdfだったため、一度Excelのデータ取得機能を経由して入力しています。  

Cesiumを使用してマップを作成しました。  
↓  
[Haga-Utsunomiya-LRT-Cesium ](https://github.com/magn01ia/Haga-Utsunomiya-LRT-Cesium)  

## 🎉202311XX    
LRTの運行が開始され、時刻表情報なども公開されたことから、これまでダミーだったデータを更新しました。  
- 作成ツールの変更  
これまでは情報も少なかったこともありテキストエディタ等で作成していましたが、今後の更新も考慮して見える化共通入力フォーマットで作成することにしました。
- 停留所idの見直し  
停留所idの振り方を変更しました、見える化共通入力フォーマットのマクロに従い作成しています。
- 停留所名の修正  
芳賀・高根沢工業団地前→芳賀・高根沢工業団地  

## ⚡注意点  
本レポジトリはmagn01iaが趣味の範囲で開通予定の芳賀・宇都宮LRTのGTFSデータを作成しているものです。  
事業本体とはなんら関係性のない個人のものですので十分ご注意下さい。   

## 🚊GTFS
GTFS(General Transit Feed Specification)とは公共交通に関する世界標準のフォーマットです、GTFSデータには2種類あり、GTFS-Staticと呼ばれるルートや停留所、時刻表などの静的データとGTFS-Realtimeと呼ばれる運行状況や乗車人数などの動的データがあります。本リポジトリはGTFS-Staticになります。 

## 🗒️各データについての説明
データは静的バス情報フォーマット(GTFS-JP)仕様書(第3版)をもとに、見える化標準フォーマットに従い作成しています。  
shape.txtについてはOpenStreatMapの情報を抽出してQGISで編集し作成しています。  
一部データはgeojsonでも作成していますのでgithub上で直接レンダリングされます。

### agency
事業者情報です。  

### stops
停留所のポイント情報です。  
idは2桁数字で  
|1桁目|2桁目|
|-|-|
|宇都宮駅東口→芳賀・高根沢工業団地前<br>に向かって1.2.3.4と連番|下り線停留所を1、上り線停留所を2<br>停留所が上り下り共有の場合は1|  

### trips
経路情報です。三桁数字の割り振りは、  
- 1桁目：1経路のみのため基本的に1、将来西側が開通した際にはそちらを2にしたい。  
- 2桁目：上り線(宇都宮方面行)を1とし、下り線(芳賀方面行)を2とした。  
- 3桁目：
  
|上り線：3桁目の番号|経路|
|-|-|
|1|平石→宇都宮駅東口| 
|2|芳賀・高根沢工業団地前→宇都宮駅東口|
|3|芳賀・高根沢工業団地前→平石|
|4|グリーンズスタジアム前→宇都宮駅東口|
|5|グリーンスタジアム前→平石|

|下り線：3桁目の番号|経路|
|-|-|
|1|平石→芳賀・高根沢工業団地前| 
|2|宇都宮駅東口→芳賀・高根沢工業団地前|
|3|芳賀・高根沢工業団地前→平石|
|4|グリーンズスタジアム前→宇都宮駅東口|
|5|グリーンスタジアム前→平石|

### stop_times
停留所の通過時刻情報です。宇都宮ライトレール株式会社HPに掲載されている時刻表pdfを基に作成しています。  
公開されているデータがpdfだったため、一度Excelのデータ取り込み機能を経由して作成しています。  

### calendar
~~平日のみ運行などの運行区分情報です。  
仮に平日のみ運行と土曜のみの運行、日曜祝日のみ運行のパターンを作成しました。~~

### shapes
運行ルートのポイント情報です。
idはとりあえずの所で11(芳賀→宇都宮)12(宇都宮→芳賀)にしてあります。  
将来西側が開通した際には1桁目を２にしたい。  
データはOpenStreetMapからLRT運行予定ルートを抽出しQGISで編集し作成されています。

## 参考リンク
[静的バス情報フォーマット（GTFS-JP)仕様書(第3版)(国土交通省)](https://www.mlit.go.jp/sogoseisaku/transport/sosei_transport_tk_000112.html)  
[宇都宮市](https://www.city.utsunomiya.tochigi.jp/index.html)  
[宇都宮ライトレール株式会社](https://www.miyarail.co.jp/)  
[OpenStreetMap](https://www.openstreetmap.org/copyright)    
[GTFS-GO](https://github.com/MIERUNE/GTFS-GO)  
[見える化共通入力フォーマット](https://www.rosenzu.com/net/mieru/fm/index.html)
