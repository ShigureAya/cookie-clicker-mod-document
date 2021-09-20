# クッキー関連

## Game.cookiesEarned

貯まったクッキー

## Game.cookies

クッキー数

## Game.cookiesd

クッキー数(表示用)

## Game.cookiesPs

クッキー生産数

## Game.cookiesPsRaw

クッキー実生産数

## Game.cookiesPsRawHighest

クッキー実生産数(現昇天の最高記録)

## Game.cookiesReset

昇天で失ったクッキー

## Game.cookieClicks

クッキークリック数

## Game.goldenClicks

ゴールデンクッキークリック数(全期間)

## Game.goldenClicksLocal

ゴールデンクッキークリック数(現昇天中)

## Game.missedGoldenClicks

ゴールデンクッキーの逃した回数

## Game.handmadeCookies

手作りクッキー数

## Game.computedMouseCps

1クリックあたりの生産数

## Game.Earn

クッキー数を増やす  

```js
//クッキー数を1000増やす
Game.Earn(1000);
```

## Game.Dissolve
クッキー数を減らす
```js
//クッキー数を1000減らす
Game.Dissolve(1000);
```


## カスタムゴールデンクッキーの生成

```js
var newShimmer = new Game.shimmer('golden', {type: 'frenzy'});
newShimmer.sizeMult = 1;//クッキーの大きさ デフォルト値:Math.random() * 0.75 + 0.25

```

|  名前(JA)  |  名前(EN)  |  type  |効果|
| ---- | ---- | ---- | ---- |
|フィーバー|Frenzy|frenzy|クッキー生産量が1分17秒の間7倍に！|
|ラッキー！|Lucky|multiply cookies|クッキーを取得|
|台無し！|Ruin|ruin cookies|クッキーを失う|
|エルダーフィーバー|Elder frenzy|blood frenzy|クッキー生産量が6秒の間666倍に！|
|障害発生|Clot|clot|クッキー生産量が1分,6秒の間半分に！|
|クリックフィーバー|Click frenzy|click frenzy|クリックパワーが13秒の間x777！|
|呪われた指|Cursed finger|cursed finger|クッキー生産が10秒の間停止。<br>一方で1回のクリックはCpS10秒相当に。|
|クッキーチェーン|Cookie chain|chain cookie|次々にゴールデンクッキーが出現|
|クッキー乱舞|Cookie storm|cookie storm|7秒間ゴールデンクッキー大量出現|
|Building special|Building special|building special|30秒間CpSの増加または減少|
|ドラゴンハーベスト|Dragon Harvest|dragon harvest|クッキー生産量が1分の間15倍に！|
|ドラゴンフライト|Dragonflight|dragonflight|クリックパワーが10秒の間x1111！|
|甘い!|Sweet|free sugar lump|砂糖玉を1個取得|
|お喋り|Blab|blab|テキストが表示されるだけ|
