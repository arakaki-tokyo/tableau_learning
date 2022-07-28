# <span id="cp2">Chapter 2</span>　テクニックで解決
- data: `付属データ/Chap02/`

## 目次
- [Chapter 2](#cp2)　 テクニックで解決
    - [2.1](#cp2_1)　 積み上げ棒グラフで各棒の値を表示
    - [2.2](#cp2_2)　 折れ線グラフでマークを強調
    - [2.3](#cp2_3)　 スケールの異なるメジャーを並べた折れ線グラフ
    - [2.4](#cp2_4)　 メジャーネームと指定の小計を表示したクロス集計
    - [2.5](#cp2_5)　 指定の3段階で色分けしたハイライト表
    - [2.6](#cp2_6)　 百万の単位でラベル表記し、データが空でもすべての値を表示
    - [2.7](#cp2_7)　 複数のディメンションがある棒グラフの並べ替え
    - [2.8](#cp2_8)　 データがないセルに0を表示
    - [2.9](#cp2_9)　 少ない度数をまとめたヒストグラム
    - [2.10](#cp2_10)　将来日付データの領域まで表示
    - [2.11](#cp2_11)　積み上げ棒グラフの棒内でカテゴリを並べ替え
    - [2.12](#cp2_12)　積み上げ棒グラフの色カテゴリで棒を並べ替え
    - [2.13](#cp2_13)　前年同月比を最終年のみ表示
    - [2.14](#cp2_14)　各カテゴリの上位Nのみ表示
    - [2.15](#cp2_15)　4月開始の上期・下期の表示
    - [2.16](#cp2_16)　長いテキストの折り返し表示
    - [2.17](#cp2_17)　左右の軸の範囲を合わせたピラミッドチャート
    - [2.18](#cp2_18)　異なるデータの異なるフィールド値同士の比較
    - [2.19](#cp2_19)　選択フィルター値を挿入したタイトル
    - [2.20](#cp2_20)　異なるダッシュボードへのフィルターアクション


## <span id="cp2_1">2.1</span>　積み上げ棒グラフで各棒の値を表示
- data: `付属データ/Chap02/2.1_trade_prices_tokyo(2020).csv`
- Viz: [ch\.2\.1: 積み上げ棒グラフで各棒の値を表示 \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_1/2_1?publish=yes)

🌟ポイント
- リファレンスラインの活用


## <span id="cp2_2">2.2</span>　折れ線グラフでマークを強調
- data: `付属データ/Chap02/2.2_pcr_positive_daily.csv`
- Viz: [ch\.2\.2: 折れ線グラフでマークを強調 \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_2/sheet0?publish=yes)

🌟ポイント
- 二重軸によって1つのチャートとして強調する

<video controls loop width="600" poster='img/2_2.png' src='img/2_2.webm'></video>

## <span id="cp2_3">2.3</span>　スケールの異なるメジャーを並べた折れ線グラフ
- data: `付属データ/Chap02/2.3_sp500_historical_quotes(2010_2020).csv`
- Viz: [ch\.2\.3: スケールの異なるメジャーを並べた折れ線グラフ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_3/sheet0?publish=yes)

🌟ポイント
- 各行または列の独立した軸範囲
- 最小値/最大値のみラベルを表示


### 別解
- WINDOW関数によって最小値と最大値のフィールドを作成する。
  - 式：下記
- Viz: 前掲Vizの[別解シート](https://public.tableau.com/views/ch_2_3/sheet2?:language=ja-JP&publish=yes&:display_count=n&:origin=viz_share_link)

```
IF WINDOW_MAX(AVG([Close])) == AVG([Close]) THEN AVG([Close])
ELSEIF WINDOW_MIN(AVG([Close])) == AVG([Close]) THEN AVG([Close])
ELSE NULL
END
```


## <span id="cp2_4">2.4</span>　メジャーネームと指定の小計を表示したクロス集計
- data: `付属データ/Chap02/2.4_hittakuri_tokyo(2019).csv`
- Viz: [ch\.2\.4: メジャーネームと指定の小計を表示したクロス集計 \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_4/sheet0?publish=yes)

🌟ポイント
- 小計の表示／非表示の指定
- クロス集計表におけるメジャーのヘッダー

<video controls loop width="600" poster='img/2_3.png' src='img/2_3.webm'></video>

## <span id="cp2_5">2.5</span>　指定の3段階で色分けしたハイライト表
- data: `付属データ/Chap02/2.5_access_to_electricity_%_of_population_region.csv`
- Viz: [2\.5: 指定の3段階で色分けしたハイライト表 \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/2_53_16589947691820/sheet0?publish=yes)

🌟ポイント
- 色に使うフィールドが非連続の場合、マークタイプを四角にしても背景全体を塗りつぶしできない
  - 🔍参照：[正方形のマークがセルの背景を均一に塗りつぶさない \| Tableau Software](https://kb.tableau.com/articles/issue/square-mark-does-not-uniformly-fill-background-of-cell?lang=ja-jp)
- 動画のテクニックを使うか、フィードを連続データにする

```
IF AVG([Access to Electricity (% of population)]) < 70 THEN "LOW"
ELSEIF AVG([Access to Electricity (% of population)]) < 90 THEN "MID"
ELSE "HIGH"
END
```

<video controls loop width="600" poster='img/2_5.png' src='img/2_5.webm'></video>


## <span id="cp2_6">2.6</span>　百万の単位でラベル表記し、データが空でもすべての値を表示
- data: `付属データ/Chap02/2.6_trade_prices_tokyo(2020).csv`
- Viz: [ch\.2\.6: 百万の単位でラベル表記し、データが空でもすべての値を表示 \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_6/sheet0?publish=yes)

🌟ポイント
- メニューバー[分析] > [表のレイアウト]より、空の行や列の表示／非表示を切り替える

<video controls loop width="600" poster='img/2_6.png' src='img/2_6.webm'></video>


## <span id="cp2_7">2.7</span>　複数のディメンションがある棒グラフの並べ替え
- data: `付属データ/Chap02/2.7_spotify_music`
- Viz: [ch\.2\.7: 複数のディメンションがある棒グラフの並べ替え \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_7/sheet0?publish=yes)

🌟ポイント
- 結合済みフィールドで並べ替えて、そのヘッダーを非表示にする

<video controls loop width="600" poster='img/2_7.png' src='img/2_7.webm'></video>


## <span id="cp2_8">2.8</span>　データがないセルに0を表示
- data: `付属データ/Chap02/2.8_hotel_bookings.csv`
- Viz: [ch\.2\.8: データがないセルに0を表示 \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_80/sheet1?publish=yes)

🌟ポイント
- 下記の様な計算式を使用する
  - `zn(lookup(COUNT([2.8_hotel_bookings.csv]),0))`
- `zn(COUNT([2.8_hotel_bookings.csv]))`だけでは意図通りに動作しない！
  - [Tableau の操作の順序](https://help.tableau.com/current/pro/desktop/ja-jp/order_of_operations.htm)が関係している
  - 参考：[Tableau Tips メジャーの空白（NULL）を0で埋める「表計算　LOOKUP, INDEX\(\)\-INDEX\(\)」｜Rika｜note](https://note.com/rika_olga_f/n/n2e8e0454d4ec)
- 🔍以下も参照(今回の例はリンク先の「オプション3」の方法)
  - [NULL や欠落しているデータをゼロまたは既存データで置き換える \| Tableau Software](https://kb.tableau.com/articles/howto/populate-empty-cells-in-a-text-table-with-zeroes-or-existing-data?lang=ja-jp)

<video controls loop width="600" poster='img/2_8.png' src='img/2_8.webm'></video>


## <span id="cp2_9">2.9</span>　少ない度数をまとめたヒストグラム
- data: `付属データ/Chap02/2.9_airbnb_summary_listings.csv`
- Viz: [ch\.2\.9: 少ない度数をまとめたヒストグラム \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_9/sheet1?publish=yes)

🌟ポイント
- 参考書籍では以下のような計算フィールドを作成しているが、あまりにも冗長…
  ```
  if [Price] < 5000 then "0 ~ 4999"
  elseif [Price] < 10000 then "5000 ~ 9999"
  ...
  ```
- せっかくビンを作る機能があるので、以下のような計算フィールドを作成してビンを作成した。(動画)
  ```
  if [Price] >= 50000 then 50000
  else [Price]
  end
  ```

<video controls loop width="600" poster='img/2_9.png' src='img/2_9.webm'></video>


## <span id="cp2_10">2.10</span>　将来日付データの領域まで表示
- data: `付属データ/Chap02/2.10_pcr_positive_daily.csv`
- Viz: [2\.10: 将来日付データの領域まで表示 \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/2_10_16590828107410/sheet0?publish=yes)

🌟ポイント
- 軸範囲の固定
- 定数線の追加
  - 定数を超えるデータがあっても、軸は自動で広がる。最大の値が不明の場合に適している

## <span id="cp2_11">2.11</span>　積み上げ棒グラフの棒内でカテゴリを並べ替え
- data: `付属データ/Chap02/2.11_trade_prices_tokyo_condo(2020).csv`
- Viz: [ch\.2\.11: 積み上げ棒グラフの棒内でカテゴリを並べ替え \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_2_11/sheet1?publish=yes)

🌟ポイント
- 結合済みフィールドを活用

<video controls loop width="600" poster='img/2_11.png' src='img/2_11.webm'></video>


## <span id="cp2_12">2.12</span>　積み上げ棒グラフの色カテゴリで棒を並べ替え
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 

## <span id="cp2_13">2.13</span>　前年同月比を最終年のみ表示
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 

## <span id="cp2_14">2.14</span>　各カテゴリの上位Nのみ表示
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 

## <span id="cp2_15">2.15</span>　4月開始の上期・下期の表示
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 

## <span id="cp2_16">2.16</span>　長いテキストの折り返し表示
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 

## <span id="cp2_17">2.17</span>　左右の軸の範囲を合わせたピラミッドチャート
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 

## <span id="cp2_18">2.18</span>　異なるデータの異なるフィールド値同士の比較
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 

## <span id="cp2_19">2.19</span>　選択フィルター値を挿入したタイトル
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 

## <span id="cp2_20">2.20</span>　異なるダッシュボードへのフィルターアクション
- data: `付属データ/Chap02/`
- Viz: 

🌟ポイント
- 




