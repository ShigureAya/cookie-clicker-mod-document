# ゴールデンクッキー/トナカイ出現関連

## Game.shimmers

- 型:`Array<shimmer>`
- 詳細:  
  表示中のShimmer一覧

## Game.shimmerTypes

shimmerの種類の定義 golden reindeer

nが画面上の数

## Game.shimmer(type,obj,noCount)

- 引数:
    - `{string} type`  
      下記のどちらかを指定
        - `golden`:ゴールデンクッキー
        - `reindeer`：トナカイ
    - `{object} obj` 省略可  
      ゴールデンクッキーの場合のみ指定する
        - `{string} type` 省略可  
          ゴールデンクッキーの種類([参照](#ゴールデンクッキーの種類))を指定する
        - `{boolean} wrath` 省略可  
          trueの場合、怒り状態のゴールデンクッキーにする
        - `{boolean} noWrath` 省略可  
          trueの場合、通常のゴールデンクッキーにする
    - `{boolean} noCount` 省略可  
      trueの場合、画面上の出現数にカウントしない

## shimmer

### type

- 型:`'golden'|'reindeer'`

- 詳細:  
  下記のどちらかが格納されている
    - `golden`:ゴールデンクッキー
    - `reindeer`：トナカイ

### l

- 型:`Element`

- 詳細:  
  shimmerの要素の参照が格納されている

### noCount

- 型:`boolean`

- 詳細:  
  trueの場合、画面上の出現数にカウントしない

### wrath

- 型:`boolean`

- 詳細:  
  trueの場合、怒り状態

### life

- 型:`Number`

- 詳細:
  生存時間 フレーム単位 0になったら消える

### dur

- 型:`Number`

- 詳細:
  デスポーンするまでの時間 秒単位

### spawnLead

- 型:`boolean`

- 詳細:
  trueの場合、クリック数などの統計をカウントする

### sizeMult

- 型:`Number`

- 詳細:
  shimmerのサイズの倍率

### pop

- 詳細:
  クリックされた際のFunction

# ゴールデンクッキーの種類

| type             | 名前(JA)           | 名前(EN)           | 効果                                       |
|------------------|------------------|------------------|------------------------------------------|
| frenzy           | フィーバー            | Frenzy           | クッキー生産量が1分17秒の間7倍に！                      |
| multiply cookies | ラッキー！            | Lucky            | クッキーを取得                                  |
| ruin cookies     | 台無し！             | Ruin             | クッキーを失う                                  |
| blood frenzy     | エルダーフィーバー        | Elder frenzy     | クッキー生産量が6秒の間666倍に！                       |
| clot             | 障害発生             | Clot             | クッキー生産量が1分,6秒の間半分に！                      |
| click frenzy     | クリックフィーバー        | Click frenzy     | クリックパワーが13秒の間x777！                       |
| cursed finger    | 呪われた指            | Cursed finger    | クッキー生産が10秒の間停止。<br>一方で1回のクリックはCpS10秒相当に。 |
| chain cookie     | クッキーチェーン         | Cookie chain     | 次々にゴールデンクッキーが出現                          |
| cookie storm     | クッキー乱舞           | Cookie storm     | 7秒間ゴールデンクッキー大量出現                         |
| building special | Building special | Building special | 30秒間CpSの増加または減少                          |
| dragon harvest   | ドラゴンハーベスト        | Dragon Harvest   | クッキー生産量が1分の間15倍に！                        |
| dragonflight     | ドラゴンフライト         | Dragonflight     | クリックパワーが10秒の間x1111！                      |
| free sugar lump  | 甘い!              | Sweet            | 砂糖玉を1個取得                                 |
| blab             | お喋り              | Blab             | テキストが表示されるだけ                             |
