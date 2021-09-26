# 実績

## Game.Win(what)

- 引数:
    - `{string|Array<string>} what`  
      実績名

- 詳細:
  実績の解除する

- 例:
  1つの実績を解除

 ```js

Game.Win('Hardcore')
```

複数の実績を解除

```js
Game.Win(['Speed baking I', 'Speed baking II', 'Speed baking III'])
```

## Game.RemoveAchiev(what)

- 引数:
    - `{string} what`  
      実績名

- 詳細:
  実績を未解除にする

- 例:

  1つの実績を未解除にする

 ```js

Game.RemoveAchiev('Hardcore')
```

## Game.HasAchiev(what)

- 引数:
    - `{string} what`  
      実績名

- 戻り値：`{boolean}` true:解除済み false 未解除
- 詳細:
  実績が解除済みか判定する

- 例:

 ```js
if (Game.HasAchiev('Hardcore')) {
    //実績[ハードコア]を解除済みの場合
} else {
    //実績[ハードコア]を未解除の場合
}

```

## Game.SetAllAchievs(on)

- 引数:
    - `{boolean} on`  
      true:実績をすべて解除する false:実績をすべて未解除にする

- 例:
  実績をすべて解除する

```js
Game.SetAllAchievs(true);
```

実績をすべて未解除にする

```js
Game.SetAllAchievs(false);
```

[comment]: <> (## Game.Achievement)

[comment]: <> (## Game.TieredAchievement)

[comment]: <> (## Game.ProductionAchievement)

[comment]: <> (## Game.BankAchievement)

[comment]: <> (## Game.CpsAchievement)

## Game.Achievements

- 詳細:  
  実績の一覧

## Achievement

Achievementオブジェクトを取得

```js
const achieve = Game.Achievements['Wake and bake']
```

### id

- 型:`number`

- 詳細:  
  実績のID

### name

- 型:`string`
- 詳細:  
  実績の名前

### dname

- 型:`string`
- 詳細:  
  実績の名前(翻訳後)

### desc

- 型:`string`
- 詳細:  
  実績の説明

### icon

- 型:`Array<number>`

- 詳細:  
  実績のアイコン

### won

- 型:`boolean`

- 詳細:  
  trueの場合、解除済み

### order

- 型:`number`

- 詳細:  
  実績の順序

### pool

- 型:`string`
- 詳細:
    - `'normal'`:通常の実績
    - `'shadow'`:隠し実績
    - `'dungeon'`:ダンジョンに関する実績

### vanilla

- 型:`boolean`

- 詳細:  
  trueの場合、Steam実績を解除する  
  Modで追加するカスタム実績の場合はfalseにした方がいいと思われる

### clickFunction

- 型:`Function`

- 詳細:  
  実績クリック時の処理