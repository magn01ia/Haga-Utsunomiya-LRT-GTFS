# Haga-Utsunomiya-LRT-GTFS  
![125547](https://user-images.githubusercontent.com/84883260/220530957-b5af260b-676c-41cc-b8d5-4171e3ea5aa0.png)  
芳賀・宇都宮LRTのGTFSデータを趣味で作っています。  
順次更新中です、  
上図は作成したデータを株式会社MIERUNE様より公開されているQGISプラグインGTFS-GOを利用し可視化したものです。  
背景地図は地理院地図ベクターを使用しています。  

 
Cesiumを使用してマップを作成しました  
↓  
[Haga-Utsunomiya-LRT-Cesium ](https://github.com/magn01ia/Haga-Utsunomiya-LRT-Cesium)  

## ⚡20231115⚡    
LRTの運行が開始され、時刻表情報なども公開されたことから、これまでダミーで入力していたデータを本格的に更新中です。  

## 注意点  
本レポジトリはmagn01iaが趣味の範囲で開通予定の芳賀・宇都宮LRTのGTFSデータを作成しているものです。  
事業本体とはなんら関係性のない個人のものですので十分ご注意下さい。   
## GTFS
GTFS(General Transit Feed Specification)とは公共交通に関する世界標準のフォーマットです、GTFSデータには2種類あり、GTFS-Staticと呼ばれるルートや停留所、時刻表などの静的データとGTFS-Realtimeと呼ばれる運行状況や乗車人数などの動的データがあります。本リポジトリはGTFS-Staticになります。 
## 各データについての説明
各データ名の()内にはデータが必須なのか任意で良いのか記載しました。  
データは静的バス情報フォーマット(GTFS-JP)仕様書(第3版)をもとに作成しています。  
一部データはgeojsonでも作成していますのでgithub上で直接レンダリングされます。
### agency(必須)  
事業者情報です。  
ダミーでid"000000000"のみ記載しています。 
### stops(必須)
停留所のポイント情報です。  
idは宇都宮駅を101_1とし、芳賀方面へ102_1、103_1、104_1…としています。  
芳賀→宇都宮方面についてはアンダーバーの次の数字を"2"にしています。  
また、停留所が一ヶ所のみと思われる停留所については宇都宮→芳賀のid(アンダーバー以下1)を採用しています。  
宇都宮市が公開しているのルート予定情報をもとに作成しています。
### trips(必須)
経路情報です。  
宇都宮→芳賀の月曜日～金曜日の運行便を1000_01とし、
芳賀→宇都宮の月曜日～金曜日の運行便を1001_01としています。
### stop_times(必須)
停留所の通過時刻情報です。  
tripsで割り当てた宇都宮発芳賀方面行(1000_01)と芳賀発宇都宮方面行(1001_01)の各停留所通過時刻を割り当てています。  
仮にそれぞれ0:0:0秒発1秒後着のデータにしています。
### calendar(条件付必須)
平日のみ運行などの運行区分情報です。  
仮に平日のみ運行と土曜のみの運行、日曜祝日のみ運行のパターンを作成しました。

### shapes(任意)
運行ルートのポイント情報です。
idはとりあえずの所で1000(宇都宮→芳賀)1001(芳賀→宇都宮)にしてあります。  
データはOpenStreetMapからLRT運行予定ルートを抽出しQGISで編集し作成されています。
## 参考リンク
[静的バス情報フォーマット（GTFS-JP)仕様書(第3版)(国土交通省)](https://www.mlit.go.jp/sogoseisaku/transport/sosei_transport_tk_000112.html)  
[宇都宮市](https://www.city.utsunomiya.tochigi.jp/index.html)  
[OpenStreetMap](https://www.openstreetmap.org/copyright)
