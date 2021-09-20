# Hook一覧

## logic

- 実行タイミング:毎フレーム

- 例:

```js
Game.registerHook('logic', () => {
    //10秒ごとに通知を表示
    if (Game.T % (Game.fps * 10) == 0) {
        Game.Notify(`10秒毎`, '', [16, 5]);
    }
    //1分秒ごとに通知を表示
    if (Game.T % (Game.fps * 60) == 0) {
        Game.Notify(`1分毎`, '', [16, 5]);
    }
});
```

## draw

- 実行タイミング:毎フレーム


- 例:
```js
Game.registerHook('draw', () => {
    if (!Game.OnAscend) {
        //昇天画面じゃない場合
        //CpSの下に毎分を表示する
        const html = l('cookiesPerSecond').innerHTML
        l('cookiesPerSecond').innerHTML = html + '<br>毎分: ' + Beautify(Game.cookiesPs * (1 - Game.cpsSucked) * 60, 1)
    }
});
```

## reset
- 引数：ハードリセットの場合true

- 実行タイミング:昇天時 or セーブ消去時


```js
Game.registerHook('reset', (hard) => {
    if (hard) {
        Game.Notify(`セーブを消去`, '', [16, 5]);
    } else {
        Game.Notify(`昇天`, '', [16, 5]);
    }
});
```

## reincarnate

- 実行タイミング:昇天時
- 例:

```js
 Game.registerHook('reincarnate', () => {

    Game.Notify(`昇天`, '', [16, 5]);
});
```

## ticker

- 戻り値：ニュースに表示したい文字列の配列
- 実行タイミング:ニュース表示時
- 例:
```js
 Game.registerHook('ticker', () => {
    return ['ニュースA', 'ニュースB', 'ニュースC']
});
```

## cps
- 引数：CpS値
- 戻り値：変更後のCpS

- 実行タイミング:CpS計算時
- 例:
```js
 Game.registerHook('cps', (cps) => {
     //cpsを2倍にする
    return cps*2
});
```

## cookiesPerClick
- 引数：1クリックあたりの生産量
- 戻り値：変更後の1クリックあたりの生産量

- 実行タイミング:1クリックあたりの生産量計算時
- 例:
```js
 Game.registerHook('cookiesPerClick', (cpc) => {
     //1クリックあたりの生産量を2倍にする
    return cpc*2
});
```


## click
- 実行タイミング:大きなクッキーをクリック時
- 例:
```js
 Game.registerHook('click', () => {
    Game.Notify(`大きなクッキーがクリックされた。`, '', [16, 5]);
});
```

## create
- 実行タイミング:ゲーム読み込み時
- 例:
```js
 Game.registerHook('create', () => {
    //ここにオリジナルのアップグレード/実績/バフ/建物などを実装を書く 
});
```

## check
- 実行タイミング:数秒毎に実行される
- 例:
```js
 Game.registerHook('check', () => {
    //アップグレードや実績の解除条件に満たしてるかなのど、定期的にチェックしたい処理を記載する
});
```

