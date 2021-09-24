# アセット

## Game.Loader.Replace(old,newer)

- 引数:
    - `{string} old`  
      画像のファイル名
    - `{object} newer`  
      画像のパスファイルパス

- 詳細:
  `Game.registerMod`の`init`内で`this.dir`でModのルートパスを取得可能なので Modのルートパスと画像のファイル名を組み合わせて`newer`に指定する
  `Game.registerHook`等でModのルートパスを取得したい場合は、`init`内で`this.dir`を変数に格納して置く必要がある。

- 例:  
  クッキーの画像をcoolCookie.pngに差し替え

```js
Game.registerMod("sample mod", {
    init: function () {
        //クッキーの画像をcoolCookie.pngに差し替え
        Game.Loader.Replace('perfectCookie.png', this.dir + '/coolCookie.png')
    },
    save: function () {
    },
    load: function (str) {
    },
})
```

5秒ごとにクッキーの画像を切り替える

```js
//Modのルートパス
let dir;

let toggle = false
Game.registerMod("sample mod", {
    init: function () {
        //Modのルートパスを保存しておく
        dir = this.dir

        Game.registerHook('draw', function () {
            if (!Game.OnAscend) {
                //昇天中じゃない場合

                if (Game.drawT % (Game.fps * 5) === 0) {
                    //5秒ごとにクッキーの画像切替
                    if (toggle) {
                        Game.Loader.Replace('perfectCookie.png', dir + '/coolCookieA.png');
                    } else {
                        Game.Loader.Replace('perfectCookie.png', dir + '/coolCookieB.png');
                    }
                    toggle = !toggle
                }

            }

        });
    },
    save: function () {
    },
    load: function (str) {

    },
});

```

## Pic(what)

- 引数:
    - `{string} what`  
      画像のファイル名
- 返り値:`HTMLImageElement`  
  img要素

[comment]: <> (## アイコン関連)

[comment]: <> (アイコンの画像パス：`src/img/icons.png`)

[comment]: <> (配列で指定)

[comment]: <> (x,y,画像パス)

[comment]: <> (48px区切り)

[comment]: <> (x,yは0始まり)