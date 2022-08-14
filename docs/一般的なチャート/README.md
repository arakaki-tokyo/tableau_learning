# 一般的なチャートの作成方法
参照：
- 『[Tableauによる最強・最速のデータ可視化テクニック 第2版 ~データ加工からダッシュボード作成まで~](https://www.amazon.co.jp/Tableau%E3%81%AB%E3%82%88%E3%82%8B%E6%9C%80%E5%BC%B7%E3%83%BB%E6%9C%80%E9%80%9F%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%8F%AF%E8%A6%96%E5%8C%96%E3%83%86%E3%82%AF%E3%83%8B%E3%83%83%E3%82%AF-%E7%AC%AC2%E7%89%88-%E3%83%87%E3%83%BC%E3%82%BF%E5%8A%A0%E5%B7%A5%E3%81%8B%E3%82%89%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E4%BD%9C%E6%88%90%E3%81%BE%E3%81%A7-VISUAL-ANALYTICS/dp/4798173304/ref=pd_bxgy_img_sccl_2/357-7698875-8116535?pd_rd_w=gN3In&content-id=amzn1.sym.918446e7-72f4-48c7-a672-af3b6ace2b19&pf_rd_p=918446e7-72f4-48c7-a672-af3b6ace2b19&pf_rd_r=N1AWC3MKHDZ0RGJB2W8C&pd_rd_wg=HXkbu&pd_rd_r=8d0ad77f-09e2-448a-b389-4247f4055bcd&pd_rd_i=4798173304&psc=1)』
    - capter 2

Viz: [一般的なチャートまとめ \| Tableau Public](https://public.tableau.com/app/profile/.33622291/viz/_16582189901660/sheet0?publish=yes)

## チャートの一覧

1. 基本チャート
    - 棒グラフ
    - 折れ線グラフ
    - 積み上げ棒グラフ
    - 面グラフ
    - 散布図
    - 密度グラフ
    - ツリーマップ
    - 円グラフ
    - ヒストグラム
    - 箱ひげ図
1. 基本チャートの組み合わせ
    - 一つの軸で複数メジャーを扱う表現
    - 複合グラフ（二重軸で複数メジャーを扱う表現）
    - スパークライン
    - スモールマルチプル
    - ガントチャート
    - スロープグラフ
    - ドーナツチャート
    - 並列棒グラフ
    - ブレットグラフ
    - Bar in Barグラフ
1. 表計算のチャート
    - 100%積み上げ棒グラフ
    - 100%面グラフ
    - 滝グラフ(ウォーターフォールチャート)
    - パレート図
    - 管理図
1. 日付型データを利用した表計算のチャート
    - 累計
    - 差
    - 移動平均
    - 前年比成長率と前年比
    - バンプチャート
1. 地図
    - ポイントマップ
    - 比例シンボルマップ
    - 色塗りマップ
    - ヒートマップ
    - 二重軸マップ
1. 集計表
    - クロス集計表(テキストテーブル)
    - ハイライト表
    - ヒートマップ

## 基本チャート

### 円グラフ
<video controls loop width="600" src='img/円グラフ.webm'></video>










## 基本チャートの組み合わせ

### 一つの軸で複数メジャーを扱う
#### 方法1
<video controls loop width="600" src='img/一つの軸で複数メジャーを扱う1.webm'></video>










#### 方法2
<video controls loop width="600" src='img/一つの軸で複数メジャーを扱う2.webm'></video>











### スパークライン
MEMO: 「軸の編集」から「各行または列の独立した軸範囲」をチェック
<video controls loop width="600" src='img/スパークライン.webm'></video>










### ガントチャート
<video controls loop width="600" src='img/ガントチャート.webm'></video>










### ドーナツチャート
<video controls loop width="600" src='img/ドーナツチャート.webm'></video>










### 並列棒グラフ
<video controls loop width="600" src='img/並列棒グラフ.webm'></video>










### ブレットグラフ_表示形式を使う方法
🌟ポイント
- 特定の年のデータが欲しい場合には、計算フィールドで作成する
  - `IIF(YEAR([絞り込むに使うディメンション]) == 2020, [絞り込むメジャー], NULL)`
  - 会計年度で絞り込む場合は？
- 棒グラフとリファレンスラインに使われるメジャーが意図したものでない場合、横軸を右クリック>「リファレンスフィールドのスワップ」で交換可能
- リファレンスラインに到達したかどうかを色分けする場合、以下のような計算フィールドを作成し、[色]にドロップする
  - `SUM([棒グラフのメジャー]) > SUM([リファレンスラインのメジャー])`

🔍参照
- [クイック スタート: ブレット グラフ \- Tableau](https://help.tableau.com/current/pro/desktop/ja-jp/qs_bullet_graphs.htm)
- [5\+ Use Cases for xViz Bullet Chart using Microsoft Power BI](https://xviz.com/blogs/5-use-cases-for-xviz-bullet-chart-using-microsoft-power-bi/)
  - 進捗状況の把握にも役立つ
- [5 Use Cases For Bullet Charts \- Visual BI Solutions](https://visualbi.com/blogs/business-intelligence/dashboards/bullet-charts-use-cases/)
  - 2つ以上の値と比較することも可能(だが、視認性、必要性、代替可能性は検討するべき)
- [Understanding and Using Bullet Graphs \| Tableau](https://www.tableau.com/data-insights/reference-library/visual-analytics/charts/bullet-graphs)
  - 悪い例

<video controls loop width="600" src='img/ブレットグラフ.webm'></video>










### ブレットグラフ_表示形式を使わない方法
🌟ポイント
- リファレンスラインとして使いたいメジャーを[詳細]にドロップ
- [アナリティクス]ペインの[リファレンスライン]を[セル]にドロップ
  - **[値]のドロップダウンリストは[詳細]にドロップしたメジャーを選択しなおす**
  - 必要に応じて集計方法も変更する
- 背景として割合を表す色を設定する場合([分布バンド])も同じ手順・注意点

<video controls loop width="600" src='img/ブレットグラフ_表示形式を使わない方法.webm'></video>










### Bar in Barグラフ
🌟ポイント
- [軸の同期]を忘れずに！

<video controls loop width="600" src='img/Bar in Barhグラフ.webm'></video>










## 表計算のチャート

### 100％積み上げ棒グラフ
🌟ポイント
- [次を使用して計算]では[セル]や[表(横)]でも今回の場合同じ挙動となる。
  - [色]分けに使うディメンションを変えることを想定する場合は[セル]に
  - 表の形を変えることを想定する場合は[カテゴリ]に

<video controls loop width="600" src='img/100％積み上げ棒グラフ.webm'></video>










#### 地域やカテゴリの並べ替え
<video controls loop width="600" src='img/100％積み上げ棒グラフ_並べ替え.webm'></video>










### 100％面グラフ

<video controls loop width="600" src='img/100％面グラフ.webm'></video>










### 滝グラフ
🌟ポイント
- 各項目の長さを下(マイナス)方向に伸ばすため、以下のような計算フィールドを作成して[サイズ]にドロップする
  - `- [長さで表すメジャー]`

<video controls loop width="600" src='img/滝グラフ.webm'></video>










### パレート図
🌟ポイント
- 定数線を引くために、x軸を累計の割合で表す必要がある
  - **列のフィールドで[メジャー]>[カウント(個別)]に変更する前に以下を実施！(順不同)**
    - 右クリックから[並べ替え]>[フィールド]、[降順]を選択
    - 当該フィールドを[詳細]にドロップ
  - 上の2つの手順は下記のようにまとめることもできる。が、分かりづらい…
    - 当該フィールドを[詳細]にドロップしてクリック、ツールバーの[降順で並べ替え]ボタンを2回クリック
- [表計算]では[次を使用して計算]の選択や[セカンダリ計算の追加]を忘れないように！


🔍参照
- [パレート図の作成 \- Tableau](https://help.tableau.com/current/pro/desktop/ja-jp/pareto.htm)
  - 手軽だがx軸の定数線を引くことができない
- [Tableauでのパレート図の作り方 \| バンブロ ～BIでビジネスにイノベーションを～](https://blogs.techvan.co.jp/bi/2020/07/13/tableau%E3%81%A7%E3%81%AE%E3%83%91%E3%83%AC%E3%83%BC%E3%83%88%E5%9B%B3%E3%81%AE%E4%BD%9C%E3%82%8A%E6%96%B9)
  - この手順を参考にした
<video controls loop width="600" src='img/パレート図.webm'></video>











### 管理図
🌟ポイント

- **2重軸で同じデータを重ねる場合、フィールドを複製しなければならない！**
- 下記の式で`±3 × 標準偏差`の計算フィールドを追加。
  `STDEV`(標本)と`STDEVP`(母集団)の違いの注意！⇐分布バンドと同じ計算を選択
```
SUM([利益]) < WINDOW_AVG(SUM([利益])) - 3*WINDOW_STDEVP(SUM([利益]))
or 
WINDOW_AVG(SUM([利益])) + 3*WINDOW_STDEVP(SUM([利益])) < SUM([利益])
```

<video controls loop width="600" src='img/管理図.webm'></video>










## 日付型データを利用した表計算のチャート

### 日付_累計
🌟ポイント
- フィールドを右クリックした[表計算の編集]で[計算アシスタント]の表示をチェックすると、[次を使用して計算]の計算順序が示される

<video controls loop width="600" src='img/日付_累計.webm'></video>











### 日付_差

#### 前月差
<video controls loop width="600" src='img/日付_差_前月.webm'></video>














#### 前年同月差(日付を離散値として)
<video controls loop width="600" src='img/日付_差_前年(日付を離散値として).webm'></video>











#### 前年同月差(日付を連続値として)
🌟ポイント
- 簡易表計算を行ったフィールドをデータペインにドロップして新しいフィールドを作成する
- 新しいフィールドの計算式を編集することができる
  - 今回は前月(-1)との差を計算していた部分を、前年同月(-12)との差を計算するように変更
<video controls loop width="600" src='img/日付_差_前年(日付を連続値として).webm'></video>












### 移動平均
🌟ポイント
- 移動平均の計算フィールドは以下
  - `WINDOW_AVG(SUM([フィールド名]), 開始, 終了)`

<video controls loop width="600" src='img/移動平均.webm'></video>










### 前年比成長率と前年比
🌟ポイント
- 簡易表計算と似たような処理は複製して書き換えると便利！
  - 複製：[行]にある簡易表計算済みのフィールドを、Ctrlキーを押しながらDD
  - 書き換え：複製したフィールドをデータペインのドロップして編集

<video controls loop width="600" src='img/前年比成長率と前年比.webm'></video>










### バンプチャート
🌟ポイント
- [軸の編集]から、軸の反転ができる

<video controls loop width="600" src='img/バンプチャート.webm'></video>










## 地図
🔍参照
- [Tableau のマップおよび地理的データの分析 \- Tableau](https://help.tableau.com/current/pro/desktop/ja-jp/maps.htm)
- [サポートされているマップデータ](https://www.tableau.com/ja-jp/mapdata?_ga=2.17567929.1699144211.1657432308-1992375919.1656732280#data)

### 二重軸マップ
🌟ポイント
- [地域]に地理的役割を与える手順
  - [都道府県]フィールドに地理的役割(都道府県)を与える
  - [地域]を右クリック > [地理的役割] > [次から作成] > [都道府県] を順に選択する

<video controls loop width="600" src='img/二重軸マップ.webm'></video>




## 集計表
### 集計表
🌟ポイント
- メジャーを重ねてドロップすることで、「メジャーネーム×メジャーバリュー」のビューを簡単に作成できる

<video controls loop width="600" src='img/集計表.webm'></video>

### ハイライト表
🌟ポイント
- 「メジャーバリュー」を[色]にドロップした場合、[別の凡例を使用]でメジャーごとに凡例の書式設定ができる。

<video controls loop width="600" src='img/ハイライト表.webm'></video>


