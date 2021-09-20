# Modに関するAPI

## Game.registerMod(id, mod)

- 引数:
    - `{string} id`  
      `info.txt`の`ID`と同じIDを設定する。
    - `{object} mod`  
        init:初期処理を記載  
        save:セーブ時の処理を記載  
        load:ロード時の処理を記載
    ```js
    Game.registerMod("my mod", {
        init: function () {
            // Modの初期処理をここに記載
        }
        ,
        save: function () {
            // 返り値の文字列がセーブデータとして保存されます。
            return 'save data';
        }
        ,
        load: function (str) {
            // 引数に `save`で保存した文字列が入ります。
        }
    });
    ```

- 使用方法:

`save`の戻り値には文字列でしか渡すことができません。より複雑なデータを保存したい場合は文字列化したJSONで保存します。

- 例:  
json形式でセーブデータを保存する
```js
let saveData = {
    dataA: 'aaa',
    dataB: 1,
    dataC: true
}
Game.registerMod("my mod", {
    init: function () {
        // Modの初期処理をここに記載
    }
    ,

    save: function () {
        return JSON.stringify(saveData);
    }
    ,
    load: function (str) {
        saveData = JSON.parse(str);
    }
});
```

## Game.registerHook(hook, func)

- 引数:
    - `{string} hook`  
        フックしたい処理のHookID 
        指定可能なHookID  
       'logic','draw','reset','reincarnate','ticker','cps','cookiesPerClick','click','create','check'  
        [詳しくはこちらを参照](./Hook.md)
      - `{function|Array<function>} func`  
        フック時に行いたいfunction

- 例:  
単一指定
```js
function funcA() {
    //処理
}
Game.registerHook('click', funcA);
```

```js
Game.registerHook('click', function () {
    //処理
});
```

```js
Game.registerHook('click', () => {
    //処理
});
```

配列指定
```js
function funcA() {
   //処理
}
function funcB() {
    //処理
}
Game.registerHook('click',[funcA,funcB]);
```




## Game.removeHook(hook, func)

- 引数:
    - `{string} hook`  
      HookIDを指定
    - `{function|Array<function>} func`  
      Game.registerHookで登録したfunction

- 例:  
  単一指定
```js
function funcA() {
    //処理
}
//処理を登録
Game.registerHook('click', funcA);
//処理の登録解除
Game.removeHook('click', funcA);
```
