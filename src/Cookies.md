# クッキー関連

## クッキー数変更

クッキー数を変更

```js
//クッキー数を1000にする
Game.cookies = 1000;
```

クッキー数を増やす

```js
//クッキー数を1000増やす
Game.Earn(1000);
```

クッキー数を減らす

```js
//クッキー数を1000減らす
Game.cookies -= 1000;
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
