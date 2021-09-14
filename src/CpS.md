# CpS関連

## CpSを再計算する

```js
Game.recalculateGains = 1;
```

## CpSを変更する


```js
//CpSを1000に固定
Game.CalculateGains = function () {
    Game.cookiesPs = 1;
    Game.computedMouseCps = Game.mouseCps();
    Game.recalculateGains = 0;
};
Game.recalculateGains = 1;
```


```js
Game.cookiesPs//毎秒生産量
Game.computedMouseCps//クリック生産量

```