# カレンダーの作成方法
## 月のカレンダー

- 参考
  - [【Tableau】カレンダー風表の作り方｜パーソルプロセス＆テクノロジー SMKT事業部｜note](https://note.com/smkt_interview/n/n8288c6198aab)
  - [Tableauでカレンダーをつくってみた : Tabろぐ](http://blog.livedoor.jp/tab_hiro/archives/17308976.html)
  - [Tableauでカレンダー形式のダッシュボードを作成する方法 │ キヨシの命題](https://yolo-kiyoshi.com/2019/07/23/post-1179/)

## 年間カレンダー

- 作成したViz: [Tips: 年間カレンダー \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/Tips_16584759196560/STEP1?publish=yes)
- 参考
  - [Viz バラエティショー: ヒートマップカレンダーはいつ使うべきか](https://www.tableau.com/ja-jp/about/blog/2017/2/viz-variety-show-heatmaps-66330)
  - [Tableau極める Day14 カレンダーを作成して売上をハイライトする \- YouTube](https://www.youtube.com/watch?v=HlmYVDDF68k)

### STEP 1：ベースとなるチャートの作成
以下の通り作成

- 列：曜日(オーダー日)
- 行：週(オーダー日)
- フィルター：年(オーダー日): 2021
- マーク：
  - 色：合計(売上)
  - テキスト：日(オーダー日)

<video controls autoplay loop width="600" src='img/step1.webm'></video>

### STEP 2：月を3列×4行で配置する

- 以下2つの計算フィールドを作成し、ディメンションにする
  - 1
    - 名前：列番号
    - 式：`(DATEPART("month", [オーダー日]) + 2) % 3 + 1`
    - 用途：3列で配置する
  - 2
    - 名前：週番号
    - 式：`DATEPART("week", [オーダー日]) - { FIXED DATETRUNC("month", [オーダー日]): MIN(DATEPART("week", [オーダー日]))}`
    - 用途：4行で配置した際に高さを揃える
- 「行」の「週(オーダー日)」を「四半期(オーダー日)」に変更
- 作成した計算フィールドを以下の通り設定
  - 列：「列番号」「曜日(オーダー日)」
  - 行：「四半期(オーダー日)」「週番号」

<video controls autoplay loop width="600" src='img/step2.webm'></video>


### STEP 3：「週番号」を連続値にする

- 「週番号」を連続値にする
- 「週番号」の軸でスケールを反転させる
- マークで「`AVG(1)`」というフィールドを作成し、「サイズ」にドロップする
- ラベルの配置を上下左右中央にする

<video controls autoplay loop width="600" src='img/step3.webm'></video>

### STEP 4：月を表示する
- 「行番号」軸の範囲(開始値)を固定し、`-2`とする
- 以下の計算フィールドを作成する
  - 名前：月ラベル
  - 式：`if DATEPART("weekday", [オーダー日]) == 4 then -1 END`
  - 用途：月の表示位置
- 作成した計算フィールドを「行」のドロップして動画の操作を行う

<video controls autoplay loop width="600" src='img/step4.webm'></video>

### STEP 5：書式設定

- 曜日を上にする
  - メニューバー「分析」 > 「表のレイアウト」 > 「詳細」にて「垂直軸がある場合は、～」のチェックを外す
- 曜日の省略表示
  - 曜日の上で右クリック > 「書式設定」 > 「日付」のドロップダウンリストから「省略形」を選択
- 枠線の調整
  - メニューバー「書式設定」 > 「線」をクリック
    - 行：
      - グリッド線：「なし」
      - ゼロライン：「なし」
  - メニューバー「書式設定」 > 「枠線」をクリック
    - 行：
      - 行の境界線：
        - ペイン：「なし」
    - 列：
      - 列の境界線：
        - ペイン：最も太い線、白
- 不要なヘッダーの非表示
  - 「行番号」を右クリック > 「ヘッダーの表示」をクリック
  - 「列番号」を右クリック > 「ヘッダーの表示」をクリック
  - 「オーダー日」を右クリック > 「列のフィールドラベルを非表示」をクリック

<video controls autoplay loop width="600" src='img/step5.webm'></video>

### カレンダーが虫食い状態となる回避策

日付だけのデータソースを別途読み込んで組み合わせればよい。

- 使用したデータソース：[date.csv](https://github.com/arakaki-tokyo/tableau_learning/blob/main/data/date.csv)
- Viz: 上述のViz[発展2: 日付を別のデータソースから組み合わせる](https://public.tableau.com/app/profile/.33622291/viz/Tips_16584759196560/2)シート


## 前の週の同じ曜日との比較
- 作成したViz：[Tips: 前の週の同じ曜日との比較 \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/Tips_16587259523910/sheet0?publish=yes)

ポイント
- PCR陽性者数と日付を両方表示するため、上記の2重軸で月ラベルを表示するテクニックを使用。
- 2重軸にするため、定数を行シェルフに追加するテクニックを使用。参照：[一般的なチャート#ドーナツチャート](../一般的なチャート#ドーナツチャート)
