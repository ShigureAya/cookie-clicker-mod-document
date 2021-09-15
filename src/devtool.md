#  開発者ツールを開く

1. SteamのライブラリからCookieClickerのローカルファイルを開く。
![img.png](src/img/devtool/img.png)

2. 'Cookie Clicker\resources\app\start.js'を開く。
   
3. `DEV`変数を`1`に変える。
```js{11}
/*
	intruder! intruder! someone breached into the core files!
	nah just kidding, just poke around responsibly and try not to break stuff
*/
const {app,BrowserWindow,screen,ipcMain,dialog,shell}=require('electron');
const path=require('path');
const fs=require('fs');
let greenworks;
let greenworksLaunched=false;

let DEV=1;//display menu and js console
let BETA=0;//save and load using different save slot
```
4. CookieClickerを起動すると、開発者ツールが開いた状態で開始される。
![img.png](src/img/devtool/img_1.png)
