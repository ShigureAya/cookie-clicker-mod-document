# CpS関連

## Game.globalCpsMult

クッキー生産数(倍率)

```js
Game.recalculateGains = 1;
```

## Game.recalculateGains

Game.recalculateGainsに1にするとCpSが再計算される

```js
Game.recalculateGains = 1;
```

## CpSを変更する

```js
 Game.registerHook('cps', (cps) => {
    //cpsを2倍にする
    return cps * 2
});
```


