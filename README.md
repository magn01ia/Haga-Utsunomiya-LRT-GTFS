# Haga-Utsunomiya-LRT-GTFS
芳賀・宇都宮LRTのGTFSデータを趣味で作っています。  
順次更新中です、閲覧の際には下記の注意点を必ずお読みください。
## 注意点  
本レポジトリはmagn01iaが趣味の範囲で開通予定の芳賀・宇都宮LRTのGTFSデータを作成しているものです。  
事業本体とはなんら関係性のない個人のものですので十分ご注意下さい。  
## GTFS
GTFS(General Transit Feed Specification)とは公共交通に関する世界標準のフォーマットです、GTFSデータには2種類あり、GTFS-Staticと呼ばれるルートや停留所、時刻表などの静的データとGTFS-Realtimeと呼ばれる運行状況や乗車人数などの動的データがあります。本リポジトリはGTFS-Staticになります。 
## 各データについての説明
各データ名の()内にはデータが必須なのか任意で良いのか記載しました。  
データは静的バス情報フォーマット(GTFS-JP)仕様書(第3版)をもとに作成しています。
### shapes.txt(任意)
運行ルート情報です。※現在宇都宮→芳賀のデータのみ作成。  
idはとりあえずの所で1000にしてあります。  
データはOpenStreetMapからLRT運行予定ルートを抽出しQGISで編集し作成されています。
## 利用データ・ツール
[© OpenStreetMap contributors](https://www.openstreetmap.org/copyright)   
shapes.txtの作成に使用。  
QGIS  
データ編集に使用。
## 参考リンク
[静的バス情報フォーマット（GTFS-JP)仕様書(第3版)(国土交通省)](https://www.mlit.go.jp/sogoseisaku/transport/sosei_transport_tk_000112.html)
## 更新履歴
20220113shapes.txt(宇都宮→芳賀)追加  
20220113リポジトリ作成
