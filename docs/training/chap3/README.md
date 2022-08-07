# <span id="cp3">Chapter 3</span>　求める値の算出
- data: `付属データ/Chap03/`

## 目次
- [Chapter 3](#cp3)　 求める値の算出
    - [3.1](#cp3_1)　 不動産取引金額が最も大きい自治体は？
    - [3.2](#cp3_2)　 日本の幸福度を抜かした国は？
    - [3.3](#cp3_3)　 評価を行う割合の高いアニメの提供方法は？
    - [3.4](#cp3_4)　 PCR民間検査会社が占める陽性者割合は？
    - [3.5](#cp3_5)　 複数国で死者を出した津波が発生した国は？
    - [3.6](#cp3_6)　 1つのデータにあってもう1つのデータにない値は？
    - [3.7](#cp3_7)　 金額上位10000の取引が占める割合が最も高い市区町村は？
    - [3.8](#cp3_8)　 GDPと幸福度の相関が高い地域グループは？
    - [3.9](#cp3_9)　 GDPと寿命と都市化率がすべて上位5以内の国は？
    - [3.10](#cp3_10)　入院治療を要する者のうち重症者の割合は？
    - [3.11](#cp3_11)　レビューされた期間が長い部屋の種類は？
    - [3.12](#cp3_12)　幸福度が高い健康寿命年齢帯は？
    - [3.13](#cp3_13)　陽性者数の7日間移動平均は？
    - [3.14](#cp3_14)　平方メートルあたりの年別平均金額の範囲は？
    - [3.15](#cp3_15)　津波の震源2地点間の距離は？
    - [3.16](#cp3_16)　井の頭公園に最も近い宿泊施設の金額は？
    - [3.17](#cp3_17)　常用漢字数も画数も標準偏差1を上回る部首は？
    - [3.18](#cp3_18)　8四半期後に予測される金額は？
    - [3.19](#cp3_19)　国別幸福度の中央50%の範囲が最も広い地域は？
    - [3.20](#cp3_20)　平均取引価格が大きな市区町村とその理由は？
    - [3.21](#cp3_21)　海に面した市区町村で、金額もレビュー数も平均以上のホテルは？
    - [3.22](#cp3_22)　最新の年に購入履歴がある顧客割合は？
    - [3.23](#cp3_23)　各区の中で不動産取引価格の割合が大きい最寄駅は？
    - [3.24](#cp3_24)　日本より自由度と社会支援は低いが、幸福度が高い国は？
    - [3.25](#cp3_25)　あるアニメ作品を観た人が他に最も多く観たアニメ作品は？


## <span id="cp3_1">3.1</span>　不動産取引金額が最も大きい自治体は？
- data: `付属データ/Chap03/3.1_trade_prices(2019).csv`
- Viz: [ch\.3\.1: 不動産取引金額が最も大きい自治体は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_1/sheet0?publish=yes)

🌟ポイント
- カスタム分割の活用


## <span id="cp3_2">3.2</span>　日本の幸福度を抜かした国は？
- data: `付属データ/Chap03/3.2_world_happiness(2015_2020)`
- Viz: [ch\.3\.2: 日本の幸福度を抜かした国は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_2/sheet0?publish=yes)

🌟ポイント
- 列名が揃っていないデータソースをユニオンする場合、ユニオン後に同じ役割の列を複数選択し、「一致しないフィールドをマージ」をクリックする


## <span id="cp3_3">3.3</span>　評価を行う割合の高いアニメの提供方法は？
- data: `付属データ/Chap03/3.3_anime`
- Viz: [ch\.3\.3: 評価を行う割合の高いアニメの提供方法は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_3/sheet0?publish=yes)

🌟ポイント
- ツールヒント上で特定の色分け項目をクリックして並べ替えることができる(動画参照)

<video controls loop width="600" poster='img/3_3.png' src='img/3_3.webm'></video>
## <span id="cp3_4">3.4</span>　PCR民間検査会社が占める陽性者割合は？
- data: `付属データ/Chap03/3.4_pcr_case_daily.csv`
- Viz: [ch\.3\.4: PCR民間検査会社が占める陽性者割合は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_4PCR/sheet0?publish=yes)


## <span id="cp3_5">3.5</span>　複数国で死者を出した津波が発生した国は？
- data: `付属データ/Chap03/3.5_tsunami`
- Viz: [ch\.3\.5: 複数国で死者を出した津波が発生した国は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_5/sheet0?publish=yes)


## <span id="cp3_6">3.6</span>　1つのデータにあってもう1つのデータにない値は？
- data: `付属データ/Chap03/3.6_world_happiness(2018_2019)`
- 回答1：結合を使う方法
  - Viz: [ch\.3\.6: 1つのデータにあってもう1つのデータにない値は？\(結合を使う方法\) \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_611/sheet0?publish=yes)
  - 2018年と2019年のデータソースを左外部結合し、2018年の国名の一覧に対してフィルターで2019年の国名がNULLのレコード以外を除外する。
- 回答2：ユニオンを使う方法
  - Viz: [ch\.3\.6: 1つのデータにあってもう1つのデータにない値は？\(ユニオンを使う方法\) \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_611_16595884230690/1?publish=yes)
  - 方法1：以下でフィルター
    ```
    SUM(IIF([年] == 2018, 1, 0)) = 1
    AND 
    SUM(IIF([年] == 2019, 1, 0)) = 0
    ```
  - 方法2：以下でフィルター
    - 国名のカウントが2より小さい
    - 2018年


## <span id="cp3_7">3.7</span>　金額上位10000の取引が占める割合が最も高い市区町村は？
- data: `付属データ/Chap03/3.7_trade_prices(2020).csv`
- Viz: [ch\.3\.7: 金額上位10000の取引が占める割合が最も高い市区町村は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_710000/sheet0?publish=yes)

🌟ポイント
- 元のデータにindexなどのユニークなメジャーがあれば、ディメンションに変更して「特定のメジャーの上位〇〇」などのセットを作ることができる
  - そのようなメジャーがない場合には実現困難


## <span id="cp3_8">3.8</span>　GDPと幸福度の相関が高い地域グループは？
- data: `付属データ/Chap03/3.8_world_happiness(2020).csv`
- Viz: [ch\.3\.8: GDPと幸福度の相関が高い地域グループは？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_8GDP/1?publish=yes)

🌟ポイント
- 傾向線の説明をラベルなどで常に表示しておくことはできない…

## <span id="cp3_9">3.9</span>　GDPと寿命と都市化率がすべて上位5以内の国は？
- data: `付属データ/Chap03/3.9_world`
- Viz: [ch\.3\.9: GDPと寿命と都市化率がすべて上位5以内の国は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_9GDP5/1?publish=yes)

🌟ポイント
- セットの結合の活用

## <span id="cp3_10">3.10</span>　入院治療を要する者のうち重症者の割合は？
- data: `付属データ/Chap03/3.10_covid19`
- Viz: [ch\.3\.10: 入院治療を要する者のうち重症者の割合は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_10/sheet0?publish=yes)


## <span id="cp3_11">3.11</span>　レビューされた期間が長い部屋の種類は？
- data: `付属データ/Chap03/3.11_airbnb_listings.csv`
- Viz: [ch\.3\.11: レビューされた期間が長い部屋の種類は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_11/sheet0?publish=yes)


## <span id="cp3_12">3.12</span>　幸福度が高い健康寿命年齢帯は？
- data: `付属データ/Chap03/3.12_world_hapiness(2020).csv`
- Viz: [ch\.3\.12: 幸福度が高い健康寿命年齢帯は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_12/sheet0?publish=yes)


## <span id="cp3_13">3.13</span>　陽性者数の7日間移動平均は？
- data: `付属データ/Chap03/3.13_pcr_positive_daily.csv`
- Viz: [ch\.3\.13: 陽性者数の7日間移動平均は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_137/sheet0?publish=yes)

🌟ポイント
- 見せたい情報によって、ラベルマークで表示の仕方を選択(最小値/最大値、最新、すべて、など)
- 折れ線グラグは最新の値のみ表示させることが適している場合が多い

## <span id="cp3_14">3.14</span>　平方メートルあたりの年別平均金額の範囲は？
- data: `付属データ/Chap03/3.14_trade_prices_tokyo.csv`
- Viz: [ch\.3\.14: 平方メートルあたりの年別平均金額の範囲は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_14/sheet0?publish=yes)


## <span id="cp3_15">3.15</span>　津波の震源2地点間の距離は？
- data: `付属データ/Chap03/3.15_sources.csv`
- Viz: [ch\.3\.15: 津波の震源2地点間の距離は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_152/1?publish=yes)


## <span id="cp3_16">3.16</span>　井の頭公園に最も近い宿泊施設の金額は？
- data: `付属データ/Chap03/3.16_airbnb_summary_listings.csv`
- Viz: [ch\.3\.16: 井の頭公園に最も近い宿泊施設の金額は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_16/1?publish=yes)

🌟ポイント
- メニューバー「マップ」>「バックグランドレイヤー」より、マップの設定が可能

## <span id="cp3_17">3.17</span>　常用漢字数も画数も標準偏差1を上回る部首は？
- data: `付属データ/Chap03/3.17_joyo_kanji.csv`
- Viz: [ch\.3\.17: 常用漢字数も画数も標準偏差1を上回る部首は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_171/1?publish=yes)


## <span id="cp3_18">3.18</span>　8四半期後に予測される金額は？
- data: `付属データ/Chap03/3.18_trade_prices_tokyo.csv`
- Viz: [ch\.3\.18: 8四半期後に予測される金額は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_188/2?publish=yes)


## <span id="cp3_19">3.19</span>　国別幸福度の中央50%の範囲が最も広い地域は？
- data: `付属データ/Chap03/3.19_world_hapiness(2020).csv`
- Viz: [ch\.3\.19: 国別幸福度の中央50%の範囲が最も広い地域は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_1950/1?publish=yes)


## <span id="cp3_20">3.20</span>　平均取引価格が大きな市区町村とその理由は？
- data: `付属データ/Chap03/3.20_trade_prices_tokyo(2010_2020).csv`
- Viz: [ch\.3\.20: 平均取引価格が大きな市区町村とその理由は？ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/ch_3_20/1?publish=yes)

🌟ポイント
- 

## <span id="cp3_21">3.21</span>　海に面した市区町村で、金額もレビュー数も平均以上のホテルは？
- data: `付属データ/Chap03/`
- Viz: 

🌟ポイント
- 

## <span id="cp3_22">3.22</span>　最新の年に購入履歴がある顧客割合は？
- data: `付属データ/Chap03/`
- Viz: 

🌟ポイント
- 

## <span id="cp3_23">3.23</span>　各区の中で不動産取引価格の割合が大きい最寄駅は？
- data: `付属データ/Chap03/`
- Viz: 

🌟ポイント
- 

## <span id="cp3_24">3.24</span>　日本より自由度と社会支援は低いが、幸福度が高い国は？
- data: `付属データ/Chap03/`
- Viz: 

🌟ポイント
- 

## <span id="cp3_25">3.25</span>　あるアニメ作品を観た人が他に最も多く観たアニメ作品は？
- data: `付属データ/Chap03/`
- Viz: 

🌟ポイント
- 

