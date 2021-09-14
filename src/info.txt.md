#  設定ファイル(info.txt)
Modの構成設定を`info.txt`に記載します。

info.txt
```json
{
  "Name": "Sample Mod",
  "ID": "sample mod",
  "Author": "Orteil",
  "Description": "A bare-bones sample mod.",
  "ModVersion": 1,
  "GameVersion": 2.031,
  "Date": "13/08/2021",
  "Dependencies": [],
  "LanguagePacks": [
    "lang.js"
  ],
  "Disabled": 1,
  "AllowSteamAchievs": 1
}
```

## Name

- 型:`string`  
  Modの表示名

## ID

- 型:`string`  
  ModのID(英数字とスペースのみ)
  データのセーブ/ロードや依存関係のキーとして使用されます
  `Game.registerMod(id,hooks)`に指定するIDと同じである必要があります。

## Author

- 型:`string`  
  Mod作成者の名前

## Description

- 型:`string`  
  Modの説明

## ModVersion

- 型:`number`
  a number value for your mod's version

## GameVersion

- 型:`number`
  このModが動くことが確認出来たCookieClickerのバージョン

## Date

- 型:`string`  
  Modの最終更新日

## Dependencies  <Badge text="任意"/>

- 型:`Array<string>`
  このModを使用する際に必要なModのIDを配列で指定
- 使用方法:

```json
"Dependencies": ["cool mod preloader", "extra stuff"],
```

## LanguagePacks <Badge text="任意"/>

- 型:`Array<string>`
  言語設定に関わるファイルを配列で指定

```json
"LanguagePacks": ["EN.js", "JP.js"],
```

## Disabled <Badge text="任意"/>

- 型:`number`
  1を指定した場合デフォルトで無効になります。   
  未指定の場合Mod初回認識時に自動的にModが有効になります。

```json
  "Disabled": 1,
```

## AllowSteamAchievs <Badge text="任意"/>

- 型:`number`
  デフォルトの場合Modが有効になっている間、Steamの実績解除をブロックします。
  (言語ファイルのみで構成されている場合は除く)
  ゲームバランスに影響しないModの場合1を設定し、Steamの実績解除をブロックしないようにします。

```json
  "AllowSteamAchievs": 1
```