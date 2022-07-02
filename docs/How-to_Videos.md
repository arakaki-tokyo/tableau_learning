# How-to Videos 内容まとめ

## 参照
- [Resources \| Tableau Public](https://public.tableau.com/en-us/s/resources)
- 一部日本語版あり：[リソース \| Tableau Public](https://public.tableau.com/ja-jp/s/resources)


## 概要



## viz 埋め込みテスト

<div class='tableauPlaceholder' id='viz1657084924909' style='position: relative'><noscript><a href='#'><img alt='CO2 Emissions around the World ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;ta&#47;tableau_070602&#47;1_1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='tableau_070602&#47;1_1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;ta&#47;tableau_070602&#47;1_1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='ja-JP' /><param name='filter' value='publish=yes' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1657084924909');                    var vizElement = divElement.getElementsByTagName('object')[0];                    vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';                    var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>



## メモ

### 全般
- シートの種類：
  - ワークシート：1シートにつき、一つのチャートを作成する。左サイドバーにあるフィールドを使用する。
  - ダッシュボード：複数のチャート(ワークシート)をまとめる。左サイドバーにあるシートを使用する。
  - ストーリー：複数のワークシートやダッシュボードをプレゼンテーションとしてまとめる。

### ワークシート
- フィールド：データペインに表示されるディメンション・メジャーの各項目
  - 離散(discrete)データ：青。通常グラフ上でヘッダーとなる。
  - 連続(continuous)データ：緑。通常グラフ上で軸の値となる。▼から離散データとして扱うことも可能。
- マーク
  - ツールヒント：マウスホバー時などにポップアップするツールチップの書式を編集
- 「表示形式」(Show Me)ツールバー：
  - フィールドを複数選択することで利用可能なグラフが示される

### ダッシュボード
- フィルター機能：
  - チャートのフィルターアイコンをクリック。チャート同士を関連付け、クリックによる選択で別チャートの表示項目を絞る。
  - フィルターによって別チャートのスケールが変わらないようにするには、チャートの縦軸ラベルをダブルクリックし、「範囲」で「固定」を選択
  - チャートの▼から、そのチャートに適用されるフィルターを選択することもできる。その場合、ワークシートでフィルタリング項目をツールヒントに追加しておく。
  - 
- ハイライト機能：フィルターでは未選択のデータは非表示になるが、ハイライトでは全てのデータは表示されたまま。
  - メニューバー「ダッシュボード」>「アクション」>「アクションの追加」>「ハイライト」
  - フィルターの動作が優先されるため、フィルターを無効化。
- ツールバー「書式設定」>「ワークブック」より、一括でフォント設定可能
- チャートのマージンを取るには、サイドバーの「オブジェクト」から「空白」を使用する
- デバイスデザイナーによるレスポンシブデザインの設計
- 

### ストーリー
- 追加方法：
  - 左サイドバーからワークシートやダッシュボードをダブルクリック or DDで追加する。
- 状態を保持：
  - 同一のシートでも、特定のデータをハイライトさせた状態で保持することが可能(操作後、「更新」をクリック)
- サイズ調整：
  - ストーリーのシートを作成後、新たにワークシートやダッシュボードを作成した場合、サイドバーの「サイズ」>「固定」から「[ストーリー名]に合わせる」を選択できる。
- 書式設定：
  - メニューバー「書式設定」>「ストーリー」から、全体の背景色やタイトル、ナビゲーター、テキストボックスのフォントを設定可能
  - サイドバー「レイアウト」より、ナビゲーターのスタイルを選択可能
    - デフォルトだと「点」のレイアウトが詰まって見える。その場合、「キャプションボックス」を選択して「●」などの記号を入力する方法が使える。
- プレビュー：
  - メニューバーの「プレゼンテーションモード」アイコンからプレビューを確認
- 

## How-to Videos コンテンツ一覧

- 1\. Tableau Public Overview
	- 日本語版あり：Tableau Public の概要	
	- [x] watch
- 2\. Connecting to Excel and Text Files
	- [ ] watch
- 3\. Connecting to Google Sheets
	- [ ] watch
- 4\. Connecting to Web Data Connectors
	- [ ] watch
- 5\. Connecting to Spatial Files
	- 日本語版あり：空間ファイルへの接続 
	- [x] watch
- 6\. Connecting to PDFs
	- [ ] watch
- 7\. Data Preparation – The Data Interpreter
	- 日本語版あり：データ準備 - データインタープリター
	- [x] watch
- 8\. Data Preparation – Pivoting your Data
	- 日本語版あり：データ準備 - データのピボット
	- [x] watch
- 9\. Data Preparation – Splitting your Data
	- 日本語版あり：データ準備 - データの分割
	- [x] watch
-  10\. Data Preparation – Joins and Unions
	- 日本語版あり：データ準備 - 結合とユニオン
	- [x] watch
- 11\. Creating Your First Chart
	- 日本語版あり：初めてのチャート作成 
	- [x] watch
- 12\. Using the Show Me Tool Bar
	- [x] watch
- 13\. Understanding the Logic of Charts
	- [x] watch
- 14\. Combining Sheets on a Dashboard
	- ダッシュボードに複数のシートをまとめる
	- [x] watch
- 15\. Adding Interactivity to Dashboards
	- 日本語版あり：ダッシュボードへのインタラクティブ性の追加
	- [x] watch
- 16\. Dashboard Formatting
	- [x] watch
- 17\. Creating Stories
	- [x] watch
- 18\. Formatting Story Points
	- [x] watch
- 19\. Designing for Mobile with the Device Designer
	- 日本語版あり：デバイスデザイナーを使ってモバイル用にデザインする
	- [x] watch
- 20\. Publishing and Embedding Vizzes
	- [ ] watch
- 22\. Edit Vizzes on the Web
	- [ ] watch
- 21\. Adding a custom Viz in Tooltip
	- [ ] watch