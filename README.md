# Haga-Utsunomiya-LRT-GTFS
芳賀・宇都宮LRTのGTFSデータを趣味で作っています。  
順次更新中です、閲覧の際には下記の注意点を必ずお読みください。
## 注意点  
本レポジトリはmagn01iaが趣味の範囲で開通予定の芳賀・宇都宮LRTのGTFSデータを作成しているものです。  
事業本体とはなんら関係性のない個人のものですので十分ご注意下さい。   
改善点等ございましたら是非ご意見ください。
## GTFS
GTFS(General Transit Feed Specification)とは公共交通に関する世界標準のフォーマットです、GTFSデータには2種類あり、GTFS-Staticと呼ばれるルートや停留所、時刻表などの静的データとGTFS-Realtimeと呼ばれる運行状況や乗車人数などの動的データがあります。本リポジトリはGTFS-Staticになります。 
## 各データについての説明
各データ名の()内にはデータが必須なのか任意で良いのか記載しました。  
データは静的バス情報フォーマット(GTFS-JP)仕様書(第3版)をもとに作成しています。  
一部データはgeojsonでも作成していますのでgithub上で直接レンダリングされます。
### stops(必須)
停留所のポイント情報です。  
idは宇都宮駅を101_1とし、芳賀方面へ102_1、103_1、104_1…としています。  
芳賀→宇都宮方面についてはアンダーバーの次の数字を"2"にしています。  
また、停留所が一ヶ所のみと思われる停留所については宇都宮→芳賀のid(アンダーバー以下1)を採用しています。  
宇都宮市が公開しているのルート予定情報をもとに作成しています。
### shapes(任意)
運行ルートのポイント情報です。
idはとりあえずの所で1000(宇都宮→芳賀)1001(芳賀→宇都宮)にしてあります。  
データはOpenStreetMapからLRT運行予定ルートを抽出しQGISで編集し作成されています。
## 参考リンク
[静的バス情報フォーマット（GTFS-JP)仕様書(第3版)(国土交通省)](https://www.mlit.go.jp/sogoseisaku/transport/sosei_transport_tk_000112.html)  
[宇都宮市](https://www.city.utsunomiya.tochigi.jp/index.html)  
[© OpenStreetMap contributors](https://www.openstreetmap.org/copyright)   
shapes.txtの作成に使用。  
## 更新履歴
20220722stops.txt、stops.geojson追加  
20220114shapes.geojson追加  
20220113shapes.txt  
20220113リポジトリ作成
