# ゴールデンクッキー/トナカイ出現関連

## Game.shimmers

- 型:`Array<shimmer>`
- 詳細:  
  出現中のゴールデンクッキー/トナカイ([Shimmer](#shimmer))リスト
- 例:

```js
//出現中のゴールデンクッキー/トナカイを逆順でループ
//※ループ中にGame.shimmersの要素が減ってしまう為、逆順で処理ないとすべてに対して処理出来ない
for (let i = Game.shimmers.length - 1; i >= 0; i--) {
    //ゴールデンクッキー/トナカイをクリックする
    Game.shimmers[i].pop()
}
```

```js
//出現中のゴールデンクッキー/トナカイをループ
//※filterによってGame.shimmersと別の配列になる為、Game.shimmersの要素が減っても正しく処理出来る
Game.shimmers.filter(() => true).forEach(shimmer => {
    //ゴールデンクッキー/トナカイをクリックする
    shimmer.pop()
})
```

```js
//出現中のゴールデンクッキーをループ
//filterによってゴールデンクッキーのみに抽出
Game.shimmers.filter(shimmer => shimmer.type === 'golden').forEach(shimmer => {
    //ゴールデンクッキーをクリックする
    shimmer.pop()
})
```

```js
//出現中のゴールデンクッキー(怒り状態)をループ
//filterによってゴールデンクッキー(怒り状態)のみに抽出
Game.shimmers.filter(shimmer => shimmer.type === 'golden' && shimmer.wrath).forEach(shimmer => {
    //ゴールデンクッキー(怒り状態)をクリックする
    shimmer.pop()
})
```

[comment]: <> (## Game.shimmerTypes)

[comment]: <> (shimmerの種類の****定****義 golden reindeer)

[comment]: <> (nが画面上の数)

## Game.shimmer(type,obj,noCount)

- 引数:
    - `{string} type`  
      下記のどちらかを指定
        - `golden`:ゴールデンクッキー
        - `reindeer`：トナカイ
    - `{object} obj` 省略可  
      ゴールデンクッキーの場合のみ指定する
        - `{string} type` 省略可  
          ゴールデンクッキーの種類([参照](#%E3%82%B3%E3%82%99%E3%83%BC%E3%83%AB%E3%83%86%E3%82%99%E3%83%B3%E3%82%AF%E3%83%83%E3%82%AD%E3%83%BC%E3%81%AE%E7%A8%AE%E9%A1%9E))
          を指定する
        - `{boolean} wrath` 省略可  
          trueの場合、怒り状態のゴールデンクッキーにする
        - `{boolean} noWrath` 省略可  
          trueの場合、通常のゴールデンクッキーにする
    - `{boolean} noCount` 省略可  
      trueの場合、画面上の出現数にカウントしない
- 例:

```js
//ゴールデンクッキーを出現させる
new Game.shimmer('golden')
```

```js
//トナカイを出現させる
new Game.shimmer('reindeer')
```

```js
//ゴールデンクッキー(ドラゴンフライト)を出現させる
new Game.shimmer('golden', {type: 'dragonflight'})
```

```js
//ゴールデンクッキー(怒り状態)出現させる
new Game.shimmer('golden', {wrath: true})
```

```js
//ゴールデンクッキー(通常状態)出現させる
new Game.shimmer('golden', {noWrath: true})
```

```js
//ゴールデンクッキーを出現させる
//画面の出現数にはカウントしない
new Game.shimmer('golden', {}, true)
```

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

```js
//ゴールデンクッキーを出現させる
var newShimmer = new Game.shimmer('golden', {}, true)
//統計をカウントを有効にする
newShimmer.spawnLead = true
```

### sizeMult

- 型:`Number`

- 詳細:
  shimmerのサイズの倍率
- 例:

```js
//2倍の大きさのゴールデンクッキーを出現させる
var newShimmer = new Game.shimmer('golden')
newShimmer.sizeMult = 2
```

### pop

- 詳細:
  クリックされた際のFunction
- 例:

```js
//ゴールデンクッキーを出現させる
var newShimmer = new Game.shimmer('golden', {}, true)
//ゴールデンクッキーをクリックする
newShimmer.pop()
```

## ゴールデンクッキーの種類

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
